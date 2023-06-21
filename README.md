# DeployFlaskAppwithRedis

Flask -> Framework to create webapp in python
Redis -> Open source in memory data structure to store data as db, cache or message broker

A flask app with redis typically involves redis to store and retrieve the data in the backend of flask web application.

In K8S AWS Machine:

mkdir redis_flask                         #Make a directory
cd redis_flask

vi app.py                                 #Create Python project using flask

Create dockerfile --->  Image ---> Containers in Deployment --> Services
vi Dockerfile                             #without any extention
vi requirements.txt

docker build -t flask-image .             #create docker image
docker tag flask-image:latest akshu20791/flask-image:flask-image-for-redis        #tag the image
docker login
Enter username and password
docker images                             #list the images
docker push akshu20791/flask-image:flask-image-for-redis

vi redis.yaml
vi flask.yaml
vi redis-svc.yaml
vi flask-svc.yaml

kubectl create -f redis.yaml
kubectl create -f flask.yaml
kubectl create -f redis-svc.yaml
kubectl create -f flask-svc.yaml
kubectl get svc
NAME  TYPE  CLUSTER-IP  EXTERNAL-IP  PORT(s)  AGE
flask        10.109.126.104           5000/TCP

curl 10.109.126.104:5000

