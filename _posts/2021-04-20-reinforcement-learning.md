- A reward $R_t$ is a scalar feedback
- It indicates how well agent's doing at step $t$
- Agent tries to maximize cumulative reward

> Goal is to maximize expected cumulitive reward

At each step $t$, the agent
- Receive observation $O_t$
- Execute action $A_t$
- Receive scalar reward $R_t$

The env.
- Receives action $A_t$
- Emits observation $O_{t+1}$
- Emits reward $R_{t+1}$

<b style="background-color:Tomato;">History</b> is what the agent seen so far
$$H_t = A_1, O_1, R_1, A_2, O_2, R_2,\dots, A_t, O_t, R_t$$

<b style="background-color:Tomato;">State</b> is the summary of the information that is used to determine what will happen next.

State is a function of History:
    $$S_t = f(H_t)$$

The <b style="background-color:Tomato;">environment state $S_t^e$</b> is the environment's private representation.
Everything is not relevent to the agent.

The <b style="background-color:Tomato;">agent state</b> $S_t^a$ is the agent’s internal representation.
$$S_t^a = f(H_t)$$

An <b style="background-color:Tomato;">information state/Markov state</b> contains all usefulinformation from the history.

$S_t$ is <b style="background-color:Tomato;">Markov</b> iff
    $$\mathbb{P}\[S_{t+1}\|S_t\] = \mathbb{P}\[S_{t+1}\|S_1,\dots,S_t\]$$ 

### Fully observable eenvironment

Agent sees stage of the agent and state of the environment.

<b>Markov Decision Process(MDP)</b>

$O_t = S_t^a = S_t^e$

### Partially observable environment

*partially observable Markov decision process(POMDP)*


### Components of RL agent
- Policy: agent's behaviour
- Value Function: how good is a state/action
- Model: agent's representation of the environment

### Policy
- agent's behaviour
- map from state to action
- deterministic policy, $a = \pi(s)$
- stochastic policy, $\pi(a\|s) = \mathbb{P}\[A=a\|S=s]$

### Value function
- prediction of expected future reward
$$v_{\pi}(s) = \mathbb{E}_{\pi} \[R_t + \gamma R_{t+1} + \gamma^2 R_{t+2} \| S_t=s \]  $$

### Model
- predict what environment do next
    - transition model: predicts the next state $\mathcal{P}_{SS'}^a = \mathbb{P}\[S' = s' \| S = s, A = a\]$
    - Reward model: predicts the next reward $\mathcal{R}_s^a = \mathbb{E} \[R \| S=s, A=a\]$

### Actor critique
Intermediate to policy and value function


## Lecture 2

Adding more and more complexity:
- Markov process
- Markov reward process
- Markov decision process
- Extensions to MDP

##### Intro to MDP
- Formally describe an environment for RL
- Env is fully observable

> A state $S_t$ is *Markov* iff: $\mathbb{P}\[S_{t+1}\|S_t\] = \mathbb{P}\[S_{t+1}\|S_1,\dots,S_t\]$

##### State Transition Matrix
For a Markov state $s$ and successor state $s'$, the state transition probability is defined by:
$$\mathcal{P}_{SS'} = \mathbb{P}\[S_{t+1} =s'\|S_t = s\]

State Transition matrix:

$$\mathcal{P} =
\begin{bmatrix}
\mathcal{P}_{11} & \dots & \mathcal{P}_{1n}\\
\vdots &\ddots& \vdots\\
\mathcal{P}_{n1} & \dots & \mathcal{P}_{nn}\\
\end{bmatrix}
$$

**$S$ is the finite set of states**

**$\mathcal{P}$ is the transition matrix**

### Markov Reward Process
A tuple $<\mathcal{S, P, R, \gamma}>$
- $\mathcal{S}$: finite set of states
- $\mathcal{P}$: transition probability, $\mathcal{P}\_{SS'} = \mathbb{P}[S_{t+1}=s'\|S_t = s]$
- $\mathcal{R}$: reward function $R_s = \mathbb{E}\[R_{t+1}\|S_t = s\]$
- $\gamma$: discount factor $\gamma \in (0,1)$

*The return $G_t$ is the total discounted reward at time-step $t$:*
$$G_t = R_{t+1} + \gamma R_{t+2} + \gamma^2 R_{t+3} + \dots = \sum_{k=t}^\infty \gamma^k R_{t+k+1}$$

$V(s)$ gives the long term value of state $s$:

$$v(s) = \mathbb{E}\[G_t\|S_t = s\]$$

#### Bellman Eqn
$$ v(s) = \mathbb{E}\[ R_{t+1} + \gamma v(S_{t+1}) \| S_t = s \] $$

In matrix notation:
$$ v = \mathcal{R} + \gamma \mathcal{P}v $$

This can be solved directly,

$$ v = \mathcal{R} + \gamma \mathcal{P}v $$
$$ (I - \gamma \mathcal{P})v = \mathcal{R} $$
$$ v = (I - \gamma \mathcal{P})^{-1}\mathcal{R} $$

### Markov Decision Process
Adding one more component, action $A$, to the Markov Reward Process: $A$ is a finite set of actions.

A tuple $<\mathcal{S, A, P, R, \gamma}>$

- $\mathcal{P}\_{ss'}^a = \mathbb{P} (S_{t+1}=s'\| S_t = s, A_t = a)$
- Reward function, $\mathcal{R}\_s^a = \mathbb{E}\[  R_{t+1} \| S_t = s, A_t = a  \] $