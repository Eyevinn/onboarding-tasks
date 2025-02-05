# Welcome
First of all Hello!, we are happy to welcome you as new developer and consultant at Eyevinn Technology. The purpose with the following tasks is to get you quickly on-board to be able to contribute to the company and the video streaming open source community.

Our manifesto is that whenever we have the possibility to release our code as open source we should. Source code under non-disclosure agreement and where the intellectual property belongs to our customers are of course not released.

Read through these tasks and you can skip the tasks that you are already quite familiar with. Every task has a named person to who you in first hand can address questions to.

# 1. Working with GitHub

We are using GitHub as the main code space for source code that we maintain and are responsible for.

## 1.1 Create a Github account

If you don't already have a Github account create an account by following the instructions here: https://help.github.com/articles/signing-up-for-a-new-github-account/

### We require that you enable two-factor authentication 
 
You can find more info on choosing your 2FA account [here](https://help.github.com/en/github/authenticating-to-github/configuring-two-factor-authentication)

Once your account has been created send the username you have chosen to Jonas Birmé on Slack or E-mail who will then add you to our organization on Github. If you are totally new to Git or Github we recommend you to take the time and read through the articles here: https://help.github.com/articles/good-resources-for-learning-git-and-github/

## 1.2 Fork this onboarding repository

Now you should be quite comfortable with Git and Github and ready to contribute. Begin with creating a fork of this onboarding repository: https://github.com/Eyevinn/onboarding-tasks

Instructions on how to fork a repository can be found here: https://help.github.com/articles/fork-a-repo/

Find something you want to modify with this text. When you have decided what you want to do, continue with next steps.

## 1.3 Create a topic branch

Create a topic branch in your forked repository for the modifications that you decided to do. Instructions on how to create a topic branch can be found here: https://help.github.com/articles/creating-and-deleting-branches-within-your-repository/

## 1.4 Issue a pull request

In your topic branch implement the feature and verify it works. Then issue a pull request, and instructions on how to do that can be found here: https://help.github.com/articles/creating-a-pull-request/

Your pull request will then be reviewed and if everything looks good it will be merged upstreams. Congratulations!

# 2. Create your own video streaming application

The goal of this task is to build your own video streaming application using the open web services available in [Eyevinn Open Source Cloud](https://www.osaas.io). Login to Eyevinn OSC using your Eyevinn email address and choose the "Eyevinn Lab Account" tenant. If that selection is not visible on the list of available tenants reach out to Jonas Birmé.

Mentor for this section is Jonas Birmé.

## 2.1 Create a streaming video file

First step is to create an streaming video file that you will use. Record a video using for example your mobile phone and transfer it to your computer. Follow the instructions in the blog post [Stream video with open web services](https://dev.to/video/stream-video-with-open-web-services-17k5) to setup a video processing pipeline and process the video you recorded.

## 2.2 Create a web video application

Next step is to create a web application to playback the video stream you created. Follow the steps in the blog post [Creating a web video application](https://dev.to/video/creating-a-web-video-application-56pb). Make the web video application available online as described in the blog post but replace the site name `video` with something of your choice. Send the URL to your site to the mentor of this section.

# 3. Install Docker Engine

It is today common to work with containerized applications as part of a micro service architecture style. It is essential to have the basic knowledge in how to work with for example Docker containers. Mentor for this section is Jonas Birmé.

Install Docker Engine on your computer. Docker Engine is an open source containerization technology for building and containerizing your applications. Docker Engine is available on a variety of Linux platforms, Mac and Windows through Docker Desktop, Windows Server, and as a static binary installation. Docker is a platform for developers and sysadmins to build, share, and run applications with containers. The use of containers to deploy applications is called containerization. Containers are not new, but their use for easily deploying applications is.

If you are new to the concept of Docker take the time and read more about it here: https://docs.docker.com/get-started/

# 4. FFMPEG (optional)

When working with media processing, you may want to experiment with some aspects on your local machine. For example, you may want to investigate how different encoder parameters affect the quality of the final output. [FFMPEG](https://www.ffmpeg.org) is an open source media toolkit that handles pretty much everything you throw at it. In this section, we'll discuss how to install FFMPEG, and use it to transcode a video.

## 4.1 Installing FFMPEG

### macOS

The easiest way of installing the latest version of FFMPEG on macOS is to use [homebrew](https://brew.sh). If you have homebrew installed, simply enter
```
brew install ffmpeg
```
into your terminal.

### Windows
If you're using windows, FFMPEG builds are available for download on the [FFMPEG download page](https://www.ffmpeg.org/download.html).

### Linux
If using a debian-based linux distro, entering
```
apt-get install ffmpeg
```
into your terminal will install FFMPEG on your system.

### Note: custom builds
Depending on your use case, you may need to build FFMPEG from source. The source code is available on the [FFMPEG download page](https://www.ffmpeg.org/download.html).

## 4.2 Transcoding a video
Now that FFMPEG is isntalled on your system, let's transcode a video. Start by verifying that FFMPEG is installed by entering
```
ffmpeg -version
```
into your terminal. You should see the version installed on your computer, as well as the configuration used for compiling it.

Now, let's transcode a video! We'll use [Big buck bunny](https://peach.blender.org) as our content, since it's free to use ad open source.
To download the video, enter 
```
curl -o bunny.mp4 http://distribution.bbb3d.renderfarming.net/video/mp4/bbb_sunflower_1080p_30fps_normal.mp4
```
The video is encoded using [h.264](https://en.wikipedia.org/wiki/Advanced_Video_Coding) and packaged into an MP4; we'll transcode it to instead use [VP9](https://en.wikipedia.org/wiki/VP9), and package it using a webm container. We'll also need to transcode the audio to use OGG vorbis.
To do this, enter the following command into your terminal:
```
ffmpeg -i bunny.mp4 -c:v libvpx-vp9 -c:a libvorbis bunny.webm
```
This tells FFMEG to transcode the input `bunny.mp4` using the `libvpx-vp9` VP9 implementation for the video, and `libvorbis` Vorbis encoder, and write the output to the file `bunny.webm`.

Congratulations, you've just transcoded a media file using FFMPEG! To learn more about FFMPEG, take a look at the [documentation](https://www.ffmpeg.org/documentation.html).