Codes changes of the application needs to applied by merging pull request to this [repository](https://github.com/cissoidx/cd12355-microservices-aws-kubernetes-project-starter/tree/main).

The merge of the pull request will trigger AWS codebuild to build a new docker image that holds the latest application.

The resulting docker image will be then pushed to AWS ECR.

The AWS kubernetes cluster contains a postgresql database deployment and a coworking application deployment. When a new docker image is pushed to ECR, the old application pod will be terminated and a new pod running the new docker image will be created.

Logs of the application can be viewed in CloudWatch. Other metrics like CPU usage, memory usage, disk usage can also be monitored. Resources of the deployment can be ajusted by querying these information. Use `kubectl apply -f deployment` to refresh the deployment in console.
