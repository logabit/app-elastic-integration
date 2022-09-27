# Elastic Integration for PIPEFORCE

This app connects PIPEFORCE with Elastic Cloud or a Elasticsearch server in 3 simple steps.

There is no need to install any of the tools from the Elastic stack like Logstash, Filebeat, Elastic Agent or similar.

## Preconditions

You have your own PIPEFORCE instance installed and running, or you have a PIPEFORCE Cloud account
at https://pipeforce.io.

You have your own Elasticsearch server up and running, or you have an Elastic Cloud account at https://www.elastic.co.

## Setup

1. Open your PIPEFORCE Portal and go to **Marketplace**. Search for this app there and click **Install**.
2. Create a new **Secret** of format `bearer` and with name `elastic-token` and copy and paste the bearer token of your
   elastic documents API endpoint into the secret field (see your Elastic documentation for details about this token).
   Click **ADD**.
3. Copy the url of your document indexing API endpoint from your Elastic installation. Go to Workbench and open
   global/app/elastic-integration/pipeline/shovel-logs and paste the url there. Click SAVE.

Done. From now on, any of your microservices in PIPEFORCE will send its logs automatically into your Elasticsearch
server for indexing.
