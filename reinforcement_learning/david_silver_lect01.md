### David Silver Slides #01
* [Original Slides](http://www0.cs.ucl.ac.uk/staff/d.silver/web/Teaching_files/intro_RL.pdf)

----
#### Characteristics of Reinforcement Learning
* No Label/Ground Truth, only reward: *Reward might not be accurate!*
* Feedback is delays: *Should learn the dependency.*
* Sequnecial Data: *Not i.i.d data, the sampling method matters*. **The actions may affect the data distribution.**

----
#### Basic Concepts
* **Reward**: scalar feedback, need to be maximize.
* **Observation**: output from environment.
* **Action**: action performed.
* **History**: $H_t = O_1, R_1, A_1, ..., A_{t-1}, O_t, R_t$
* **State**: $s_t = f(H_t)$, the summary of the history. 
* **Policy**: A conditional distribution over actions given a specific state.
* **Value Function**: Prediction of future reward.
* **Model**:The predictions of the next state, like $\mathbf{P}[S_{t+1}|S_t, a_t]$ and $\mathbf{P}[R_{t+1}|S_t,a_t]$.

----
* **Markov State** $\longleftrightarrow \mathbf{P}[S_{t+1}|S_t]=\mathbf{P}[S_{t+1}|S_1, S_2, ..., S_t]$
* **Fully observability**: Agent state = Environment state = Markov state.
* **Paritally Observability**: Agent state $\neq$ Environment state. *Example: The poker playing agetnt only observeds public cards*. In that case, the agent should construct the state representation with a model like RNN. 

----
#### RL Agents
* Component perspective:
    * Value Based: Only Value Function
    * Policy Based: Only Policy
    * Actor Critic: Both Policy and Value Function
* Model perspective:
    * Model-Free: Policy & Value Function, without model(prediction)
    * Model-Based: Policy & Value Function, with model(prediction)
    ![Different Agents](./Screen Shot 2016-11-27 at 5.27.41 PM.png)

----
#### Fundamental Tasks
    * Learning: improve the policy with unkown environment *Example: Playing Video Game* 
    * Planning: improve the policy given the environment with a known model(state transition matrix). *Example:Searching*

----
#### Methods in RL
* **Exploration** finds more information in the environment while **exploitation** uses more information to maximize the reward: $\epsilon-greedy$.
* **Prediction** is given the policy, how do we evaluate the value while **Control** is to find the best policy to optimise the future. 
