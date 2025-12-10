# Reliable-AI4Sys

### General Scheduling
1. [SOSP'25](https://dl.acm.org/doi/pdf/10.1145/3731569.3764846) COpter: Efficient Large-Scale Resource-Allocation via Continual Optimization

   _Suhas Jayaram Subramanya, Don Kurian Dennis, Gregory R. Ganger, Virginia Smith_

   Keywords: Resource-Allocation, MILP.

   Motivation: 1) Exsiting solvers are not scalable: Extremely slow with large scales. 2) Exsitings accelerating techniques cannot keep efficiency and optimality. 3) Accelerate and keep optimality .

   Design: 1) Solving a standard LP: Utilize standard LP to unify different problems. 2) System-level problem parametere manipulation for acceleration. 3) Eliminate slow post-processes from related LP solutions to MILP solutions by simple rounding.

### Storage Systems
1. [SOSP'24](https://dl.acm.org/doi/pdf/10.1145/3694715.3695968) Tiered Memory Management: Access Latency is the Key! 

   _Midhul Vuppalapati, Rachit Agarwal_
   
   Keywords: Measurement, Page placement

   Motivation: 1) Hotest pages may be not expected: Demonstrated by experiments. 3) Palcement should minimize expected latency. 

   Design: 1) Measure expected queue with small effort: CPU-to-memory datapath. 2) Algorithm (Or principle): Change type (hot or alternative) of pages by measured latencies.


### Networks
1. [SIGCOMM'25](https://dl.acm.org/doi/epdf/10.1145/3718958.3750524) SaTE: Low-Latency Traffic Engineering for Satellite Networks

   _Hao Wu, Yizhan Han, Mohit Rajpal, Qizhen Zhang, Jingxian Wang_

   Keywords: Satellite Network, Traffic Engineering, ML Generalization

   Motivation: 1) Dynamic: Satellite Networks' topology change frequently. 2) Generalization: NN-like approaches' general problem. 3) Large Scale: Numerous nodes and links.

   Design: 1) GNN-only: Elinimate DNN to improve generalizability. 2) Graph pruning based on topology similarity (to an existing baseline topology): improve generalizability. 3) Supervisely learn Gurobi's solution.


2. [SIGCOMM'25](https://dl.acm.org/doi/pdf/10.1145/3718958.3750519)Centralium: A Hybrid Route-Planning Framework for Large-Scale Data Center Network Migrations
   
   _Yikai Lin, Mohab Gawish(Meta)_
   
   Keywords: Centralized Routing, Distributed Routing, Network Migration, Route Planning, BGP
   
   Motivation:
   1)Data centers frequently undergo large-scale network migrations
   2)BGP cannot encode the sequential and conditional routing behaviors required during transitional migration phases.
   
   Design:
   1)Route Planning Abstraction (RPA):Intervenes in BGP decisions by injecting an "intent" (a prioritized set of paths) and three primitives: Path Selection RPA, Route Attribute RPA, and Route Filter RPA.
   2)Hybrid Control Plane: Centralium + BGP. Centralium is a centralized controller embedded with the RPA module, while BGP is responsible for route execution.
   3)Protection Mechanisms: Loop avoidance via worst-attribute advertisement, and transient traffic imbalance avoidance via bottom-up deployment.

4. [SIGCOMM'25](https://dl.acm.org/doi/10.1145/3718958.3750503)From ATOP to ZCube: Automated Topology Optimization Pipeline and a Highly Cost-Effective Network Topology for Large Model Training

   _Zihan Yan, Dan Li (Tsinghua University)_
   
   Keywords: Data center networks, Network topology, AI infrastructure
   
   Motivation:
   1)The explosive growth in LLM training scales requires new large-scale network topology designs.
   2)Expert-designed topologies overlook potential asymmetric structures and struggle to balance multi-objective performance; existing automated approaches are not mature enough.
   
   Design:1)formalize existing topologies into hyperparameters to  construct topology space.2)using the NSGA-II evolutionary algorithm to explore topology designs and evaluate in simulator(astra-sim).3)2-stage Evaluator: the first stage produces a Pareto-optimal set of topologies,the second obtains the final results.
### EDA
1. [DAC'21](https://ieeexplore.ieee.org/stamp/stamp.jsp?tp=&arnumber=9586188) NVCell: Standard Cell Layout in Advanced Technology Nodes with Reinforcement Learning

   _Haoxing Ren, Matthew Fojtik_
   
   Keywords: Standard Cell Layout, RL, DRC, Placement and Routing
   
   Motivation:1) Advanced technology nodes face DRC explosion with conditional and multi-pattern correlation, hard to model analytically. 2) Traditional methods suffer from long runtime, variable explosion, and poor scalability. 3) Need automated layout generation with competitive area and DRC compliance.

   Design: 1)Integrate simulated annealing, RL and ML routability prediction for placement. 2) Use genetic algorithm for initial routing and RL for local DRC fixing. 3)Pre-trained with simulated annealing samples. 4) ML routability predictor.


2. [DAC'20](https://ieeexplore.ieee.org/stamp/stamp.jsp?tp=&arnumber=9218757) GCN-RL Circuit Designer: Transferable Transistor Sizing with Graph Neural Networks and Reinforcement Learning

   _Hanrui Wang, Kuan Wang, Jiacheng Yang, et al._

   Keywords: Transistor Sizing, Graph Convolutional Network (GCN), RL, Transfer Learning

   Motivation: 1) Analog circuit sizing relies on human experts, time-consuming with complex performance tradeoffs.  2) Traditional black-box methods (BO, ES) ignore circuit topology and cannot transfer knowledge across technology nodes/topologies.  3) Need transferable automated sizing with superior performance.

   Design: 1)Circuit modeled as graph to capture topology. 2)7-layer GCN aggregates neighbor features, Actor-Critic architecture with DDPG for continuous action space. 3) Action space: Component-specific continuous parameters to avoid discrete space explosion. 
