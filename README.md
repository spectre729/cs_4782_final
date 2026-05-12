# cs_4782_final

## Introduction
This repository contains our re-implementation of the paper _LoRA: Low-Rank Adaptation of Large Language Models_ by Edward J. Hu et al. The paper proposes a parameter-efficient fine-tuning method that freezes the pretrained model weights and trains only small low-rank update matrices inserted into selected Transformer layers.

The goal of this project was to reproduce and evaluate the effectiveness of LoRA as a parameter-efficient fine-tuning method for transformer-based language models. As an  extension to the paper we varied the LoRA rank r to examine how much model capacity is actually needed for effective adaptation.

## Chosen Result
Our project focused on reproducing the SST-2 and QNLI results (two GLUE
benchmark tasks) using the RoBERTa-base model presented in the original paper. Specifically, we evaluated whether LoRA fine-tuning could achieve performance comparable to full fine-tuning while using substantially fewer trainable parameters.

<img width="549" height="122" alt="Screenshot 2026-05-12 at 11 25 50 AM" src="https://github.com/user-attachments/assets/0924ce50-fb8e-4f31-bb3f-c2dad0099eb7" />

## GitHub Contents
- code/: A directory containing your re-implementation and extension code.
- data/: A directory containing a README with instruction on how to obtain the dataset.
- results/: A directory containing the results of your re-implementation (graphs/figures).
- poster/: A directory containing a PDF of the poster.
- report/: A directory containing a PDF of the final report submitted.

## Re-implementation Details
The RoBERTa-base model was trained on the SST-2 and QNLI datasets from the GLUE benchmark. Frameworks used for this project included PyTorch, Hugging Face Transformers, PEFT, and loralib. Evaluation metrics including analyzing training loss, validation loss, and accuracy. Challenges encountered included reproducing exact hyperparameter settings from the paper and balancing GPU memory constraints with training efficiency. 

## Reproduction Steps
1. In the repo open code/LoRA_reimplementation.ipynb
2. Make a copy of the Google Collab code
3. Connect to a T4 High-RAM runtime
4. Click "Run All" at the top of the file
5. Training and evaluation outputs will be generated automatically

## Results/Insights
Our re-implementation achieved performance comparable to the results reported in the original paper while training significantly fewer parameters than full fine-tuning. Performance remained competitive despite parameter reduction. 

## Conclusion
Our experiments demonstrated that low-rank adaptation can achieve strong downstream performance while dramatically reducing the number of trainable parameters. In addition to the re-implementation, the rank experiments showed that performance improves quickly at small ranks and then begins to plateau, showing that low-rank updates are
often sufficient for adapting pretrained language models.

## References
[1] Hu, E. J., Shen, Y., Wallis, P., Allen-Zhu, Z., Li, Y., Wang, S., Wang, L., and Chen, W. LoRA: Low-Rank Adaptation of Large Language Models. arXiv preprint arXiv:2106.09685, 2021.2

[2] Balaban, Michael. “A100 vs V100 Deep Learning Benchmarks — Lambda.” Lambda.ai, Lambda, Inc., 28 Jan.2021, lambda.ai/blog/nvidia-a100-vs-v100-benchmarks.

[3] Socher, Richard, et al. “Recursive Deep Models for Semantic Compositionality over a Sentiment Treebank.” Proceedings of the 2013 Conference on Empirical Methods in Natural Language Processing, 2013, pp. 1631–1642.

[4] Rajpurkar, P., Zhang, J., Lopyrev, K., & Liang, P. (2016). SQuAD: 100,000+ questions for machine comprehension of text. In Proceedings of the 2016 Conference on Empirical Methods in Natural Language Processing (pp.2383–2392)

[5] Wang, A., Singh, A., Michael, J., Hill, F., Levy, O., & Bowman, S. R. (2018). GLUE: A multi-task benchmark and analysis platform for natural language understanding. Proceedings of the 2018 EMNLP Workshop BlackboxNLP.

[6] Liu, Y., Ott, M., Goyal, N., Du, J., Joshi, M., Chen, D., Levy, O., Lewis, M., Zettlemoyer, L., & Stoyanov, V. (2019). RoBERTa: A robustly optimized BERT pretraining approach. arXiv preprint arXiv:1907.11692.

[7] Mangrulkar, S., Gugger, S., Debut, L., Belkada, Y., Paul, S., Bossan, B., & Tietz, M. (2022). PEFT: State-ofthe-art Parameter-Efficient Fine-Tuning methods https://github.com/huggingface/peft
## Acknowledgements
