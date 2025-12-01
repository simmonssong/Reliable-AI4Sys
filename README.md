# Reliable-AI4Sys

### General Methods
1. [SOSP'25](https://dl.acm.org/doi/pdf/10.1145/3731569.3764846) COpter: Efficient Large-Scale Resource-Allocation via Continual Optimization

   _Suhas Jayaram Subramanya, Don Kurian Dennis, Gregory R. Ganger, Virginia Smith_

   Keywords: Resource-Allocation, MILP.

   Motivation: 1) Exsiting solvers are not scalable: Extremely slow with large scales. 2) Exsitings accelerating techniques cannot keep efficiency and optimality. 3) Accelerate and keep optimality .

   Design: 1) Solving a standard LP: Utilize standard LP to unify different problems. 2) System-level problem parametere manipulation for acceleration. 3) Eliminate slow post-processes from related LP solutions to MILP solutions by simple rounding.
   
2. [SOSP'24](https://dl.acm.org/doi/pdf/10.1145/3694715.3695968) Tiered Memory Management: Access Latency is the Key! 

   _Keywords: Memory management, Measurement_

   Motivation: 1) Page placement in memory. 2) Hotest pages may be not expected: Demonstrated by experiments. 3) Palcement should minimize expected latency. 

   Design: 1) Measure expected queue with small effort: CPU-to-memory datapath. 2) Algorithm (Or principle): Change type (hot or alternative) of pages by measured latencies.
