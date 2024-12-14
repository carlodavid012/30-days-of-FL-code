# 30DaysOfFLCode


This repository contains my progress for #30DaysOfFLCode challenge to commit 30 days of learning, and building Federated Learning, and other Privacy Enhancing Technologies (PETs) skills.


#### Day 1:

- Watched lecture on Privacy Preserving AI MIT Deep Learning Series
- Lecture notes summary:
	- Is it possible to answer questions using data we cannot see?
		- getting access to private data(cancer, dementia, depression etc.) is HARD 
	- Tools to answer questions using data we cannot see
		- Tool 1: Remote Execution
			- perform remote computation without getting direct access to other people's machine
			- Pros:
				- RPC: data remains on remote machine
			- Cons:
				- how can do do good data science without looking at the data?
		- Tool 2: Search and example data 
			- private search and the ability to look at sample data to do sort of things like feature engineering etc.
			- Pros:
				- we can feature engineer with sample data
			- Cons:
				- we can steal data, e.g. PointerTensor.get()
		- Tool 3: Differential Privacy
			- enables to do statistical analysis without compromising the privacy of the dataset
				- allows us to query a database while making certain guarantee about the privacy of other records contained in the database
				- epsilon: privacy budget, upper bound amount of statistical uniqueness allowed in database 
			- Pros:
				- formal, rigorous privacy budgeting
			- Cons:
				- the data is safe, but the model is put at risk!
				- what if we need to do a join/computation across multiple data owners?
		- Tool 4: Secure Multi-Party Computation
			- multiple people can combine their private inputs to compute a function, without revealing their inputs to each other
				- Encryption: neither knows the hidden value
				- Shared Governance: the number can only be used if everyone agrees
			- Models and datasets are just large collections of numbers which we can encrypt
			- Pros:
				- model can be encrypted during training
				- can do joins / functions across data owners
		- Federated Learning (FL)
			- two forms of federated learning:
				- on device federated learning
					- remote execution, example is smartphone keyboard when predicting the next word
				-  centralized federated learning with encrypted data/models
					- both the model and the dataset are encrypted, ensuring accuracy is maintained and sensitive data is protected while still enabling collaboration across distributed data sources.
      - FL trains models on decentralized data but is not inherently secure, as models can memorize and potentially expose sensitive information.
          - needs to combine with differential privacy or other techniques
       
#### Day 2:

I came across with CS-E4740 - Federated Learning. Watched the first two lectures(introduction and ML basics Part I). 

Notes:
- Foundations of ML for FL
	- reviewed key concepts like features, labels, models, loss functions, and Empirical Risk Minimization (ERM), which is essential for building ML models in federated setups.
	- learned how data choices affect ML performance, using FMI weather data (features: station name, location, timestamp; label: max temperature) as an example.
	- learned how ERM minimizes average loss, with gradient descent solving optimization problems like squared error in linear regression.
	- reviewed how validation sets help detect overfitting/underfitting, using training/validation error comparisons and regularization techniques to improve performance.

Lecture videos: https://youtube.com/playlist?list=PLrbn2dGrLJK9TwK1TILxluPApQCLq1Tf5&feature=shared

Github repo: https://github.com/alexjungaalto/FederatedLearning


#### Day 3:

Continued with lecture 3(FL Design Principle) of CS-E4740 - Federated Learning.

Notes:

- Federated Learning:
	- In machine learning, the basic setting involves collecting data points into a feature matrix (X) and a label vector (Y) to learn a linear model parameterized by a weight vector.
 	- Instead of a single dataset, federated learning deals with multiple local datasets, each with its own feature matrix and label vector.
- Important Applications
	- Healthcare: Hospitals can train models using local datasets without sharing raw patient data.
	- Meteorology: Weather stations use distributed data from various locations, leveraging federated learning for localized forecasting.
	- Internet of Things (IoT): Devices like cars with sensors can train models based on local data without centralizing sensitive information.
	- Finance: Financial institutions can collaboratively learn models to detect fraudulent activities without sharing customer data.
