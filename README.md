# Container-Orchatration-Automation


## Objective
1. Creating Kubernetes deployment files and a HELM chart for a MERN (MongoDB, Express.js, React.js, Node.js) based application.
2. Write Jenkins Groovy code to automate the build and deployment process, ensuring consistency and efficiency in your CI/CD pipeline.


## Concepts/Technology/Tool Covered
1. Kubenetes
2. Helm
3. Docker
4. Git & Github
5. Jenkins

## Steps

#### Setting up Database first
1. Apply the kubernetes files placed inside [Database](./databaseMongoDB/) in the folowing sequence as mentioned.
```
kubectl apply -f namespace.yml
kubectl apply -f pvc.yml
kubectl apply -f pv.yml
kubectl apply -f deployment.yml
kubectl apply -f service.yml
```
2. Check the pod is in running state with the command `kubectl get pods -n db-app` else wait until it's in running state.

_note:- might take few minutes_

3. You can check you mongo is up and running with the command `minikube service db-service -n db-app`. This will launch mongodb and minkube will take care for tunneling.

_everytime we run the application the port will be different for real world scenario we can use step 4 for this_

4. As the service is up and running inside the pod we need to access it through outside world, which can be done with the command `kubectl port-forward service/db-service 30005:27017 -n db-app`

#### _Setting up Backend_
1. 

#### _Setting up Frontend_


## References & Links


## Happy Coding
Thanks for continuing till the End. :)