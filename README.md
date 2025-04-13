## An Environment for applying Reinforcement Learning to train a Predictive Maintenance Agent for Milling Machine Tools
- Author: Rajesh Siraskar
- Date: 11-Apr-2025
- Download the environmment software from: https://doi.org/10.5281/zenodo.15168512
- Environment DOI: 10.5281/zenodo.15168512  

Reinforcement Learning (RL) is a biologically inspired, autonomous machine learning method. RL algorithms can help generate optimal predictive maintenance (PdM) policies for complex industrial systems. 

Milling machines are highly versatile, ubiquitous machines serving a variety of industries. A milling machine removes metal from the work piece by rotating and driving a cutting device into it. Abrasive forces cause tool wear, and optimal tool replacement reduces direct costs and optimizes the machines' downtime. The cutting tool experiences multiple types of wear as it cuts through metal. Tool wear depends on several factors such as the cutting speed, force applied to the tool, lubrication and materials of the work piece and cutting tool. 

RL requires an environment to function. We have built a custom environment, using OpenGym standards, for researchers to train their RL agents, to learn a policy for tool replacement. 

In this article we describe the design of the environment, followed by how to use it.

### Environment Design:

1. The design is based on [OpenGym standards](https://github.com/openai/gym]).
2. Variants possible using parameterized settings
3. Study of noise in RL settings is of prime importance. Noise can be added to the tool-wear measurement. This allows for training robust agents.
4. Variant combination possibility: 
   - Two levels of noise possible using a Gaussian distribution: Low: Order 1e-3 i.e. (0.0, 0.001] and High: Order 1e-2, (0.0, 0.01]. Since the tool wear is less than 0.24 mm, this adds significant perturbations.
   - Chance of break-down: None, low and high probability
5. See sample images below of the variant and the impact on training the RL agent.
   - The noise affects the tool replacement decision (solid blue line) around the replacement threshold (dotted red line).
   - The human preventive maintenance policy replaces the tool if the wear exceeds the threshold and this decision boundary oscillates due to the noise.

#### Variant examples:

**Uni-variate state with no noise or breakdown**:
![Univariate](https://github.com/RajeshSiraskar-PhD/An-environment-for-applying-RL-to-train-a-predictive-maintenance-agent-for-milling-machine-tools/blob/main/PHM-C06.%20Variant%20Univariate%20state%2C%20high-noise%20and%20high%20chance%20of%20breakdown.webp)


**Multi-variate state with no noise or breakdown**:
 ![Multivariate state with no noise or breakdown:](https://github.com/RajeshSiraskar-PhD/An-environment-for-applying-RL-to-train-a-predictive-maintenance-agent-for-milling-machine-tools/blob/main/PHM-C01.%20Variant%20Multivariate%20state%2C%20No%20noise%20or%20breakdown.webp)

