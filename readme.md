# Petclinic + Artifactory + Xray + Docker


## Step 1: Check compilation

This uses the maven-build.yml file to build the package each time a pull-request or commit to the "main" branch is made. The command run is `mvnw -B package` and will be successful if the build completes without error.



docker build --tag petclinic-app .