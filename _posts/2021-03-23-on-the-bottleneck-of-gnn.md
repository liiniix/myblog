# [On The Bottleneck of Graph Neural Network](https://drive.google.com/file/d/1D8SahmGNWHWNVr-1Jp1YutUqx4V18q3D/view?usp=sharing)

# Abstract
- GNN struggles to propagate distant node info
- GNN are susceptible to bottleneck when carrying info from distant nodes
- The bottleneck cause over-squashing into fixed-sized vector
- As a result gnn fails in long term interaction

# Introduction

- Stacking multiple layers achieve long distant message passing.
- range of interactive between nodes: the problem radius
- But it has been obserbed that there is no benefit of more than few layers for distant node message passing.
- explanation was *over-smoothing*:  node representations are indistinguishable when number of layers increases.
- as the number of layers increases, the number of nodes in each node’s receptive field grows exponentially. This causes over-squashing: information from the exponentially-growing receptive field is compressed into fixed-length node vectors.