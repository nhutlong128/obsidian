---
cards-deck: Obsidian::Cloud-Computing::AWS ML Specialty
tags: aws-ml-specialty
---
Course Content
# 1. Data Engineering (20%)
##### Storage
- [[S3]]
##### Data Transformation
- [[Glue]]
##### Streaming
- [[Kinesis]]
##### Workflows
- [[Data Pipeline]]
- [[Step Functions]]
##### Batch Job (Clean Up ~ not ETL Job)
- [[Batch]]
# 2.Exploratory Data Analysis (EDA) (24%)
##### Data Science (Data distribution, Trends, Seasonality)
- Type of Data
	- Numerical ~ Quantitative measurement
		- Discrete Data ~ often counts of some event
		- Continuous Data ~ infinite number of possible value
	- Categorical
	- Ordinal ~ Mix of Categorical and Numerical
- Distribution
	- The probability distribution function gives us the probability of a data point falling within given range of a given value
	- Type
		- Probability Density Function (Normal Distribution) ~ continuous data
		- Probability Mass Function (Poisson Distribution, Binomial Distribution, Bernouli Distribution) ~ discrete data
- Time Series
	- Trends ![[Pasted image 20210623212552.png]]
	- Seasonality ![[Pasted image 20210623212609.png]]
	- Both ![[Pasted image 20210623212630.png]]
	- Noise ![[Pasted image 20210623212803.png]]
##### Analysis Tools (Athena, Quicksight, EMR, Spark)
- [[Athena]]
- [[Quicksight]]
- [[EMR]]
##### Feature Engineering (Imputation, Outlier, Binning, Log Transform, One-hot encoding, Scaling and Normalization)
- Imputation
	- Mean Replacement (Median Replacement can be better if outliers are present) => Not use for Category features
	- Dropping (When dont have time) => Not very "best" approach
	- KNN: Find K "nearest" rows and average their values (or Hamming Distance for categorical features)
	- Build ML model to impute data => works well for categorical data
	- Regression: Find linear and non linear relationship between missing features and other features (Ex: MICE ~ Multiple Imputation by Chained Equations)
	- Getting more data :))
- Handling Unbalanced Data
	- Oversampling from the minority class (Random)
	- Undersampling from the majority class (Random) => Not throwing data
	- SMOTE (Both Oversampling and Undersampling)
	- Applying Threshold before making decision
- Handling outliers
	- Variance is the average of squared differences between data points and the mean
	- Standard Deviation is the square root of Variance
	- If data point lie more than 1 Standard Deviation => Unusual
	- If data point lie more than some multiple of Standard Deviation => Outliers
	- Can remove outliers
- Binning
	- Transform numeric data to ordinal data
	- Binning data points together based on ranges of values
- Transforming
	- Applying some function to feature to make it better suited for training
- Encoding
	- Transforming data into new representation that model required (Ex: Word => Number)
	- One-hot encoding
- Scaling / Normalization
	- Some model prefer feature data to be normally distributed around 0 -> Easily converge, comparing features (Features with larger magnitude will have more weight than they should)
- Shuffling
	- Many algorithms benefit from shuffling their training data => Reduce overfit
- [[SageMaker GroundTruth]]
# 3. Modeling (36%)
##### Deep Learning
- Activation Function
	- Linear activation function => Degenerate to a single layer
	- Binary step function (on or off)
	- Sigmoid 0 -> 1
	- Logistic 0 -> 1
	- Tanh -1 -> 1 (preferable than Sigmoid) => do well with RNN
	- ReLU (When inputs are negative or 0 -> Linear Function -> Dying ReLU)![[Pasted image 20210624012209.png]]
	- Leaky ReLU solve dying ReLU![[Pasted image 20210624012153.png]]
	- Parametric ReLU (PReLU)![[Pasted image 20210624012242.png]]
	- Other ReLU variants
		- Swish: benefits with deep layers ~ 40+ layers
	- Softmax![[Pasted image 20210624012343.png]]
