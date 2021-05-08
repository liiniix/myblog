<iframe width="560" height="315" src="https://www.youtube.com/embed/O5hkIfUR_uA" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

### State Machine
$$S = \text{Set of states}$$
$$X = \text{Set of possible inputs}$$
$$s_0 \in S : \text{initial state}$$
$$f: S \times X \to  S: \text{transition function}$$
$$Y = \text{set of possible outputs}$$
$$g: S \to Y: \text{output function}$$

### Markov Decision Process
$$S = \text{Set of states}$$
$$A = \text{Set of possible actions}$$
$$T:S\times A \times S \to \mathbb{R} \text{ transition model}$$
$$R : S \times A \to \mathbb{R} \text{ Reward function}$$
$$\text{A discount factor}$$
$$\pi: S \to A: \text{ policy}$$

![]({{site.url}}/{{site.baseurl}}/assets/state_machine/mdp.jpg)

### What is the value of policy?

$$h: \text{ horizon, how many seasons left?}$$
$$V_\pi^h(s): \text{ expected reward with policy $\pi$ starting at $s$}$$
$$V_\pi^h(s) = R(s, \pi(s)) + \sum_{s'} T(s, \pi(s), s')R_\pi^{h-1}(s')$$
$$V_\pi(s) = R(s, \pi(s)) + \gamma \sum_{s'} T(s, \pi(s), s')R_\pi(s')$$
$$Q(a, s) = \text{ first action $a$ at state $a$, optimal action onward, in this case how much reward}$$
$$Q^h(s, a) = R(s, a) + \sum_{s'}T(s, a, s') \max_{a'}Q^{h-1}(s', a')$$