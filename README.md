# elk-cloudtrail
<i>ELK v5 stack for CloudTrail logs (Amazon Web Services API calls)</i>

![Alt text](https://github.com/prasenforu/elk-cloudtrail/blob/master/images/elk-cloudtrail.png "Overview") 

Docker images:

	Kibana: 		latest version, Official
	Elasticsearch: 		latest version, Official + Data on EFS
	Logstash:		Modified version, cloudtrail codec plugin installed, create new image (Logstash)

<b>Installation:</b>

1.	git clone https://github.com/prasenforu/elk-cloudtrail.git

2.	Goto folder elk-cloudtrail/logstash/   and edit/change following section as per your configuration

	bucket => <b>"CLOUD_TRAIL_BUCKET_NAME"</b>
	
  	access_key_id => <b>"ACCESS_KEY"</b>
	
  	secret_access_key => <b>"SECRET_ACCESS_KEY"</b>
	
	prefix => "AWSLogs/<b>AMAZON_ACCOUNT_ID</b>/CloudTrail/"

3.	Make executable docker-entrypoint.sh

	chmod 755 docker-entrypoint.sh

4.	Build docker container

	docker build -t logstash5 .

5.	Run Docker Compose form elk_v_5 folder

	docker-compose up -d
	
6. 	View `Kibana` at http://localhost:5601

    	Use the **index pattern** as `logtash-*` and select the **time field** as `@timestamp`

For Stop, shutdown and restart

1. `sudo docker-compose stop` to shutdown all the docker containers.

2. `sudo docker-compose down` to shutdown and remove all the files from docker. 

3. `sudo docker-compose restart` to restart docker container. 


