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

#### Generating a Token for the K8s Dashboard
Created a shell script `~\gentoken`:
```
# Generate a MicroK8 access token
token=$(microk8s.kubectl -n kube-system get secret | grep default-token | cut -d " " -f1)
microk8s.kubectl -n kube-system describe secret $token
```
```
./gentoken
name:         default-token-b4m6z
Namespace:    kube-system
Labels:       <none>
Annotations:  kubernetes.io/service-account.name: default
              kubernetes.io/service-account.uid: 9602f557-8203-45bc-a5c1-049b57969d0b

Type:  kubernetes.io/service-account-token

Data
====
namespace:  11 bytes
token:      eyJhbGciOiJSUzI1NiIsImtpZCI6Imdoa0JlanZqYTVPZ25GTnRIZ2lmVFZTeFdXMHo4Sk55akVydF9WLTcxTE0ifQ.................................eyJpc3MiOiJrdWJlcm5ldGVzL3NlcnZpY2VhY2NvdW
ca.crt:     1103 bytes
```
Then past the certificate into the dashboard where it asks for a token on the login screen

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
[Deploy Wordpress Tutorial](https://webcloudpower.com/use-kubernetics-locally-with-microk8s/)

[Helmchart for how to deploying Jira and Postgress containers](https://github.com/stevehipwell/helm-charts/tree/master/charts/jira-software)

## Jekyll - Website authoring