- RNN
	- ![[Pasted image 20210624013346.png]]
	- ![[Pasted image 20210624013433.png]]
- Instance type for Deep Learning on [[EC2]], [[EMR]]
	- P3
	- P2
	- G3
- Learning Rate
	- ![[Pasted image 20210624013637.png]]
	- ![[Pasted image 20210624013650.png]]
	- ![[Pasted image 20210624013744.png]]
- Regularization Techniques
	- Use fewer layers
	- Drop Out
	- Early Stopping
- The Vanishing Gradient Problem
	- ![[Pasted image 20210624014749.png]]
	- ![[Pasted image 20210624014801.png]]
	- ![[Pasted image 20210624014819.png]]
- L1 & L2 Regularization
	- ![[Pasted image 20210624015041.png]]
	- ![[Pasted image 20210624015053.png]]
	- ![[Pasted image 20210624015110.png]]
- Metrics
	- Confusion Matrix
	- ROC Curve
	- AUC
	- F1
- Ensemble Learning
		- Bagging
		- Boosting
##### SageMaker (Built-in algorithms, Automatic model tuning)
- [[SageMaker]]
-  Data must come from [[S3]]
- [[SageMaker Built-In Algorithm]]
##### High-Level AI Services (Comprehend, Translate, Polly, Transcribe, Lex, Rekognition, Personalize, Forecast, Textract, DeepLens)

##### Evaluating and Tuning (Confusion Matrix, RMSE, Precision and ReCall, F1 Score, ROC/AUC)

# 4. ML Implementation & Operations (20%)
##### SageMaker Operations (Using Containers, Choosing Instance Type, A/B Testing, SageMaker Neo & Pipes, Elastic Inference and Inference Pipeline)
- Containers
![[Pasted image 20210625220305.png]]
- Production Variants testing new model while using old models
# 5. Questions
### Data Engineering

##### What is the simplest way to manage automating the archiving or deletion of old data in your S3 data lake?
- Write a script that runs periodically using the boto3 API
- Use S3 Lifecycle Rules
- Use S3 bucket policies
- Use S3 partitioning strategies
#card
Use S3 Lifecycle Rules

##### A Kinesis Data Stream's capacity is provisioned by _shards_. What is the maximum throughput of a single shard?
- 100MB/s or 1000 messages/s
- 100MB/s or 100 messages/s
- 1MB/s or 1000 messages/s
#card
1MB/s or 1000 messages/s

##### Which Amazon service is appropriate for connecting video data from cameras to backend systems to analyze that data in real time?
- Rekognition
- SageMaker
- Kinesis Video Streams
- DeepLens
#card 
Kinesis Video Streams

##### What is the underlying platform for Glue ETL?
- A serverless Apache Spark platform
- Redshift
- RDS
- SageMaker
#card 
A serverless Spark platform

##### Which AWS data store provides a highly scalable data warehouse (for OLAP) that can query your S3 data lake directly?
- RDS
- Redshift
- Dyamodb
- ElasticSearch
#card 
Redshift

### EDA
##### Which kind of graph is best suited for visualizing outliers in your training data?
- Pair Plot
- Box and Whisker Plot
- Tree Map
#card 
Box and Whisker Plot

##### What sort of data distribution would be relevant to flipping heads or tails on a coin?
- Binomial Distribution
- Poisson distribution
- Normal Distribution
#card 
Binomial Distribution

##### What is a serverless, fully-managed solution for querying unstructured data in S3?
- Redshift
- RDS
- Athena
#card 
Athena

##### Which of the following is NOT a feature of Amazon Quicksight's Machine Learning Insights?
- Visualization of precision and recall
- Anomaly detection
- Forecasting
- Auto-narratives
#card 
Visualization of precision and recall

##### Which imputation technique for missing data would produce the best results?
- Mean or Median Replacement
- Dropping
- MICE
#card 
MICE

### Modelling

