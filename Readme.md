# Building Go with Glide package management in the cloud

## Introduction

Glide is a popular vendor package management system for Golang. It is possible to use it with the convenience of managing the build process in the cloud with Cloud Container Builder. This repository shows how to do it just by build the glide binary itself from souce. Container Builder defined build pipeline in `cloudbuild.yaml` will clone the glide source from its GitHub repository, use glide install to pull in the correct versions of all dependencies, and the go-debian based builder to build the glide binary.

## Instructions

You can launch this tutorial in Cloud Shell clicking this button:

[![Open in Cloud Shell](http://gstatic.com/cloudssh/images/open-btn.svg)](https://console.cloud.google.com/cloudshell/open?git_repo=https%3A%2F%2Fgithub.com%2Fsh3lld00m%2Fbuild-glide.git&page=shell&tutorial=Readme.md)

Make sure you're in a GCP project where Google Cloud Container Builder API has been enabled. 

If you're interested in knowing what's going on between build steps defined in `cloudbuild.yaml`, there's a `gsutil` step copying the content of the /workspace container to a GCS bucket. Put your own bucket there or delete the whole step for this to work.

Once `cloudbuild.yaml` is configured to your liking, just run the script that's using the GCP SDK:

    build.sh
