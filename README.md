# An Environment for applying Reinforcement Learning to train a Predictive Maintenance Agent for Milling Machine Tools

Reinforcement Learning (RL) is a biologically inspired, autonomous machine learning method. RL algorithms can help generate optimal predictive maintenance (PdM) policies for complex industrial systems. 

Milling machines are highly versatile, ubiquitous machines serving a variety of industries. A milling machine removes metal from the work piece by rotating and driving a cutting device into it. Abrasive forces cause tool wear, and optimal tool replacement reduces direct costs and optimizes the machines' downtime. The cutting tool experiences multiple types of wear as it cuts through metal. Tool wear depends on several factors such as the cutting speed, force applied to the tool, lubrication and materials of the work piece and cutting tool. 

Reinforcement learning (RL) is an artificial intelligence technique inspired by nature. Of all the foundational machine learning (ML) methods, RL is the closest method of learning as seen in animals and humans. Biological learning systems use the learning feedback loop, Fig. \ref{fig_RL-loop}, that inspired core RL algorithms, \cite{barto2018}.
	
	An actor or ``agent'' interacts with an environment and learns via ``trial-and-error''. It acts based on stimuli or feedback received from the environment after performing a certain action. Actions that help in achieving the learning goal receive a reward while actions that do not, are punished. Repeating this loop over thousands of episodes ``reinforces'' good actions thereby building a ``policy'' that is optimized for that goal. In the case of predictive maintenance for milling machines, the agent is the ``planner'' with a goal of learning an optimal tool replacement policy. The environment is technically anything other than the agent -- sensors attached to the machine, job specifications, ambient conditions etc.


to train a Predictive Maintenance Agent for Milling Machine Tools

RL requires an environment to function. We have built a custom environment, using OpenGym standards, for researchers to train their RL agents, to learn a policy for tool replacement. 

Study of noise in RL settings is of prime importance, as suggested by} \cite{Eimer2023AutoRL}. Fig. \ref{fig_noise} shows the effect of adding two levels of noise; a ``low'' level by adding Gaussian noise of order $-3$, $(0.0, 0.001]$ and ``high'' of order $-2$, $(0.0, 0.01]$. Since the tool wear is less than 0.24 mm, this adds significant perturbations as seen in Fig. \ref{fig_LBD} and \ref{fig_HBD}. The noise affects the tool replacement decision (solid blue line) around the replacement threshold (dotted red line). The \textit{human} preventive maintenance policy replaces the tool if the wear exceeds the threshold and this decision boundary oscillates due to the noise. One can see that in the case of no noise (Fig. \ref{fig_NBD}), the decision boundary is clean.
