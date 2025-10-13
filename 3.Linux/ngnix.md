aseenbled page and displayed for user
serve web pages to client browser

add a few more servers
ngnix acts as a load balancing
proxy server = forwards client requests to other servers
1. web server
2. proxy server


what else does proxy: 1. load balancing, 2. caching, 3. security, 4. scripting
- fetching data for every request is slow so we cache 
- we dont expose all servers on public internet
- only one server that is public, it becomes the entrypoint

send the request encrypted. the server decrypts itself. 
netflix uses nginx 
it can compress the data when receiving. 


ssl trafic????
web vs proxy server
port to listen 
port 80 and http is not secure... we need https

can add it on kubernetes. on containers

ingress controller -> proxy for kubernetes 


ngnix + 