


To setup the demo environment you need:

1. Kafka
   - this is a distributed streaming platform, acting as our message bus for all the events
2. Filebeat
   - this will watch systemd applications such as httpd and nginx
3. Mattermost
   - Acting as our outside ITSM / Chat Application
   - We need a TOKEN to communicate to Mattermost
4. httpd
   - this is our web application on the