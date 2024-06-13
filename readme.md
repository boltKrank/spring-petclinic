# Petclinic + Artifactory + Xray + Docker


Each time the code is commited to the GitHub repository, a GitHub action (referenced in docker-build.yaml) will run what's written in the Dockerfile.

In this file Maven dependancies are resolved with the command "./mvnw dependency:resolve". 

A maven build of the package is made and pushed to the image.

The image is then pushed to a Docker repostiory hosted on Artifactory.

Adding `jf xr curl -XGET api/v1/release_bundle_v2_versions` to the github action was attempted to get the data back, but this is still work in progress.