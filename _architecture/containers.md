---
layout: single
author_profile: false
title: "Containers and orchestration"
excerpt: "The story of a whale and a boat."
sidebar:
  nav: "architecture"
header:
  teaser: /assets/images/docker/containers-small.png
gallery1:
  - url: /assets/images/docker/containers.png
    image_path: assets/images/docker/containers.png
gallery2: 
  - url: /assets/images/docker/structure.png
    image_path: assets/images/docker/structure.png
gallery3: 
  - url: /assets/images/docker/kubernetes.png
    image_path: assets/images/docker/kubernetes.png
---

## An easy way to deploy applications :sunny:

When creating a new application, developers often rely on a lot of additional software dependencies (reused libraries or packages). Therefore, as they want to deliver their app to another person (for testing purposes for example) or to deploy it in production, they have to specify the OS and all the associated dependencies. Several apps may even require different versions of the same libs! That is a tedious task, resulting in a lot of wasted energy to make it work. :scream: With **containers**, developers can easily package up the application code and all its dependencies in a single container image. :gift: Applications are therefore much more independent from the underlying infrastructure.

Unlike Virtual Machines which require to install a full OS, containers reuse the host OS kernel. Therefore, they are lighter, use less resources, and boot up faster than VMs. :leaves: Of course, this comes at the expense of security since a larger software stack is shared between containers. The following modelling illustrates differencies between Containers and Virtual Machines.

{% include gallery id="gallery1" type="center" %}

**Note:** Containers are not new! LXC containers have already been existing for a while. But **Docker** provides a high-level interface which makes it much easier to build, administrate and run runC containers. :whale:
{: .notice--warning}

## Docker architecture

Docker is built on a client-server model:
- The docker client uses a Command Line Interface to send commands to the docker server.
- The docker server hosts the docker daemon, which listens for API requests and manages docker objects.
- The docker registry (private or public) hosts docker images which contain all the instructions for running a Docker container.

In order to build a new image, Docker uses **Dockerfiles** to list all the instructions (commands on CLI) that a user would use. :hammer: The syntax makes it very easy to start from an existing Docker image (such as an alpine or busybox distribution), to copy a script on the image, to specify execution commands… The **Docker Hub** already contains a dazzling amount of predefined container images, for databases, web servers, messaging brokers… :pray: It becomes much easier to build microservices architectures, that divide code into separate, standalone, and task-specific building blocks.

But what if we want to deploy a full application with several containers and networking services? Typing many Docker commands is time-consuming and error-prone. Instead, Docker uses the YAML syntax to create a **Compose file** that fully defines our multi-containers application. And we can now start multiple services from a single command! :sparkles:

The following modelling illustrates the layered structure of Dockers, and some of its native security features.

{% include gallery id="gallery2" type="center" %}

<div class="notice--warning" markdown="1">
**Docker commands 101:**
- docker run -p 80:8080 -v /kartapuce/datadir:/var/lib/mysql -e PWD=unsecure --name kartapuce-container --network kartapuce-network -d -it kartapuce-image:latest
- docker inspect kartapuce-container
- docker history kartapuce-container
- docker build -f dockerfile -t kartapuce-image
- docker push kartapuce-image
- docker compose -f kartapuce-microservices.yaml up
- docker compose down
</div>

## We need some orchestration ! :musical_score:

With Docker, we have all our applications easily deployed into production. Now what? We need to make sure that they will deliver the required services without any downtime! :chart_with_downwards_trend: So, we must find a way to automatically scale up and down our microservices, to manage them across several hosts, to detect a failure and respond by spawning a new instance, to easily upgrade or rollback containers without any downtime… To keep it short, we need an **orchestration technology** to deploy and manage containers in a cluster environment. There comes **Kubernetes**! :anchor:

The Kubernetes architecture relies on the following core components:
- A Control Plane: It watches the nodes of the cluster and responds to cluster events (orchestration). The API server acts as the front-end of the cluster. The control plane also contains the etcd, controller manager, and scheduler.
- A cluster: It is a set of worker nodes that run containerized applications.
- Worker nodes: A physical or virtual machine that hosts a container runtime (such as containerd or Docker), and runs the containers. :construction_worker: They also host the kubelet agent that registers the node with the API server, and make sure that containers are up and running.

The flowing modelling describes some of the workloads provides by the Kubernetes architecture.

{% include gallery id="gallery3" type="center" %}

Kubernetes uses the YAML syntax to define objects. These definition files specify the expected state of each object (pods, replicas, deployments, services...), and are used to set up the expected deployment. :rocket:

<div class="notice--warning" markdown="1">
**Kubernetes commands 101:**
- kubectl run kartapuce --image kartapuce-image
- kubectl describe pod kartapuce
- kubectl get pods, replicasets, deployments, services
- kubectl apply -f kartapuce-deployment.yaml
</div>

**Note:** Based on original learning material from [Docker](https://docs.docker.com/) and [Kubernetes](https://kubernetes.io/) engineers.
{: .notice--info}
