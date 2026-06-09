Abstract—In a recent interview on the Lex Fridman Podcast
(#494), NVIDIA CEO Jensen Huang observed that Moore’s Law
alone would have delivered roughly a 100× improvement in
computing performance over the past decade, while NVIDIA
achieved approximately a million-fold increase through what he
describes as “extreme co-design”—joint optimization across the
model, software stack, hardware architecture, memory hierarchy, and system infrastructure [1]. 
This observation highlights
the growing importance of algorithm–hardware co-design as a
primary driver of performance and energy efficiency in modern
artificial intelligence systems.
This work presents an empirical study of algorithm–hardware
co-design for large language model (LLM) inference on commodity GPU platforms. 
We evaluate the impact of low-precision quantization and structured sparsity on inference throughput, memory
utilization, power consumption, energy efficiency, and model
quality. Experiments were conducted using Llama 3.1 8B as the
primary evaluation model, with additional cross-model validation
performed using Llama 3.2 1B and Qwen 1.5-1.8B. Quantization
techniques included BitsAndBytes INT8 and INT4 quantization
as well as Activation-Aware Weight Quantization (AWQ), while
sparsity experiments compared naive 2:4 structured pruning
against MaskLLM-generated 2:4 sparsity masks. Results were
collected across NVIDIA T4, L4, and A100 GPUs to investigate
how hardware characteristics influence the effectiveness of these
optimization techniques. The findings provide insight into the
tradeoffs between model quality and inference efficiency and
demonstrate the importance of co-design when deploying LLMs
on resource-constrained hardware.

Some of our results are:
<img width="2370" height="1466" alt="dynamic_efficiency_comparison" src="https://github.com/user-attachments/assets/a631fcfa-f833-4339-9908-7e2356fe99e7" />
<img width="2370" height="1466" alt="memory_comparison" src="https://github.com/user-attachments/assets/c3df47f9-944d-4efd-9039-97fe76ad66d5" />
<img width="590" height="390" alt="perplexity" src="https://github.com/user-attachments/assets/409fd82b-2866-4a43-b71f-3a204bd20467" />
<img width="2370" height="1466" alt="power_comparison" src="https://github.com/user-attachments/assets/706cc7ee-5a52-4fba-acc3-d7344c802370" />
<img width="2370" height="1466" alt="throughput_comparison" src="https://github.com/user-attachments/assets/ee1612ab-fd6e-4b94-bd3d-14d77f85311d" />
<img width="2370" height="1466" alt="throughput_speedup_vs_fp16" src="https://github.com/user-attachments/assets/0a23ecf2-8970-49b0-90d3-4b600c9a04f3" />
