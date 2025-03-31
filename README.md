# icml


# Table 1

| Methods        | Exp-1 | Exp-2 | Exp-3 | Avg ± std     |
|----------------|-------|-------|-------|---------------|
| Random         | 68.76 | 68.83 | 69.17 | 68.92 (0.22)  |
| Avg-sim        | 70.08 | 70.24 | 70.73 | 70.35 (0.34)  |
| Perplexity     | 63.98 | 64.97 | 64.61 | 64.52 (0.50)  |
| Influence      | 65.33 | 65.25 | 65.02 | 65.20 (0.16)  |
| Rewriting      | 64.38 | 64.56 | 64.49 | 64.47 (0.09)  |
| Perplexity-MAB | 65.19 | 65.35 | 65.30 | 65.28 (0.08)  |
| Influence-MAB  | 68.49 | 67.68 | 67.17 | 67.78 (0.67)  |
| EQUAL(ours)    | 72.51 | 72.70 | 73.78 | 73.01 (0.69)  |



# Table 2

| Methods         | Error Bars |
|-----------------|------------|
| Random          | 68.92      |
| Avg-sim         | 70.35      |
| Perplexity      | 64.52      |
| Influence       | 65.20      |
| Rewriting       | 64.47      |
| Perplexity-MAB  | 65.28      |
| Influence-MAB   | 67.78      |
| EQUAL(ours)     | 73.01      |


 As suggested by the reviewer, we add KnowledgePile as the candidate dataset, associated with MMLU (a benchmark for evaluating knowledge and problem-solving skills) and BBH (a benchmark requiring multi-step reasoning) as new downstream tasks. We also add a model with a different size (internlm2-20B[cite]). The results are as follows:

| Model            | GSM8K | MATH  | FLOPs   | HUMANEVAL | MBPP  | FLOPs   | MMLU  | BBH   | FLOPs   |
|------------------|-------|-------|---------|-----------|-------|---------|-------|-------|---------|
| Base             | 76.16 | 25.5  | -       | 49.6      | 63.0  | -       | 67.1  | 70.3  | -       |
| Random           | 77.3  | 27.6  | 11.23   | 59.7      | 63.8  | 9.67    | 68.7  | 71.3  | 17.65   |
| Avg-sim          | 77.9  | 28.3  | 121.25  | 61.4      | 63.0  | 67.73   | 67.6  | 70.4  | 231.02  |
| Perplexity       | 76.6  | 31.1  | 156.70  | 62.5      | 63.8  | 73.25   | 68.3  | 72.0  | 302.51  |
| Influence        | 76.3  | 29.6  | 511.96  | 62.2      | 64.6  | 373.51  | 70.3  | 73.8  | 976.96  |
| Rewriting        | 77.5  | 30.5  | 21.38   | 63.3      | 64.7  | 16.96   | 69.7  | 73.3  | 28.10   |
| Perplexity-mab   | 77.7  | 31.9  | 21.35   | 63.2      | 63.7  | 17.01   | 69.1  | 72.2  | 28.23   |
| Influence-mab    | 76.7  | 30.7  | 32.76   | 64.7      | 64.1  | 28.46   | 70.6  | 73.7  | 46.53   |
| EQUAL            | 80.3  | 33.7  | 21.03   | 67.3      | 66.7  | 16.65   | 73.1  | 76.3  | 27.46   |


We thank your comments for improving our paper! Based on your valuable suggestions, we have added experiments by enlarging the model size and the diversity of downstream tasks, so as to further validate the effectiveness of EQUAL. The results are as follows:

**internlm-20B model**

| Method          | GSM8K | MATH  | FLOPs   | HUMANEVAL | MBPP  | FLOPs   | MMLU  | BBH   | FLOPs   |
|-----------------|-------|-------|---------|-----------|-------|---------|-------|-------|---------|
| Base            | 76.16 | 25.5  | -       | 49.6      | 63.0  | -       | 67.1  | 70.3  | -       |
| Random          | 77.3  | 27.6  | 11.23   | 59.7      | 63.8  | 9.67    | 68.7  | 71.3  | 17.65   |
| Avg-sim         | 77.9  | 28.3  | 121.25  | 61.4      | 63.0  | 67.73   | 67.6  | 70.4  | 231.02  |
| Perplexity      | 76.6  | 31.1  | 156.70  | 62.5      | 63.8  | 73.25   | 68.3  | 72.0  | 302.51  |
| Influence       | 76.3  | 29.6  | 511.96  | 62.2      | 64.6  | 373.51  | 70.3  | 73.8  | 976.96  |
| Rewriting       | 77.5  | 30.5  | 21.38   | 63.3      | 64.7  | 16.96   | 69.7  | 73.3  | 28.10   |
| Perplexity-mab  | 77.7  | 31.9  | 21.35   | 63.2      | 63.7  | 17.01   | 69.1  | 72.2  | 28.23   |
| Influence-mab   | 76.7  | 30.7  | 32.76   | 64.7      | 64.1  | 28.46   | 70.6  | 73.7  | 46.53   |
| EQUAL           | 80.3  | 33.7  | 21.03   | 67.3      | 66.7  | 16.65   | 73.1  | 76.3  | 27.46   |


Thanks for your suggestions on improving our paper! To demonstrate the benefit of the data extracted by EQUAL for the LLaMA-3.8B-Instruct model, we further fine-tuned the LLaMA-3.8B-Instruct model using the data synthesized by EQUAL. The results are as follows:

| Model               | GSM8K | MATH  | HUMANEVAL | MBPP  | MMLU  | BBH   |
|---------------------|-------|-------|-----------|-------|-------|-------|
| Llama3-8B-Instruct  | 79.5  | 30.0  | 60.4      | 70.6  | 68.7  | 53.7  |
| Llama3-8B-EQUAL     | 80.7  | 31.3  | 61.0      | 71.5  | 69.0  | 54.6  |



Thanks! We follow the method of Qurating[1] and add the baseline of data generation paired with LLM quality filtering(LLM-filtering). The results are as follows:
|               |       | GSM8K | MATH  | FLOPs   | HUMANEVAL | MBPP  | FLOPs   |
|---------------|-------|-------|-------|---------|-----------|-------|---------|
| LLM-filtering | LoRA  | 65.73 | 30.55 | 271.56  | 34.3      | 53.5  | 141.38  |
| EQUAL         | LoRA  | 67.32 | 31.86 | 17.75   | 36.0      | 55.3  | 12.99   |
| LLM-filtering | FULL  | 68.38 | 33.19 | 273.91  | 46.9      | 53.7  | 142.73  |
| EQUAL         | FULL  | 73.01 | 35.10 | 18.55   | 49.4      | 56.3  | 13.50   |


Thanks for your comments! We have added the results of the "All (Mammoth)" baseline in Table 1. The results are as follows:

| Method          | GSM8K | MATH  | FLOPs   | HUMANEVAL | MBPP  | FLOPs   | GSM8K | MATH  | FLOPs   | HUMANEVAL | MBPP  | FLOPs   |
|-----------------|-------|-------|---------|-----------|-------|---------|-------|-------|---------|-----------|-------|---------|
| ALL(Mammoth) LoRA | 65.43 | 32.90 | 170.21  | 34.8      | 55.3  | 126.38  | 55.15 | 21.50 | 159.60  | 29.6      | 46.3  | 121.23  |
| ALL(Mammoth) FULL | 70.28 | 40.02 | 181.66  | 45.6      | 56.0  | 143.73  | 62.21 | 26.52 | 176.11  | 35.7      | 47.0  | 134.91  |

