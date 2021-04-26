- Most of the game tree increase exponential rate.
- Ideally knowing every move is cool but as it increases exponentialy, computation needed goes beyond limit.
- Monte Carlo Tree Search solves it by sampling.
- MCTS has four phases: Selection, Expansion, Rollout/Simulation, Bakpropagation

#### Selection
Player select best node form tree expanded so far making choice based on visit count and utilities score.

#### Expansion
The successor of the node selected on selection step exanded.

#### Rollout/Simulation
Player rollout the selected node until terminal node occours.

#### Backpropagation
The value earned in terminal state is backpropagated towards its root and node visit count is also updated.

#### Upper confidance bound (UCB1)
$$ v_i + C \times \sqrt{\frac{lnN}{n_i}}$$
$$ v_i = \text{ value at state } S_i$$
$$ C = \text{ constant for fine-tuning} $$
$$ N = \text{ total visit counts of the nodes at the same level at } S_i \text{ or visit count of the parent of } S_i $$
$$ n_i = \text{ visit count of node } S_i $$

> If selected node is new/ $n_i = 0$, make simulation skipping expansion

> If selected node is not new/ $n_i > 0$, make expansion and then simulation on expanded node

#### Worked out example

<img style="image-orientation:from-image;" src="{{site.url}}/{{site.baseurl}}/assets/mcts/mcts1.jpg">
<img style="image-orientation:from-image;" src="{{site.url}}/{{site.baseurl}}/assets/mcts/mcts2.jpg">

#### MCTS: Advanteages
- **Aheuristic:** Does not require any domain knowledge apart from game rules and condition. So transferable to another game. 
- **Asymmetric:** MCTS visits more interesting nodes more often. Focuses on relevant part of the game.
- **Anytime:** Possible to stop the game anytime and return current best estimate.
- **Elegant:** Not complex and easy ro implement

#### MCTS: Disadvanteages
- **Playing trength:** In basic form, MCTS can fail to converge
- **Speed:** May take many moves to converge

#### MCTS: Improvements

- **Domain Knowledge:** Domain knowledge can be integrated to produce more sophisticated result
- **Domain Independent:** GEnerality can be maintained and focus on general algorithm development