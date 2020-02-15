---
layout: post
title:  "What I Learnt Today - microk8s helm jekyll"
date:   2020-02-15 14:20:25 +0000
categories: updates 
---
## MicroK8s Installation

Install using SNAP - _don't forget the --classic_

```sudo snap install microk8s --classic```

[Ubuntu Quick Start](https://ubuntu.com/tutorials/install-a-local-kubernetes-with-microk8s#1-overview)

## Helm - Kubernetes automation

[Helm Snapcraft](https://snapcraft.io/helm)

```snap install helm --classic```

### Getting Started resources
Watch [Building Helm Charts from the Ground Up](https://www.youtube.com/watch?time_continue=1388&v=vQX5nokoqrQ&feature=emb_title)

[Helm Docs](https://helm.sh/docs/)

### How to make Helm work with microk8s
* Enable the Helm service 
```microk8s.enable helm```

* Export the microk8s config

```
sudo mkdir /etc/microk8s
sudo microk8s.config > /etc/microk8s/microk8s.conf
export KUBECONFIG=/etc/microk8s/microk8s.conf
```

* Example usage

```helm --kubeconfig /etc/microk8s/microk8s.conf ls```

[notes](https://worklifenotes.com/2020/01/22/how-to-make-microk8s-work-with-helm/)



### ToDo
[Deploy Wordpress](https://webcloudpower.com/use-kubernetics-locally-with-microk8s/)

[Deploy Jira and Postgress](https://github.com/stevehipwell/helm-charts/tree/master/charts/jira-software)

## Jekyll - Website authoring
