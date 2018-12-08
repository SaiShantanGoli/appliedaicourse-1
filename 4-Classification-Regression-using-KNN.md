
* Classification vs Regression 
* K-Nearest Neighbours Geometric intuition 
* Probabilistic class label
* Failure cases and Limitations 
* How to measure the effectiveness
* Time and space complexity 
* Decision surface for K-NN as K changes 
* k-NN for regression 
* Weighted k-NN
* Voronoi diagram
* KNN using KD-Tree (Binary search tree)
* How to build a kd-tree
* Find nearest neighbours using kd-tree
* Limitations of Kd tree
* Extensions
* Hashing vs LSH
* LSH for cosine similarity 
* LSH for euclidean distance


can KNN be parallelized 


KNN is notoriously hard to parallelize in Spark because KNN is a "lazy learner" and the model itself is the entire dataset. Most single machine implementations rely on KD Trees or Ball Trees to store the entire dataset in the RAM of a single machine. I would recommend using scikit-learn's single machine implementation with a Simple Random Sample of the dataset if you really want to use KNN.
