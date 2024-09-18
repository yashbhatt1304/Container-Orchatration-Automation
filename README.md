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

#### **_Setting up Database first_**

1. Apply the kubernetes files placed inside [Database](./databaseMongoDB/) in the folowing sequence as mentioned.
> ```
kubectl apply -f namespace.yml
kubectl apply -f pvc.yml
kubectl apply -f pv.yml
kubectl apply -f deployment.yml
kubectl apply -f service.yml
> ```
2. Check the pod is in running state with the command `kubectl get pods -n db-app` else wait until it's in running state.
> _note:- it might take few minutes._

3. You can check you mongo is up and running with the command `minikube service db-service -n db-app`. This will launch mongodb and minkube will take care for tunneling.
> _note:- Everytime the application is run with above step will create different port. For real world scenario we can use step 4 for this._

4. As the service is up and running inside the pod we need to access it through outside world, which can be done with the command `kubectl port-forward service/db-service 30005:27017 -n db-app`

5. You can check making connection to the DB at 30005 port.
![MongoDB_Connection](./snapshots/MongoDbInCompass.png)

#### **Setting up Backend**

1. Apply the kubernetes files placed inside [Backend](./backend/) in the folowing sequence as mentioned.
> ```
kubectl apply -f namespace.yml
kubectl apply -f secret.yml
kubectl apply -f deployment.yml
kubectl apply -f service.yml
> ```
2. Check the pod is in running state with the command `kubectl get pods -n learner-report-backend` else wait until it's in running state.
> _note:- it might take few minutes._

3. You can check you backend is up and running with the command `minikube service backend-service -n learner-report-backend`. This will launch backend and minkube will take care for tunneling.
> _note:- Everytime the application is run with above step will create different port. For real world scenario we can use step 4 for this._

4. As the service is up and running inside the pod we need to access it through outside world, which can be done with the command `kubectl port-forward service/backend-service 3001:3001 -n learner-report-backend`

5. You can check making connection to the backend at 3001 port.
![Backend_Connection](./snapshots/BackendInBrowser.png)

#### **Setting up Frontend**

1. Apply the kubernetes files placed inside [Frontend](./frontend/) in the folowing sequence as mentioned.
> ```
kubectl apply -f namespace.yml
kubectl apply -f configMap.yml
kubectl apply -f deployment.yml
kubectl apply -f service.yml
> ```
2. Check the pod is in running state with the command `kubectl get pods -n learner-report-frontend` else wait until it's in running state.
> _note:- it might take few minutes._

3. You can check you mongo is up and running with the command `minikube service frontend-service -n learner-report-frontend`. This will launch mongodb and minkube will take care for tunneling.
> _note:- Everytime the application is run with above step will create different port. For real world scenario we can use step 4 for this._

4. As the service is up and running inside the pod we need to access it through outside world, which can be done with the command `kubectl port-forward service/frontend-service 3000:3000 -n learner-report-frontend`

5. You can check making connection to the DB at 30005 port.
![Frontend_Connection](./snapshots/FrontendInBrowser.png


## References & Links


## Happy Coding
Thanks for continuing till the End. :)