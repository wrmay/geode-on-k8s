# Setup

This is a development environment for docker images and
it uses ansible-container.  To get ansible container to work you will first
need to install special versions of some packages.  I recommend using
[virtualenv](https://virtualenv.pypa.io).  


```
virtualenv pyenv
. pyenv/bin/activate
```

Install the following pip packages.  Note that it was necessary to actually
downgrade pip.

 ```
 pip install --force-reinstall pip==9.0.3
 pip install ansible-container[docker,k8s]
 pip install docker==2.7.0
 ```

# Usage

Build the image.

```
ansible-container build
```

Push the image to dockerhub.  This is rather finicky.  After trying several
things, this is what worked:

```
ansible-container push --push-to=https://docker.io/DOCKERHUN_USER  --username=DOCKERHUB_USER --password=MY_PASSWORD

# replace DOCKERHUB_USER and MY_PASSWORD with your information !
```

# Notes on Using VMWare PKS (formerly VKE)

- go to the console at vke.cloud.vmware.com
- click on "Developer Center" and follow instructions to get vke set up
- create a "Smart Cluster" and run `vke cluster auth setup <cluster-name>` to
point kubectl at the cluster
