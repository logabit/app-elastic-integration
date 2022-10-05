# Elastic Integration for PIPEFORCE 

This app connects PIPEFORCE with Elastic Cloud or an Elasticsearch server in 3 simple steps. After installing this app,
you can browse all logs of all microservices and pipelines in Elastic and use Kibana to filter and build dashboards
instantly.

Since PIPEFORCE comes with its own message and logs shovel implementation, there is no need to install and host any of
the tools from the Elastic stack like Logstash, Filebeat, Elastic Agent or similar. Its optional.

For more details about PIPEFORCE messaging and monitoring, refer to
the [Developer Documentation](http://docs.pipeforce.io).

## Preconditions

 - You have your own PIPEFORCE instance installed and running, or you have a PIPEFORCE Cloud account
at https://pipeforce.io. 
 - You have your own Elasticsearch server up and running, or you have an Elastic Cloud account at https://www.elastic.co.

## Setup

1. Open your PIPEFORCE Portal and go to **Marketplace**. Search for this app `app-elastic-integration` there and
   click **Install**.
2. Create a new **Secret** of format `bearer` and with name `elastic-token` and copy and paste the bearer token of your
   elastic documents API endpoint into the secret field (see your Elastic documentation for details from where to get this token).
   Click **ADD**.
3. Copy the url of your document indexing API endpoint from your Elastic installation. Go to Workbench and open
   global/app/elastic-integration/pipeline/shovel-logs and paste the url there. Click SAVE.

Done. From now on, any of your microservices in PIPEFORCE will send its logs automatically into your Elasticsearch
server for indexing and further processing.
