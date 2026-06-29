# Dynamodb locally

install admin:
>npm install -g dynamodb-admin

CLIENT:
>docker run -p 8000:8000 amazon/dynamodb-local

ADMIN:
>set DYNAMO_ENDPOINT=http://192.168.99.100:8000
>dynamodb-admin
NOW you can open http://localhost:8001



read more:
https://medium.com/swlh/a-gui-for-local-dynamodb-dynamodb-admin-b16998323f8e
