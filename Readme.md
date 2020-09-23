Create AutoScaling Group
- Use the ib_cf.yaml file to create the autoscaling group using cloudformation. It is a asg config plus extended scaling policies. Scaling up if CPU Utilisation > 90% and Scaling down if CPU Utilisation < 70% for more than 10 minutes

Handling Traffic Spike
- Using AWS Auto Scaling service to scale our ASG. Choose 'Optimize for availability' scaling strategy and enable both 'Enable predictive scaling' and 'Enable dynamic scaling'

Redis Cluster via ElastiCache as central PHP Session storage for the AutoScalingGroup above
- Create a redis cluster via ElastiCache in cluster mode and note down the cluster endpoint. [Refer this](https://www.brandonchecketts.com/archives/php-sessions-with-redis-cluster-using-aws-elasticache)
- Assuming my PHP server is running in the ASG created above, then while setting it up, I'll include the redis cluster info in the userdata to setup the PHP server properly