- Data Structure and Model Training
	- each local dataset corresponds to a node, and local models are trained separately, enhancing privacy and personalization.
 	- the goal is to create normalized models while maintaining individual data privacy.
- Graph Representation in Federated Learning
	- empirical graph consists of nodes (local datasets) and edges (connections which can reflect relationships between datasets)
	- connection strength between nodes should reflect the statistics of the datasets—similar distributions justify stronger connections
- Total Variation Minimization
	- measures the change in model parameters; minimizing this variation leads to models that generalize better while maintaining individual node characteristics.
	- during federated learning, we want to minimize the total variation of model parameters across edges.
	- strong coupling between model parameters of similar datasets prevents overfitting to individual datasets.
- Generalized Total Variation Minimization (GTVMin)
	- focuses on optimizing model parameters across distributed datasets while maintaining privacy and individuality of the data.


#### Day 4: 

- Decided to dive into hands-on learning with OpenMined courses. Finished the first lesson(Federated Learning), explored Duet basics and gained insights into federated learning with PySyft and working with multiple data owners.
- Course link:
	- https://courses.openmined.org/courses/foundations-of-private-computation

#### Day 5: 
- Continued the OpenMined course, started lessons on Split Learning. Learned how to split models across machines for privacy, trained Split Neural Networks using PySyft, and tackled exercises like building Multi-limb SplitNNs on MNIST.

#### Day 6: 
- Continued OpenMined course on lesson about cryptographic ciphers. Learned about encryption and ciphers basics, encoding and decoding with Shift Cipher, its history, and how secret keys ensure secure communication. Also explored the notebook on attacks on ciphers.


#### Day 7: 
- Continued with cryptographic ciphers lectures. Learned about Monoalphabetic and Vigenère Ciphers, worked through exercises on attacking Monoalphabetic Ciphers to understand encryption vulnerabilities.


#### Day 8: 
- Finished the chapter on cryptographic cipher. Learned about One-Time Padding and its challenges, explored the risks of ciphers with short keys, the importance of using long keys, and why One-Time Padding can fail in practice.


#### Day 9: 
- Started the next lesson(openmined course) on modular algebra which is a mathematical foundation of cryptography. Reviewed concepts on modular algebra and prime numbers, and explored topics such as modular sums, cyclic and multiplicative groups, GCDs, and the Euclidean Algorithm.


#### Day 10: 
- Continued openmined course on modular algebra, Reviewed topics on multiplicative inverses, (groups, rings, fields), and prime numbers. Also explored primality testing, Miller-Rabin test, Mersenne primes, and composite factorization. Next, i'll focus on practical cryptography.

