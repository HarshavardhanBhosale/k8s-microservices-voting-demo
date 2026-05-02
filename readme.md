🐾 Cat vs Dog Voting App (Kubernetes)A multi-stack microservices application deployed on Kubernetes. This project demonstrates the orchestration of different programming languages and data stores working together in a containerized environment.🏗️ ArchitectureThe application consists of five main components:Vote (Python/Flask): Frontend web app to cast votes.Redis: In-memory queue to collect raw votes.Worker (.NET): Consumes votes from Redis and stores them in the DB.PostgreSQL (DB): Persistent storage for vote results.Result (Node.js): Frontend web app to display real-time results.🚀 Deployment DetailsBased on the current cluster status:Pods: 5 microservices running in high availability.Services:vote: Accessible on NodePort 31000result: Accessible on NodePort 31001db & redis: Internal ClusterIP services.🛠️ How to RunClone the repo:bashgit clone https://github.com/HarshavardhanBhosale/k8s-microservices-voting-demo.git
cd k8s-microservices-voting-demo
Use code with caution.Apply the manifests:bashkubectl apply -f .
Use code with caution.Access the App:Voting Page: http://<node-ip>:31000Results Page: http://<node-ip>:31001📊 Current Cluster StatustextNAME                          READY   STATUS    RESTARTS   AGE
pod/db-5f4b6959b4-p4bz5       1/1     Running   0          39s
pod/redis-69f5974b5-66x5d     1/1     Running   0          39s
pod/result-5dbd594fb5-52jxw   1/1     Running   0          39s
pod/vote-8f9979fc-b9kzw       1/1     Running   0          39s
pod/worker-558876578-cmkkq    1/1     Running   0          38s
Use code with caution.📜 AcknowledgmentsProject inspired by the KodeKloud Kubernetes for Beginners course.