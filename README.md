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
