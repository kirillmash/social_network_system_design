# Info
- Posts, comments and messages store in postgresql db
- Images store in s3
- For storing posts will use sharding by user_id
- For storing images will use sharding by post_id
- For storing comments will use sharding by post_id
- For all storages will use async master-slave replication with replication factor 2
- In total for sharding and replication  we will have 20 hosts with 1TB hdd, 170 hosts with 40TB ssd and 2 host with 500GB hdd
