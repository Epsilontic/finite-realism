# Finite Realism

Operational realism for finite agents: windows, earning (compression + intervention-stability), and persistence across refinements. Code + notebooks + paper.

## Quickstart
```python
from finite_realism.windows import Window
from finite_realism.ipm import product_tv, DW
from finite_realism.nd_projection import project_to_nd
from finite_realism.witnesses import chsh_witness

W = Window.from_defaults(eps=0.05)   # declare Φ_W, I, budgets
P_hat = ...  # empirical table
P_nd, eps_proj = project_to_nd(P_hat, weights="uniform")
S = chsh_witness(P_nd)               # S>2 indicates contextuality
margin = (S-2) - (W.eps + eps_proj + 0.02)  # 0.02 = ε_stat
print("Certified contextuality:", margin > 0)
