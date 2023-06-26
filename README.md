# DeployFlaskAppwithRedis

Flask -> Framework to create webapp in python</br>
Redis -> Open source in memory data structure to store data as db, cache or message broker</br>

A flask app with redis typically involves redis to store and retrieve the data in the backend of flask web application.</br>

In K8S AWS Machine:</br>

mkdir redis_flask                         #Make a directory</br>
cd redis_flask</br>

vi app.py                                 #Create Python project using flask</br>

Create dockerfile --->  Image ---> Containers in Deployment --> Services</br>
vi Dockerfile                             #without any extention</br>
vi requirements.txt</br>

docker build -t flask-image .             #create docker image</br>
docker tag flask-image:latest akshu20791/flask-image:flask-image-for-redis        #tag the image</br>
docker login</br>
Enter username and password</br>
docker images                             #list the images</br>
docker push akshu20791/flask-image:flask-image-for-redis</br>

vi redis.yaml</br>
vi flask.yaml</br>
vi redis-svc.yaml</br>
vi flask-svc.yaml</br>

kubectl create -f redis.yaml</br>
kubectl create -f flask.yaml</br>
kubectl create -f redis-svc.yaml</br>
kubectl create -f flask-svc.yaml</br>
kubectl get svc</br>
NAME  TYPE  CLUSTER-IP  EXTERNAL-IP  PORT(s)  AGE</br>
flask        10.109.126.104           5000/TCP</br>

curl 10.109.126.104:5000</br>
This is the IP of AWS EC2 which is now disabled

