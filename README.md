## Project Description: 

This project is part of a broader use case involving a company that provides Reinforcement Learning from Human Feedback (RLHF) services. RLHF is a technique commonly used to fine-tune Large Language Models (LLMs) by incorporating human feedback to train, evaluate, and enhance the models' safety and usefulness. In this scenario, the company acts as an RLHF service provider, recruiting workers to its platform to carry out RLHF tasks on behalf of its clients.

The purpose of this exercise is to estimate workers' lifetime value. Consider these workers as skilled freelance employees who often work sporadically on projects posted to the platform. Much like more conventional applications of CLTV models, where non-subscription retail customers come and go with no long-term commitments, estimating the long-term value of a worker can be difficult given the uncertainty of future engagement. 

Through this exercise, we aim to garner key insights into: 

**Predicting Future Engagement:** Assess the likelihood of future engagement across the workforce to enable more effective planning and execution of acquisition strategies that align with the platform’s future needs.

**Worker Churn and Re-engagement:** Identify which workers have stopped participating or are at risk of churning. This enables targeted outreach through email, SMS, or digital advertising to encourage their return.

**Worker Prioritization and Segmentation:** Use estimated lifetime value as a key metric to segment and prioritize workers. This allows for more strategic and personalized engagement efforts based on potential long-term contribution.

**Active Worker Output and User Acquisition:** Analyze the expected work output of currently active workers over a given time period. These insights help guide user acquisition strategies, ensuring the platform maintains a sufficient and balanced supply of available workers to meet ongoing demand.


## Methodology: 

Estimating the Lifetime Value of RLHF workers will consist of two primary components: predicting future engagement and estimating future earnings.

### Predicting Worker Engagement: 

To predict the probability of future re-engagement, we will leverage Buy 'til You Die (BTYD) models. These models utilize a worker's recency of last engagement and the frequency of repeat sessions to fit curves describing session frequency distribution and engagement drop-off. We will evaluate and compare two popular models, the **Beta-Geometric/Negative Binomial Distribution (BG/NBD)** and the **Pareto/Negative Binomial Distribution (Pareto/NBD).** For this project, we will be estimating worker sessions in place of customer purchases. 

### Estimating Future Earnings: 

As a complement to our BTYD model, we will develop a **Gamma-Gamma model** to estimate the average monetary value of worker sessions on the platform. The output of this model, when combined with the predicted future session frequency from the BTYD model, will culminate in our worker lifetime value predictions over a future period. In this context, earnings will serve as the proxy for purchase value. Earnings are variable, as they are influenced by task rates (urgency, complexity, and required expertise) and session duration. We assume the business makes a percentage of the total revenue (rate * minutes_worked/60), in which case earnings is a comparable proxy to order value. 


