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


Day 4: 

- Decided to dive into hands-on learning with OpenMined courses. Finished the first lesson(Federated Learning), explored Duet basics and gained insights into federated learning with PySyft and working with multiple data owners.
- Course link:
	- https://courses.openmined.org/courses/foundations-of-private-computation



