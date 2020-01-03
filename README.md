# Welcome
First of all, we are happy to welcome you as new developer and consultant at Eyevinn Technology. The purpose with the following tasks is to get you quickly on-board to be able to contribute to the company and the video streaming open source community.

Our manifesto is that whenever we have the possibility to release our code as open source we should. Source code under non-disclosure agreement and where the intellectual property belongs to our customers are of course not released.

Read through these tasks and you can skip the tasks that you are already quite familiar with.

## 1.1 Create a Github account

If you don't already have a Github account create an account by following the instructions here: https://help.github.com/articles/signing-up-for-a-new-github-account/

We require that you enable two-factor authentication

Once your account has been created send the username you have chosen to Jonas Birmé on Slack or E-mail who will then add you to our organization on Github. If you are totally new to Git or Github we recommend you to take the time and read through the articles here: https://help.github.com/articles/good-resources-for-learning-git-and-github/

## 1.2 Fork our HTML5 player

Now you should be quite comfortable with Git and Github and ready to contribute. Begin with creating a fork of our HTML5 player: https://github.com/Eyevinn/html-player

Instructions on how to fork a repository can be found here: https://help.github.com/articles/fork-a-repo/

Eyevinn HTML Player is a simplistic video player for playback of ABR streams. It is free-to-use and currently supports the ABR streaming formats Apple HLS, MPEG-DASH and Microsoft Smooth Streaming. Once you have the player up and running browse through the code and repository that you forked and see if you find anything to contribute with. It can be a simple task such as modifying or adding a README file or a more complex task to add a new feature of your choice. It is completely up to you what you choose to do.

When you have decided what you want to do continue with next steps

## 1.3 Create a topic branch

Create a topic branch in your forked repository for the addition that you decided to do. Instructions on how to create a topic branch can be found here: https://help.github.com/articles/creating-and-deleting-branches-within-your-repository/

## 1.4 Issue a pull request

In your topic branch implement the feature and verify it works. Then issue a pull request, and instructions on how to do that can be found here: https://help.github.com/articles/creating-a-pull-request/

Your pull request will then be reviewed and if everything looks good it will be merged upstreams. Congratulations!

## 2. Install Docker Engine

Install Docker Engine on your computer. Docker Engine is an open source containerization technology for building and containerizing your applications. Docker Engine is available on a variety of Linux platforms, Mac and Windows through Docker Desktop, Windows Server, and as a static binary installation. Docker is a platform for developers and sysadmins to build, share, and run applications with containers. The use of containers to deploy applications is called containerization. Containers are not new, but their use for easily deploying applications is.

If you are new to the concept of Docker take the time and read more about it here: https://docs.docker.com/get-started/

## 3. Setup and Orchestrate a simple Media Function

The portability and reproducibility of a containerized process mean we have an opportunity to move and scale our containerized applications across clouds and datacenters; containers effectively guarantee that those applications will run the same way anywhere, allowing us to quickly and easily take advantage of all these environments. Furthermore, as we scale our applications up, we’ll want some tooling to help automate the maintenance of those applications, able to replace failed containers automatically and manage the rollout of updates and reconfigurations of those containers during their lifecycle.

Tools to manage, scale, and maintain containerized applications are called orchestrators, and the most common examples of these are Kubernetes and Docker Swarm. Development environment deployments of both of these orchestrators are provided by Docker Desktop, which we’ll use throughout this guide to create our first orchestrated, containerized application.

Enable and starta a Kubernetes single-node cluster on your computer that will run an example of a Media Function that you can read more about here: https://medium.com/@eyevinntechnology/building-serverless-media-functions-61bfc400af20

Your task is then to create a Kubernetes `pod.yaml` that will create a pod with this single `function-probe` container. Verify that it is up and running:

```
$ kubectl get pods
NAME             READY   STATUS    RESTARTS   AGE
function-probe   1/1     Running   0          5s
```

and to try it out create a port-forwarding:

```
$ kubectl port-forward function-probe 8080:8080
```

and then point your browser to `http://localhost:8080/` and if everything works correctly the API documentation for this media function will be shown.

## 4. Install our streaming toolbox

There a couple of tools that are useful to have at hand when working with video and streaming. We have a set of Docker images prepared with a couple of these tools pre-built: https://github.com/Eyevinn/toolbox 

And if you have any suggestion on what should be added to the toolbox file an issue in the above repository or even better make your own contribution.

## 5. Make a contribution to the community

Browse through Github to find a relevant repository / project in the video streaming area which you can contribute to. When you have found the project to contribute to then:

 1. Fork the repository
 2. Create topic branch
 3. Implement feature
 4. Issue pull request
 
Congratulations! You have now made your (first) contribution to the video streaming open source community.
