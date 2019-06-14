In this project several novel tecniques were tested on several datasets to predict next Time Series.

- Variant A: Train on 2600 rows, test on last 70 days for TRMF (novel method from Sk) and theta (M4)
- Variant B (Cloud Computing Provider/CDnow): 
    1. Take clusters -> split dataset based on given clusters (around 2000 clusters) -> train on (all-70), test on (70) 
    2. Train classifier to predict clusters, train on given 2000 clusters.
    3. Predict clusters for addtional 600/2000/5000/... rows
    4. Train again and test using given additional generated clusters for rows
- Clusterwise Regression (Electronics manufacturer/M4):
    1. Take clusters.
    2. Fit models on each of them
    3. Calculate training error for clusters (Each cluster has its own training error) 
    4. Take observation x from cluster a, where error_x > error_a
    5. Move observation x to the cluster with the lowest training error
    6. Train again all clusters where there were changes
    7. Stop when error didn't improve several times
    8. Do the test on final setting
 
https://docs.google.com/document/d/1WbWhuo2dEpGf9a7NiyHRcz_wTnI-WXKYDAXUj65VxII/edit
             
             
### Clusters
The clusters were generated on methods from corresponding paper
- GMM_Pair
- GMM_Vote


### Papers 
- Topological Clusterwise Ensemble with Matrix Completion Methods for Demand Forecasting
- Topology-based Clusterwise Regression for User Segmentation and Demand Forecasting