##### Your deep neural network seems to converge on different solutions with different accuracy each time you train it. What's a likely explanation?
- The learning rate is too small
- The batch size is too small
- The batch size is too large
#card 
The batch size is too large. Large batch sizes tend to get stuck, at random, inside "local minima" instead of the correct solution.

##### Your neural network's accuracy on its training data is increasing beyond the accuracy on test or validation data. What might be a valid thing to try to prevent this overfitting?
- Use dropout
- Add more layers to the model
- Implement gradient checking
#card 
Use dropout

##### You're implementing a machine learning model for fraud detection, where most of your training data does not indicate fraud. The cost of a incorrectly identifying an actual fraudulent transaction is much higher than the cost of incorrectly identifying a non-fraudulent transaction. Which metric should you focus on for your model?
- Precision
- Recall
- RMSE
#card 
Recall is appropriate when you care most about false negatives, which in this case is incorrectly identifying fraudulent transactions as non-fraudulent.

##### Where does the training code used by SageMaker come from?
- Jupyter notebooks
- A docker image registered with ECR
- A Github repository
#card 
A docker image registered with ECR. Whether it's your own code, a built-in algorithm from SageMaker, or a model you've purchased in the marketplace - all training code deployed to SageMaker training instances come from ECR.

##### Which SageMaker algorithm would be best suited for identifying topics in text documents in an unsupervised setting?
- BlazingText can predict labels for sentences, but only if you've trained it in a supervised setting. It's not appropriate for working with entire documents
- Object2Vec
- LDA
#card 
LDA

###  ML Implementation

##### Where does SageMaker's automatic scaling get the data it needs to determine how many endpoints you need?
- CloudWatch
- CloudTrail
- EC2
#card 
CloudWatch. CloudWatch is a repository of performance metrics associated with your endpoints, which SageMaker can use to determine if you have the right amount of them.

##### Your SageMaker inference is based on a Tensorflow or MXNet network. You want it to be fast, but don't want to pay for P2 or P3 inference nodes. What's a good solution?
- Use inference pipelines
- Use Elastic Inference
- Use an M4 inference node
#card 
Use Elastic Inference. EI accelerators can be attached to CPU inference instances to accelerate deep learning inference at a fraction of the cost of using a GPU inference node.

##### You are deploying SageMaker inside a VPC, but the Internet access from SageMaker notebooks is considered a security hole. How might you address this?
- Disable internet access when creating the notebook, and set up a NAT gateway to allow the outbound connection needed for training and hosting
- Enable network isolation
- Enable SSL / TLS in SageMaker
#card 
Disable internet access when creating the notebook, and set up a NAT gateway to allow the outbound connection needed for training and hosting. Alternatively, PrivateLink endpoints could be used instead of a NAT Gateway.

##### You want to deploy your trained semantic segmentation model from SageMaker to an embedded ARM device in a car. Which services might you use to accomplish this?
- Lambda and Lex
- SageMaker Neo and IOT GreenGrass
- AWS DeepRacer and Deep Lens
#card 
SageMaker Neo and IOT GreenGrass. Neo can compile your model to an ARM processor, and GreenGrass can get it to the device you want.

##### When constructing your own training container for SageMaker, where should the actual training script files be stored?
- /opt/ml/code
- /opt/ml/model
- /opt/ml/train
#card 
/opt/ml/code. This is where your code should go. The SAGEMAKER_PROGRAM environment variable will indicate the specific script that should be run.

### Practice Test 1

##### You are training an XGBoost model on SageMaker with millions of rows of training data, and you wish to use Apache Spark to pre-process this data at scale. What is the simplest architecture that achieves this?
- Use Amazon EMR to preprocess your data using Spark, and use the same EMR Instances to host your SageMaker notebook
- Use Amazon EMR to preprocess your data using Spark, and then use AWS Data Pipelines to transfer the processed training data to SageMaker
- Use Sparkmagic to preprocess your data within a SageMaker notebook, transform the resulting Spark DataFrames into RecordIO format, and then use Spark XGBoost algorithm to train the model
- Use sagemaker_pyspark and XGBoostSageMakerEstimator to use Spark to pre process, train and host your model using Spark on SageMaker
#card 
Use sagemaker_pyspark and XGBoostSageMakerEstimator to use Spark to pre process, train and host your model using Spark on SageMaker. The SageMakerEstimator classes allow tight integration between Spark and SageMaker for several models including XGBoost, and offers the simplest solution. You can't deploy SageMaker to an EMR cluster, and XGBoost actually requires LibSVM or CSV input, not RecordIO.

