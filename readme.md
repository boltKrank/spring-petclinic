# Petclinic + Artifactory + Xray + Docker


Each time the code is commited to the GitHub repository, a GitHub action (referenced in docker-build.yaml) will run what's written in the Dockerfile.

In this file Maven dependancies are resolved with the command "./mvnw dependency:resolve". 

A maven build of the package is made and pushed to the image.

The image is then pushed to a Docker repostiory hosted on Artifactory.

Adding `jf xr curl -XGET api/v1/release_bundle_v2_versions` to the github action was attempted to get the data back, but this is still work in progress.

Once this is done, run the following command to test the application:

`docker run -p 8080:8080 <JFROG_ID>.jfrog.io/pet-clinic-docker/pet-clinic-image:11`

If you don't want to run it and just wish to pull the image you can do the same with

`docker pull <JFROG_ID>.jfrog.io/pet-clinic-docker/pet-clinic-image:11`

The tag is based on the image number - which is viewable from the "Actions" sub-menu in GitHub. 

Also, since Artifactory has a virtual integration with Docker Hub, you can run it like a Docker hosted repository, whilst managing your images in Artifactory.

This is very useful, as it will allow you to deploy and test multiple versions just by changing that tag number.

