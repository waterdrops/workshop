# 3. Push image into private docker registry.
- A [private docker registry](https://github.com/docker/distribution) has been created on 10.128.3.11:5000. Since it is within our private office network, we will use it as an insecure registry for our docker images.
- Please follow [official instructions](https://docs.docker.com/registry/insecure/) and configure your docker engine to access our private registry.
- Example procedures after you have successfully configured your docker engine.
  - $ docker pull gosharplite/duck:v4
  - $ docker tag gosharplite/duck:v4 10.128.3.11:5000/duck:v4
  - $ docker push 10.128.3.11:5000/duck:v4
  - $ docker rmi 10.128.3.11:5000/duck:v4
  - $ docker pull 10.128.3.11:5000/duck:v4
  - $ docker run --publish 8093:8092 10.128.3.11:5000/duck:v4 -port=8092