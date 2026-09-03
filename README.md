# Awesome ECS with stars

A curated list of guides, development tools, and resources for:

[<img src="ecs.svg" width="32px" align="middle" style="vertical-align: middle"> Amazon Elastic Container Service](https://aws.amazon.com/ecs/) (ECS)

[<img src="fargate.svg" width="32x" align="middle" style="vertical-align: middle"> AWS Fargate](https://aws.amazon.com/fargate/)

This list includes both community created content as well as content created by AWS.

Are you looking for infrastructure as code templates and tutorials for ECS? [Containers on AWS](https://containersonaws.com/pattern) is the home for infrastructure patterns and sample code to get you started fast.

[<img src="https://containersonaws.com/images/social-card.png" width="50%" style="vertical-align:middle">](https://containersonaws.com/pattern)

Do you prefer video instead? If so check out [Containers from the Couch](https://containersfromthecouch.com/) for videos on all things AWS + containers.

[<img src="containers-from-the-couch.png" width="50%">](https://containersfromthecouch.com/)

*Want to add something? Open a PR!* 🙂

### First steps

* [Amazon ECS Core Concepts](https://containersonaws.com/presentations/amazon-ecs-core-concepts/) - Introduction to core concepts of Amazon ECS, including what are containers, why it is important to decouple applications from their underlying compute infrastructure, how ECS works, and what integrations that ECS has with the rest of AWS.
* [Building Blocks of Amazon ECS](https://medium.com/containers-on-aws/building-blocks-of-amazon-ecs-db7fdfeeaa6f) - Learn about the basic building blocks of ECS and how they fit together to fully understand how it works and how you can use it!
* [ECS Workshop](https://ecsworkshop.com/) - A detailed workshop that guides you through creating a simple microservice deployment, load testing it, and monitoring it.
* [AWS Copilot](https://aws.github.io/copilot-cli/docs/getting-started/first-app-tutorial/) - The getting started guide for AWS Copilot helps you deploy your first simple static website container on Fargate.

### Pick your container hosting strategy:

* [Amazon EC2 or AWS Fargate?](https://containersonaws.com/blog/2023/ec2-or-aws-fargate/) - Which compute capacity makes more sense for your workload: serverless AWS Fargate, or EC2 instances?
  * If you pick EC2 capacity learn about [ECS capacity providers linked to EC2 auto scaling groups](https://containersonaws.com/pattern/ecs-ec2-capacity-provider-scaling) and [running containers on EC2 spot capacity](https://containersonaws.com/pattern/ecs-spot-capacity-cluster) and consider [Bottlerocket](https://bottlerocket.dev/) as the [container focused operating system for your Amazon ECS cluster](https://containersonaws.com/pattern/ecs-ec2-bottlerocket-cluster).

### Pick a tool for deploying your application

* [CloudFormation](https://github.com/awslabs/aws-cloudformation-templates/tree/master/aws/services/ECS) ⭐ 5,212 | 🐛 5 | 🌐 Python | 📅 2026-07-28 - You can choose to write CloudFormation templates to describe your deployment directly, in which case these sample templates will help. Check out [prebuilt CloudFormation patterns for AWS CloudFormation and Amazon ECS + AWS Fargate](https://containersonaws.com/pattern/?tool=cloudformation)
* [Troposphere + ECS](https://github.com/cloudtools/troposphere/blob/master/examples/ECSFargate.py) ⭐ 4,944 | 🐛 163 | 🌐 Python | 📅 2026-08-19 - For Python users [Troposphere](https://github.com/cloudtools/troposphere) ⭐ 4,944 | 🐛 163 | 🌐 Python | 📅 2026-08-19 can help create CloudFormation templates. This example shows how to create an ECS deployment using Troposphere
* [AWS Copilot](https://aws.github.io/copilot-cli/) - The easiest starting experience for launching your local container on Fargate. This commandline tool helps you build and deploy your application, as well as deploy CI/CD pipelines that automatically rebuild and redeploy your application on Git push. It creates infrastructure as code templates for you behind the scenes.
* [AWS Cloud Development Kit](https://aws.amazon.com/cdk/) - AWS CDK is an SDK that lets developers define and deploy AWS infrastructure using familiar programming languages, often the same language that the application itself is coded in. CDK creates CloudFormation automatically behind the scenes.
  * [aws-ecs](https://www.npmjs.com/package/@aws-cdk/aws-ecs) - This module provides simple low level constructs for creating ECS and Fargate services. It gets about 100k downloads per week on NPM, so it is quite popular as a choice.
  * [aws-ecs-patterns](https://www.npmjs.com/package/@aws-cdk/aws-ecs-patterns) - A more beginner friendly interface to CDK. These patterns help you setup simple things like a "load balanced service" or a "scheduled task"
  * [ecs-service-extensions](https://www.npmjs.com/package/@aws-cdk-containers/ecs-service-extensions) - This CDK module provides the most extendable interface for ECS services. It lets you deploy an ECS service and then optionally attach extensions to it, which do things like add the service to a service mesh, or add an observability sidecar, etc. Read more about [how to build custom extensions for ECS deployments](https://containersonaws.com/pattern/ecs-service-extensions-custom-extension)
* [Terraform ECS Blueprints](https://catalog.workshops.aws/ecs-solution-blueprints/en-US) - Production ready AWS ECS infrastructure as code with Terraform

<details>
  <summary><b>Older tools</b></summary>

The following tools may not be as up-to-date or maintained, but are retained here for reference:

* [ecs-deploy](https://github.com/silinternational/ecs-deploy) ⭐ 1,985 | 🐛 1 | 🌐 Shell | 📅 2026-07-01 - Simple but powerful tool for initiating automatic blue green deploys on ECS
* [CloudFormation reference architecture](https://github.com/awslabs/ecs-refarch-cloudformation) ⚠️ Archived - An older CloudFormation reference architecture for ECS
* [ecspresso](https://github.com/kayac/ecspresso) ⭐ 1,118 | 🐛 24 | 🌐 Go | 📅 2026-09-02 - Minimalistic: JSON file goes in, service launches
* [mu](https://github.com/stelligent/mu) ⭐ 965 | 🐛 89 | 🌐 Go | 📅 2020-06-18 - Automates everything relating to ECS devops and CI/CD. This framework lets you write a simple metadata file and it constructs all the infrastructure you need so that you can deploy to ECS by simply pushing to your Git repo.
* [ecsdeploy](https://github.com/in4it/ecs-deploy) ⭐ 259 | 🐛 8 | 🌐 Go | 📅 2026-09-03 - A client and simplified web interface for managing your ECS cluster, rolling out and rolling back application versions
* [ecsctl](https://github.com/cxmcc/ecsctl) ⭐ 117 | 🐛 2 | 🌐 Python | 📅 2021-03-22 - Open source tool similar to Kubernetes `kubectl` for ECS.
* [fargate-create](https://github.com/turnerlabs/fargate-create) ⭐ 106 | 🐛 4 | 🌐 Go | 📅 2026-08-07 - A CLI tool for creating new projects based on Terraform templates and [Fargate CLI](https://github.com/turnerlabs/fargate) ⭐ 150 | 🐛 10 | 🌐 Go | 📅 2026-07-27. Supported stacks:
  * [Web Application (ALB - HTTP/HTTPS)](https://github.com/turnerlabs/terraform-ecs-fargate) ⭐ 433 | 🐛 5 | 🌐 HCL | 📅 2026-05-06
  * [Network Application (NLB)](https://github.com/turnerlabs/terraform-ecs-fargate-nlb) ⚠️ Archived
  * [Scheduled Task (Job)](https://github.com/turnerlabs/terraform-ecs-fargate-scheduled-task) ⚠️ Archived
  * [Background Worker (Service)](https://github.com/turnerlabs/terraform-ecs-fargate-background-worker) ⚠️ Archived
* [deployfish](https://github.com/caltechads/deployfish) ⭐ 91 | 🐛 4 | 🌐 HTML | 📅 2026-09-02 - Write a simplified `deployfish.yml` file describing your deployment and let this tool handle the heavy lifting of deploying your service.
* [ecsq](https://github.com/mightyguava/ecsq) ⭐ 90 | 🐛 2 | 🌐 Go | 📅 2023-03-10 - A developer friendly tool for querying the state of an ECS cluster
* [broadside](https://github.com/lumoslabs/broadside/) ⭐ 44 | 🐛 5 | 🌐 Ruby | 📅 2021-07-22 - Ruby based command line tool for deploying to ECS
* [pnzr](https://github.com/jobtalk/pnzr) ⭐ 31 | 🐛 4 | 🌐 Go | 📅 2018-09-18 - Go based tool for building and pushing to ECS, also has integraton with AWS KMS for secrets management.
* [deplojo](https://github.com/LabD/ecs-deplojo) ⭐ 19 | 🐛 5 | 🌐 Python | 📅 2026-04-28 - Python based deployment tool using ECS
* [ecsrun](https://github.com/masterpointio/ecsrun) ⭐ 17 | 🐛 0 | 🌐 Go | 📅 2026-04-08 - Easily run one-off tasks against an ECS Task Definition using a config file based approach.
* [kms-env](https://github.com/ukayani/kms-env) ⭐ 17 | 🐛 2 | 🌐 JavaScript | 📅 2023-04-18 - CLI tool for managing secrets using AWS KMS in .env files which can be used in conjunction with **ecs-service** to supply secrets to your containers
* [shipctl](https://github.com/SKAhack/shipctl) ⭐ 12 | 🐛 1 | 🌐 Go | 📅 2018-11-30 - Tool that supports deploying a task on ECS, rolling back, or just running a one-off task
* [ecs-service](https://github.com/ukayani/ecs-service) ⭐ 12 | 🐛 6 | 🌐 JavaScript | 📅 2017-10-12 - CLI tool for deploying to ECS using CloudFormation with support for .env files for environment specific configuration of your containers
* [ECS CLI v1](https://docs.aws.amazon.com/AmazonECS/latest/developerguide/ECS_CLI.html) - The original CLI for ECS is designed to be mostly compatible
  with Docker Compose. It turns a local Docker Compose file into a remote deployment.
* [fargate](http://somanymachines.com/fargate/) - Command line tool for interacting with AWS Fargate. With just a single command you can build, push, and launch your container in Fargate, orchestrated by ECS.
* [Airship Terraform for ECS](https://github.com/blinkist/terraform-aws-airship-ecs-service)
* [Cloudonaut CloudFormation templates](https://cloudonaut.io/new-cloudformation-templates-ecs-cluster-service-legacy-vpc-wrapper-automated-tests/)
* * [empire](https://github.com/remind101/empire) ⭐ 2,675 | 🐛 90 | 🌐 Go | 📅 2023-11-25 - Control layer on top of ECS that provides a Heroku like workflow
* [UFO](http://ufoships.com/) - Ruby based tool for building containers and shipping them to ECS
* [bash deployment script](https://spin.atomicobject.com/2017/06/06/ecs-deployment-script/) by [Justin Kulesza](https://twitter.com/JustinKulesza)
* [convox](https://convox.com/) - Easily build, deploy and scale applications on ECS
* [Wonqa](https://www.npmjs.com/package/wonqa) is a tool for spinning up disposable QA environments in AWS Fargate, with SSL enabled by Let's Encrypt. More details about Wonqa on the [Wonder Engineering blog](https://medium.com/wonder-engineering/on-demand-qa-environments-with-aws-fargate-c23b41f15a0c).

</details>

### Solutions

* <a name="service-discovery" /> **Service Discovery**
  * [Using built-in AWS CloudMap service discovery](https://containersonaws.com/pattern/service-discovery-fargate-microservice-cloud-map)
  * [Using built-in ECS Service Connect](https://docs.aws.amazon.com/AmazonECS/latest/developerguide/service-connect.html)
  * [Using Consul](https://aws.amazon.com/blogs/compute/service-discovery-via-consul-with-amazon-ecs/)
  * [Using Weaveworks](https://www.weave.works/blog/using-weave-to-network-containerized-microservices-on-amazon-ecs/)
  * [Using linkerd](https://medium.com/attest-engineering/linkerd-a-service-mesh-for-aws-ecs-937f201f847a)
  * [Using HAProxy](https://medium.com/ground-signal-engineering/ecs-service-discovery-with-lambda-dns-and-haproxy-1126ab381688)
* **Scaling**
  * [Amazon ECS Scalability Best Practices](https://containersonaws.com/presentations/amazon-ecs-scaling-best-practices/)
  * [Target tracking based application scaling](https://containersonaws.com/pattern/target-tracking-scale-ecs-service-cloudformation)
  * [Step scaling policies for application scaling](https://containersonaws.com/pattern/scale-ecs-service-cloudformation)
* **Service Mesh**
  * [Service Connect (Envoy Proxy based service mesh built-in to Amazon ECS)](https://containersonaws.com/pattern/ecs-service-connect-aws-copilot)
  * [AWS App Mesh](https://docs.aws.amazon.com/app-mesh/latest/userguide/getting-started-ecs.html)
* **Data Persistance**
  * [Using Amazon Elastic File System example in AWS Cloud Development Kit](https://containersonaws.com/pattern/elastic-file-system-ecs-cdk)
  * [Using Amazon Elastic File System example in CloudFormation](https://containersonaws.com/pattern/cloudformation-ecs-durable-task-storage-with-efs)
  * [Using Amazon Elastic File System example in AWS Copilot](https://containersonaws.com/pattern/elastic-file-system-aws-copilots)
* **Secrets Management**
  * [Open source tool for automatically getting secrets from SSM into your docker environment](https://github.com/SignalMedia/signal-secret-service) ⭐ 21 | 🐛 1 | 🌐 Shell | 📅 2023-03-13
  * [AWS Secrets Manager + Amazon ECS](https://docs.aws.amazon.com/AmazonECS/latest/developerguide/specifying-sensitive-data-tutorial.html)
  * [Using Parameter Store and IAM Roles for Tasks](https://aws.amazon.com/blogs/compute/managing-secrets-for-amazon-ecs-applications-using-parameter-store-and-iam-roles-for-tasks/)
  * [Using ECS Task roles for managing AWS credentials](https://medium.com/@RemindEng/keeping-aws-secrets-secret-with-ecs-ec4a51517b4d)
  * [The right way to store secrets using Parameter Store](https://aws.amazon.com/blogs/mt/the-right-way-to-store-secrets-using-parameter-store/)
  * [Scaling from 10 to 16k+ tasks in a single ECS cluster](https://containersonaws.com/pattern/scaling-from-10-to-15000-tasks)
* **Administration**
  * [Accessing Rails console inside of an ECS task](https://github.com/mnc/rails-console-ecs) ⭐ 15 | 🐛 5 | 🌐 Shell | 📅 2018-08-03
  * [Monitor cluster state with Cloudwatch event stream](https://containersonaws.com/pattern/ecs-task-events-capture-cloudwatch)
  * [React to ECS events such as crashed containers using a serverless function](https://medium.com/@laardee/subscribe-to-aws-ecs-event-stream-using-serverless-framework-74de3db66ddb)
  * [Run an ECS Task on every cluster instance](https://aws.amazon.com/blogs/compute/running-an-amazon-ecs-task-on-every-instance/)
* **CI/CD**
  * [AWS CodePipeline](https://github.com/awslabs/ecs-refarch-continuous-deployment) ⚠️ Archived
  * [Atlassian Bamboo](https://bitbucket.org/atlassian/per-build-container)
  * [JetBrains TeamCity](https://blog.jetbrains.com/teamcity/2017/11/teamcity-aws-ec2-container-service/)
  * [Lambda](https://medium.com/@YadavPrakshi/automate-zero-downtime-deployment-with-amazon-ecs-and-lambda-c4e49953273d)
  * [CircleCI](https://github.com/circleci/go-ecs-ecr)
  * [Shippable](http://blog.shippable.com/continuous-delivery-from-github-to-amazon-ecs)
  * [Gitlab](https://jeanphix.github.io/2017/06/14/how-to-configure-a-gitlab-ecs-continuous-deployment-pipeline/)
  * [SemaphoreCI](https://semaphoreci.com/community/tutorials/continuous-deployment-of-a-dockerized-node-js-application-to-aws-ecs)
* **CI/CD mechanics:**
  * [Canary Deploy](https://github.com/awslabs/ecs-canary-blue-green-deployment) ⚠️ Archived
  * [Rolling blue/green deploy in place](https://blog.codeship.com/easy-blue-green-deployments-on-amazon-ec2-container-service/)
  * [Isolated Regression Testing](https://aws.amazon.com/blogs/compute/amazon-ecs-at-the-climate-corporation-using-ecr-and-multiple-accounts-for-isolated-regression-testing/)
* **Open source:**
  * [Sample task definitions](https://github.com/aws-samples/aws-containers-task-definitions) ⭐ 276 | 🐛 0 | 📅 2021-07-26 - Sample task definitions for running applications like Nginx, Tomcat, Gunicorn, Wildfly, Kibana, and Jetty as containers under Amazon ECS
  * [ecs-export](https://github.com/slok/ecs-exporter) ⭐ 143 | 🐛 9 | 🌐 Go | 📅 2023-11-03 - A tool for exporting ECS cluster metrics to Prometheus for advanced querying
  * [docker-elk-ecs](https://github.com/markriggins/docker-elk-ecs) ⭐ 14 | 🐛 0 | 🌐 Shell | 📅 2016-05-25 - Connecting Amazon ECS container logs to an ELK (Elasticsearch, Logstash, Kibana) stack
  * [Watchbot](https://github.com/mapbox/ecs-watchbot) - This tool by [Mapbox](https://www.mapbox.com/) helps you run data processing across an ECS cluster in response to external events

### Reference Architectures

* [Mythical Misfits](https://github.com/aws-samples/amazon-ecs-mythicalmysfits-workshop) ⭐ 338 | 🐛 29 | 🌐 HTML | 📅 2025-09-12 - Deploy a sample application to serverless AWS Fargate capacity
* [Cats n' Dogs](https://github.com/aws-samples/amazon-ecs-catsndogs-workshop) ⭐ 169 | 🐛 14 | 🌐 Shell | 📅 2020-10-18 - A fun workshop that covers service and container-instance auto-scaling, spot-fleet integration, container placement strategies, service discovery, secrets management with AWS Systems Manager Parameter Store, among other things.
* [Bun JavaScript container that uses AWS SDK to connect to DynamoDB](https://containersonaws.com/pattern/bun-js-aws-sdk-container) - A tiny hit counter application. It demonstratres launching a Bun JavaScript container, with an IAM role that grants it access to use a DynamoDB table as it's state store.
* [NGINX Reverse Proxy sidecar container on AWS ECS](https://containersonaws.com/pattern/nginx-reverse-proxy-sidecar-ecs-fargate-task) - A common architecture for serving a website or API from a container
* [Deploy Jupyter notebook container with Amazon ECS](https://containersonaws.com/pattern/jupyter-notebook-inference-container-cloudformation) - High cost, high performance machine learning playground, orchestrated by Amazon ECS on specialized AWS Inferentia enabled hardware.

### Courses

* **Free**
  * [ECS Workshop](https://ecsworkshop.com/) - Learn how to deploy a 3 tier, polyglot, microservice based application to AWS Fargate
  * [Cloudskills: The beginners guide to running Docker containers on AWS](https://www.youtube.com/watch?v=lO2wU2rcGUw)
  * [Simplilearn: AWS ECS Tutorial](https://www.youtube.com/watch?v=46mFdtpy3NQ)
* **Paid**
  * [Microservices with Docker, Flask, and React](https://testdriven.io/courses/aws-flask-react/) - Learn how to build, test, and deploy microservices powered by Docker, Flask, and React on Amazon ECS!
  * [AWS Developer: Optimizing on AWS](https://courses.edx.org/courses/course-v1:AWS+OTP-AWSD3+1T2018/course/) - Learn how you can optimize your applications on AWS with Amazon ECS!
  * [Udemy: ECS Deep Dive](https://www.udemy.com/course/aws-ecs-deep-insight/)
  * [Cloud Academy: Introduction to ECS](https://cloudacademy.com/course/introduction-to-amazon-ecs-services/introduction-41/)
  * [Coursera: Building Containerized Applications on AWS](https://www.coursera.org/lecture/containerized-apps-on-aws/introduction-to-week-3-0owxp)

### Blogs

* [Run a PHP application on AWS Fargate](https://www.codedge.de/posts/20200419-run-php-application-on-aws-fargate/) - An in-depth guide to run a Laravel app on AWS Fargate with Github Actions for deployment
* [Deploying a Rails app to Fargate](http://blog.scoutapp.com/articles/2018/01/08/deploying-to-aws-part-i-running-a-rails-app-on-fargate) - Step by step walkthrough of deploying a Ruby + RDS app, with helpful debugging tips
* [How to use AWS Fargate and Lambda for long-running processes in a Serverless app](https://serverless.com/blog/serverless-application-for-long-running-process-fargate-lambda/) - Great tutorial showing how to leverage the power of long running docker containers in Fargate alongside Lambda. Example application processes video files to extract thumbnails using just S3, Lambda, and Fargate... no EC2.
* [Setting up service discovery for AWS Fargate using CloudFormation](https://paul.annesley.cc/ecs-service-discovery-cloudformation/)
* [Using the Clair image scanner with Fargate, ECR and CodeBuild/CodePipeline](https://github.com/jasonumiker/clair-ecs-fargate)
* [A lighter way to deploy to ECS/Fargate](https://ramblingsofasoftwaredevelopermanager.wordpress.com/2019/05/18/a-lighter-way-to-deploy-to-aws-ecs/) - combining update-service/task data from several sources including metadata of the docker image itself to deploy new versions.
* [Chaos testing with ECS](https://docs.chaostoolkit.org/drivers/aws/#ecs) - Chaos toolkit supports ECS as a target for [chaos engineering](https://principlesofchaos.org/)
* [Private subnets tutorial](https://www.topcoder.com/blog/aws-container-services-private-subnets-tutorial/)
* [End-to-end TLS traffic](https://aws.amazon.com/blogs/compute/maintaining-transport-layer-security-all-the-way-to-your-container-using-the-network-load-balancer-with-amazon-ecs/) - How to setup end-to-end TLS from client to container, as well as from container to container
* [Docker for .NET Developers](https://www.stevejgordon.co.uk/docker-dotnet-developers-part-1)

### Presentations

* [Amazon ECS Scalability Best Practices](https://containersonaws.com/presentations/amazon-ecs-scaling-best-practices/)
* [Running your Dockerized application(s) on AWS EC2 Container Service](https://speakerdeck.com/mpas/running-your-dockerized-application-s-on-aws-ec2-container-service) by [Marco Pas](https://twitter.com/marcopas)
* [Microservices on AWS with Weaveworks](https://www.youtube.com/watch?v=nSvpjZkmYIM)
* [Running a Virtual World via ECS](https://www.youtube.com/watch?v=wGg_4aFOHsY) - Linden Labs on their usage of ECS
* [Advanced Task Scheduling with AWS ECS](https://www.youtube.com/watch?v=RJZU0zZoKR8)
* [Instacart on running microservices on Amazon ECS](https://www.youtube.com/watch?v=CtALTTjy7Qw)
* [Building Next-Generation Applications with Amazon ECS](https://www.youtube.com/watch?v=xIc3WT6kAVw) - How Meteor Built Galaxy on Amazon ECS
* [Amazon ECS at Coursera: A General Purpose Microservice](https://www.slideshare.net/AmazonWebServices/cmp406-amazon-ecs-at-coursera-a-generalpurpose-microservice)

***

> _Enhansomed by [enhansome](https://github.com/enhansome) on 2026-09-03._
