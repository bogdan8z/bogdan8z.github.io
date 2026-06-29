# docker redis local setup

>docker run -d --name redis-stack-server -p 6379:6379 redis/redis-stack-server:latest
  
  
  >docker exec -it redis-stack-server bash
  
  >redis-cli
  
	>ping
	
  >SET mykey "Hello\nWorld"
	
  >GET mykey
