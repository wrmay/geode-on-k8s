This is a development environment for docker images and 
it uses ansible-container.  Be sure to activate the virtual 
environment:

```
. env/bin/activate
```

Notes:

- had to downgrade pip to install ansible-container

 ```
 pip install --force-reinstall pip==9.0.3 
 pip install ansible-container[docker,k8s]
 pip install docker==2.7.0
 ``` 