##### You are developing a machine learning model to predict house sale prices based on features of a house. 10% of the houses in your training data are missing the number of square feet in the home. Your training data set is not very large. Which technique would allow you to train your model while achieving the highest accuracy?
- Impute the missing values using the mean square footage of all homes
- Impute the missing values using deep learning, based on other features such as number of bedrooms
- Drops all rows that contain missing data
- Impute the missing footage values using KNN
#card 
Impute the missing footage values using KNN. Deep learning is better suited to the imputation of categorical data. Square footage is numerical, which is better served by kNN. While simply dropping rows of missing data or using the mean values are a lot easier, they won't result in the best results.

##### You are developing a computer vision system that can classify every pixel in an image based on its image type, such as people, buildings, roadways, signs, and vehicles. Which SageMaker algorithm would provide you with the best starting point for this problem?
- Rekognition
- Object Detection
- Semantic Segmentation
- Object2Vec
#card 
Semantic Segmentation. Semantic Segmentation produces segmentation masks that identify classifications for each individual pixel in an image. It uses MXNet and the ResNet architecture to do this.

##### A large news website needs to produce personalized recommendations for articles to its readers, by training a machine learning model on a daily basis using historical click data. The influx of this data is fairly constant, except during major elections when traffic to the site spikes considerably. Which system would provide the most cost-effective and simplest solution?
- Publish click data into Amazon S3 using Kinesis Firehose, and process the data nightly using Apache Spark and MLLib using reserved instances in an EMR cluster. Publish the model's results to DynamoDB for producing recommendations in real-time.
- Publish click data into Amazon S3 using Kinesis Streams, and process the data in real time using Splunk on an EMR cluster with spot instances added as needed. Publish the model's results to DynamoDB for producing recommendations in real-time.
- Publish click data into Amazon S3 using Kinesis Firehose, and process the data nightly using Apache Spark and MLLib using spot instances in an EMR cluster. Publish the model's results to DynamoDB for producing recommendations in real-time.
- Publish click data into Amazon Elasticsearch using Kinesis Firehose, and query the Elasticsearch data to produce recommendations in real-time.
#card 
Publish click data into Amazon S3 using Kinesis Streams, and process the data in real time using Splunk on an EMR cluster with spot instances added as needed. Publish the model's results to DynamoDB for producing recommendations in real-time. The use of spot instances in response to anticipated surges in usage is the most cost-effective approach for scaling up an EMR cluster. Kinesis streams is over-engineering because we do not have a real-time streaming requirement. Elasticsearch doesn't make sense because Elasticsearch is not a recommender engine.

### Practice Test 2 
Link: https://tyme.udemy.com/course/aws-certified-machine-learning-specialty-full-practice-exams/
Name: Mini Practice

### Practice Test 3
Link: https://tyme.udemy.com/course/aws-certified-machine-learning-specialty-full-practice-exams/
Name: Test 1

### Practice Test 4
Link: https://tyme.udemy.com/course/aws-certified-machine-learning-specialty-full-practice-exams/
Name: Test 2

### Practice Test 5
Link: https://tyme.udemy.com/course/aws-machine-learning-practice-exam/
Name: Quick Test

### Practice Test 6
Link: https://tyme.udemy.com/course/aws-machine-learning-practice-exam/
Name: Test 1

### Practice Test 7
Link: https://www.examtopics.com/exams/amazon/aws-certified-machine-learning-specialty/
Name: Amazon AWS Certified Machine Learning - Specialty Exam