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
<img width="711" height="511" alt="Screenshot 2026-06-09 at 9 55 16 AM" src="https://github.com/user-attachments/assets/09e296fd-1d60-40fb-ac94-b9cd161a9d3c" />
<img width="913" height="321" alt="Screenshot 2026-06-09 at 9 53 35 AM" src="https://github.com/user-attachments/assets/923be551-e4e9-4c59-9d33-52352a4be17a" />
<img width="5343" height="2954" alt="Llama8B_Total_Energy_Ranking" src="https://github.com/user-attachments/assets/001c9a3a-2df9-4a2d-85f6-301444aaf647" />
<img width="5340" height="2951" alt="Llama8B_Efficiency_Ranking" src="https://github.com/user-attachments/assets/279f5077-7cf2-4524-a815-0bf7b164070c" />
<img width="4157" height="2353" alt="L4_Llama8B_throughput_vs_memory_pareto" src="https://github.com/user-attachments/assets/749e717f-a150-481f-b87d-7cd1cdeff21b" />
<img width="4158" height="2353" alt="L4_Llama8B_efficiency_vs_memory_pareto" src="https://github.com/user-attachments/assets/953983ee-4d4c-492c-adac-a573f88f1672" />
<img width="3600" height="3000" alt="A100_sparsity_FP16_vs_MaskLLM" src="https://github.com/user-attachments/assets/16fc0044-27ec-4649-a808-e0d36ab3a78a" />
<img width="4157" height="2353" alt="A100_Llama8B_throughput_vs_memory_pareto" src="https://github.com/user-attachments/assets/2407eef6-ee38-4fea-99f2-cc06eeecc0db" />
<img width="4158" height="2353" alt="A100_Llama8B_efficiency_vs_memory_pareto" src="https://github.com/user-attachments/assets/3ca833ce-2aee-4669-8fd4-eb987064eabb" />
<img width="4157" height="2353" alt="T4_Llama8B_throughput_vs_memory_pareto" src="https://github.com/user-attachments/assets/60dd708e-03f8-4bef-8b1d-ab37deab5822" />
<img width="4157" height="2353" alt="T4_Llama8B_efficiency_vs_memory_pareto" src="https://github.com/user-attachments/assets/7c7d3867-1ee1-4a0b-b8bd-343d6d37875f" />
<img width="6540" height="4210" alt="Qwen_Llama1B_Comparison" src="https://github.com/user-attachments/assets/76649428-1f80-4555-aebc-8d822e9dd12b" />
<img width="6551" height="4043" alt="Llama8B_Quantization_GPU_Comparison" src="https://github.com/user-attachments/assets/4306849a-2491-44d0-b3a8-a48c308d68fe" />
