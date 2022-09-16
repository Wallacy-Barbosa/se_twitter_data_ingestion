## Data Engineer SE Case - Twitter


### Initial settings

###
#### Step 1: Run the command:
    sh start.sh
** It may take a few minutes the first time as it will prepare all images.

###
#### Step 2: Run the command:
    docker-compose ps

** Wait until all containers are healthy in the status column.
It may take 10 or 15 minutes. </br>
** Don't worry about unhealthy containers, it means the container is still starting.

###
#### Step 3: Log in on Airflow:
url: http://localhost:8080/ </br>
user: airflow </br>
password: airflow

###
#### Step 4: Create Connections on Airflow

    Conn Id: hive_conn
    Conn Type: Hive Server 2 Thrift
    Host: hive-server
    Login: hive
    Password: hive
    Port: 10000

###
#### Step 5: Turn on dag se_twitter_data_ingestion </br>

###
#### Step 6: Trigger Dag (if not already triggered)

###
#### Step 7: Log In to Hive and create or user:
    
    url: http://localhost:32762/
    user: [your name]
    password: [your name]

** Close tips that will appear after you create your login

###
#### Step 8: After the DAG ends, select tables on hive:

    select * from tb_raw_twitter_tweets;
    select * from tb_business_twitter_tweets;

** These tables are partitioned by hashtag

###
#### Final Step: To delete all containers, network and images, run the command bellow:

    sh reset.sh
