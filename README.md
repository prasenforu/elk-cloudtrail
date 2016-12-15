# elk_v_5
ELK v5 stack for CloudTrail logs (Amazon Web Services API calls)

Docker images:

	Kibana: 		latest version, Official
	Elasticsear: 	latest version, Official + Data on EFS
	Logstash:		Modified version, cloudtrail codec plugin installed, image uploaded to private ECR

Amazon Elastic File system is used, mounted to:

	 ECS Cluster node (EC2): /opt/efs/elasticsearch_data
		|_Elasticsearch container: /usr/share/elasticsearch/data	#to save Elasticsearch data
	 ECS Cluster node (EC2): /opt/efs/logstash_data
		|_Logstash container: /usr/share/logstash/data 				#to save "sincedb" file with date of last s3 read by s3 logstash plugin
      