#### Day 11:
- Decided to focus more on hands on tutorials/books. Came across with the book Privacy preserving machine learning(https://www.manning.com/books/privacy-preserving-machine-learning).

- Finished reading the chapter 1 which tackles Privacy  complications in the AI era, and the threat of learning beyond the intended purpose.
- Explored threats and attacks for ML systems(e.g. De-anonymization, Reconstruction attacks, Parameter inference
attacks, Model inversion attacks, Membership inference attacks).
- Also reviewed on differential privacy (DP) which attempts to protect an individual’s sensitive information from any inference attacks targeting the statistics or aggregated data of the individual.

#### Day 12:

- Continued reading the book Privacy preserving machine learning(https://manning.com/books/privacy-preserving-machine-learning……). 

Finished reading chapter on differential privacy and learned how DP works. It protects individual data by adding random noise to results before sharing them. This noise ensures that small changes in the data, like adding or removing one person’s information, don’t noticeably affect the results. 

I also learned about sensitivity and privacy budget, to be able to know how much noise should be added for each DP application. Sensitivity measures the impact one individual’s data could have on the result, helping decide how much noise to add for protection, while privacy budget sets how much deviation is allowed, balancing privacy and data usefulness. 

Then i learned some of the most popular mechanisms in DP namely:  

1. Binary Mechanism (Randomized Response): 
Adds uncertainty by introducing randomness to individual answers, like flipping a coin to decide whether to submit the true or a random response. It protects privacy while preserving overall data accuracy, making it ideal for surveys.  
2. Laplace Mechanism: Adds noise drawn from a Laplace distribution to numerical query results (e.g., counts or averages). The amount of noise depends on the query's sensitivity (max impact of one individual’s data) and the privacy budget, balancing utility and privacy.  
3. Exponential Mechanism: Designed for scenarios with categorical or discrete outputs, where adding direct noise would make results meaningless (e.g., choosing an optimal auction bid). It selects the best response using a utility function and applies probability proportional to the function's score.

#### Day 13:

Learned about approaches in applying differential privacy in machine learning. Here are my notes:

- Input perturbation: add noise to the clean
private data
- Algorithm perturbation: add noise to the intermediate
values in each iteration while training the ML models
- Objective perturbation: add noise to the objective
loss function of the ML models
- Output perturbation: add noise to the output of the ML algorithm

Here are examples of differentially private ML algorithms:

Linear Regression:
- we aim to find the best-fit line or plane that minimizes the difference (residuals) between the observed data and the predicted values. For differentially private linear regression, an input perturbation strategy can be used, where noise is added to the dataset itself to obscure the contribution of individual data points

K-means
- an algorithm perturbation strategy is used by adding Laplace noise to the intermediate centroids and cluster sizes during the iterative updates of the Lloyd algorithm. This approach (known as DPLloyd) ensures privacy while maintaining the utility of the clustering process

Logistic Regression: 
- uses a perturbation strategy by adding noise to the objective function, such as applying the vector mechanism to perturb the loss function of the logistic regression model

Naive Bayes Classification
- we apply output perturbation strategy, where the sensitivity of the naive Bayes model parameters is derived and the Laplace mechanism (Laplacian noise) is then directly applied to the model parameters



#### Day 14:

Learned about local differential privacy (LDP) and its applications. Here are my notes:

Local Differential Privacy (LDP)
- Ensures privacy without relying on a trusted data curator by having individuals perturb their data locally before sharing it with a data aggregator. 

Difference Between Local DP and Normal DP:

Normal DP:
- Relies on a trusted data curator to collect raw data and apply differential privacy mechanisms (e.g., noise addition) before publishing aggregated statistics or models.
Local DP:
- Does not require a trusted curator. Individuals perturb their data themselves before sharing, ensuring privacy even if the aggregator is untrusted.

Real-World Use Cases:
- Google’s RAPPOR: Gathers browser statistics while preserving user anonymity. 
- Apple’s Count Mean Sketch: Obscures trends like emoji usage and web activity to protect user privacy.

Key LDP Mechanisms:
- Randomized response and other noise-adding techniques are used to obfuscate individual data while maintaining useful aggregate insights
- Controlled by the privacy budget (epsilon), balancing privacy and data utility

Encoding mechanism:
- Direct Encoding:  
Maps categorical values to a predefined domain and applies noise for LDP, suitable for multiple-choice problems.

- Histogram Encoding: 
Encodes numerical/continuous values as vectors and adds noise.
          - SHE(Summation with Histogram Encoding): calculates the sum of all values
reported by individuals.
          - THE (Thresholding with Histogram Encoding): applies a threshold to reduce noise variance, improving estimation accuracy

- Unary Encoding: 
is a more general and efficient LDP mechanism for categorical and discrete problems


#### Day 15: 

Had a great time with Openmined First "Show & Tell" Session, where we got the opportunity to learn from other members FL projects. 

First session is an introductory FL computation on SyftBox by Ionesio Junior, then an exciting e-voting project by Lucas Lopes.


#### Day 16: 

Came across with a great course on differential privacy: CS 860 - Algorithms for Private Data Analysis(http://gautamkamath.com/CS860-fa2020.html) by Gautam Kamath. 

Finished the first lecture 1A, which discuss some attempts or failures at Data Privacy. It turns out privacy is really hard and a lot of people try doing ad hoc things. here are the summary for each attempt:

Example 1: NYC Taxicab Data
In 2014, a dataset of NYC taxi trips from 2013 was released through a FOIL request, containing 19 GB of trip information, including anonymized driver identifiers. However, the MD5-hashed identifiers were reversible, leading to massive privacy violations, such as revealing drivers' incomes and home addresses.

Example 2: Netflix Prize
Netflix's 2006-2009 competition shared anonymized user movie rating data to improve their recommendation system. Researchers later re-identified users by cross-referencing it with IMDb reviews, exposing private viewing habits and leading to a class-action lawsuit and cancellation of future competitions.



#### Day 17: #30DaysOfFLCode 

Continued with the course CS 860 - Algorithms for Private Data Analysis. Finished Lecture 1B, which is a continuation on some Attempts at Data Privacy. Traditional anonymization methods are insufficient to ensure data privacy. Further research and advanced methods like differential privacy are critical.

Here are the summary notes on some attempts at privacy:

Example 3: Memorization in Neural Networks
- Neural networks can memorize sensitive training data like social security numbers.
- Exposure is measured using log perplexity, where lower perplexity signals higher memorization likelihood.
- Canary phrases are used to test memorization.
Differential privacy is one of the few effective mitigation techniques.

Example 4: Membership Inference Genomic Studies
- Aggregate statistics in genomic studies can reveal individual participation.
- Example: Homer et al. demonstrated reidentification from DNA mixtures.
- Led to restricted access to genomic datasets and a focus on privacy-preserving methods.

Example 5: Massachusetts Group Insurance Commission
- Anonymized hospital visit records were cross-referenced with voter rolls by Latanya Sweeney.
Reidentified individuals, exposing vulnerabilities in simplistic anonymization techniques.
- k-Anonymity: Ensures individuals are indistinguishable from at least k−1 others based on quasi-identifiers.
- Vulnerable to attacks using external information or overlapping datasets.


#### Day 18: #30DaysOfFLCode 

Continued with course CS 860 - Algorithms for Private Data Analysis. Finished Lecture 2, which discussed what it means for an algorithm to be non private. Also explored vulnerabilities in releasing aggregate statistics and how attackers can reconstruct microdata or compromise privacy. 

Here are the summary notes from today’s study:

Cencus reconstruction
- Aggregate statistics are often released instead of raw data to protect privacy, but these statistics can still reveal sensitive information.
- An example discussed census data with aggregate statistics like age, sex, and race. By analyzing redundancies in these statistics, constraints can be formed on the possible microdata.
- With sufficient constraints, attackers can reconstruct the original microdata, violating privacy.
- A real-world example: In a test of the 2010 US Census data, researchers were able to reconstruct microdata for 46% of the population, enabling large-scale reidentification.
- Such large scale reconstruction attacks were considered to be a red flag, leading to the adoption of differential privacy for disclosure avoidance in the 2020 US census.

Blatant Non-Privacy
- An algorithm is blatantly non-private if an adversary can reconstruct the database matching 99% of entries.

Dinur-Nissim Attack
- demonstrates that even when noise is added to query responses, privacy can still be compromised if the noise is insufficient or if too many queries are allowed.
- The attacker asks many subset queries about the data (e.g., "How many rows satisfy certain conditions?").
The system adds noise to the true answer to "protect" privacy.
- By analyzing the noisy responses, the attacker identifies patterns and eliminates inconsistent possibilities.

Real-World Example:
- In the 2017 Aircloak Challenge, a system called Diffix allowed analysts to run a large number of queries on anonymized data. Researchers used techniques inspired by Dinur-Nissim to reconstruct sensitive data and won a $5,000 bounty for identifying these vulnerabilities.

Takeaway: Even advanced systems can be vulnerable to reconstruction attacks if not adhering to strict privacy protocols like differential privacy.


#### Day 19: #30DaysOfFLCode

Continued with the course CS 860 - Algorithms for Private Data Analysis. 
Finished Lecture 3, which introduces Differential Privacy. Explored the concept of randomized response which is the oldest differentially private algorithm introduce by Warner(1965), which significantly predates the notion of differential privacy. 

Here are summary notes:

Randomized Response
- a technique to protect individual privacy while allowing estimation of aggregate statistics.
- Mechanism:
     - Respond truthfully with probability (0.5 + gamma)
     - Respond with the inverted answer (1 - true value) with probability (0.5 - gamma).
- Key observations:
     - Gamma = 0.5: Perfect accuracy, no privacy.
     - Gamma = 0: Perfect privacy, no accuracy.
     - Values between 0 and 0.5 balance plausible deniability and accuracy.
- Accuracy analysis: The estimator for population proportion has an error bound proportional to 1 divided by (gamma times the square root of the number of participants).

Differential Privacy (DP)
- Ensures that the output of an algorithm does not change significantly with the presence or absence of an individual’s data.
- Formal definition: An algorithm is epsilon-DP if the probability of any event in its output is at most e^epsilon times the probability of the same event when one individual’s data is changed.
- Smaller epsilon means stronger privacy.
- Differential privacy prevents attacks like:
     - Linkage attacks: Re-identifying individuals by combining datasets.
     - Reconstruction attacks: Inferring sensitive details from aggregates.

#### Day 20: #30DaysOfFLCode 

Continued with the course CS 860 - Algorithms for Private Data Analysis. Finished Lecture 4A, which is a review on Laplace mechanism, which is one of the most important algorithm for differential privacy. It builds directly on concepts like sensitivity and improves accuracy compared to randomized response for numeric queries. here are the summary and takeaway notes:

Sensitivity
- Measures how much a function’s output changes when a single individual's data is modified.
- Important for determining how much noise to add for privacy guarantees.
- lecture focused on 1-sensitivity (sum of absolute differences).

Laplace Distribution
- Used for adding noise in this mechanism.
- Compared to Gaussian, it has heavier tails, meaning broader noise.

Laplace Mechanism
- Adds noise proportional to sensitivity to ensure privacy.
- Example: Computing the average of a dataset.Noise added depends on dataset size and privacy level (ε).
More data → less noise needed for the same privacy guarantee.
- Provides better accuracy than randomized response for numeric queries.

Applications
- Counting Queries: adds small noise to count individual attributes; error depends on ε but not dataset size.
- Multiple Queries: noise scales with the number of queries; works in non-adaptive settings.
- Histograms: reduced sensitivity due to structured bins; error grows logarithmically with bin count

Takeaways
- Laplace Mechanism is more accurate than randomized response for large datasets.
- Sensitivity analysis is key to adding just enough noise for privacy.
- Structured queries (like histograms) can use reduced sensitivity for better results.

#### Day 21: #30DaysOfFLCode 

Continued with the course CS 860 - Algorithms for Private Data Analysis. Finished Lecture 4B: Properties of Differential Privacy. Learned about some of the most fundamental properties of DP, namely:

1. Post-Processing
- Once data is privatized, no further analysis can "undo" the privacy guarantee, even if subsequent transformations or computations occur.
- Any computation or transformation on differentially private outputs remains private.
- This property is essential for creating pipelines where private outputs are analyzed without compromising the original privacy guarantee.

2. Group Privacy
- Differential privacy gracefully extends to groups of individuals. When datasets differ by more than one entry, the privacy loss scales linearly with the number of differing entries.
- If datasets differ in multiple entries, the privacy loss increases depending on how many entries differ between datasets.
- This property helps ensure that privacy guarantees hold even when the dataset changes in more complex ways, like when multiple people are added or removed.

3. Basic Composition
- Running multiple differentially private algorithms on the same dataset results in cumulative privacy loss.
- Privacy Loss: When multiple independent mechanisms each guarantee privacy with a given level of protection (denoted as epsilon), the combined mechanism guarantees privacy with the sum of these levels of protection.
- Limitation: The privacy guarantee weakens as the number of queries or mechanisms increases.

#### Day 22: #30DaysOfFLCode

- Attended the second session of OpenMined Show & Tell, where we had the opportunity to learn about different projects from other members and applications of Federated Learning (FL). Learned about interesting and fun projects, including private Data search using Netflix data, learning analytics from a browser history aggregator, and Federated Game of Life.
