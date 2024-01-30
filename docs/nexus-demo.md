Nexus Demo
==========

## Objectives

1. Build docker image and push to local Nexus repository
2. Pull and run docker image from local Nexus repository

## Steps

1. Download & extract source

    ```sh
    curl -sL https://github.com/ausuwardi/docker-cowsay/archive/master.zip -o docker-cowsay.zip
    unzip docker-cowsay.zip
    ```

2. `cd` into directory and build. Replace '&lt;user&gt;' in the image tag with your name

    ```sh
    cd docker-cowsay
    docker build --rm -t nxdr-demo.parainfra.id/demo/<user>/cowsay:1.0.0
    ```

3. Log in to Nexus Docker registry. Enter 'docker.demo' as user when prompted, and the password you get from admin

    ```sh
    docker login nxdr-demo.parainfra.id
    ```

4. Push image to nxdr-demo.parainfra.id

    ```sh
    docker push nxdr-demo.parainfra.id/demo/<user>/cowsay:1.0.0
    ```

5. Delete local cache of image

    ```sh
    docker rmi nxdr-demo.parainfra.id/demo/<user>cowsay:1.0.0
    ```

6. Run Docker image from nxdr-demo registry

    ```sh
    docker run --rm nxdr-demo.parainfra.id/demo/<user>/cowsay:1.0.0 hello nexus demo
    ```


