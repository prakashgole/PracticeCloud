# PracticeCloud
Repository to practice cloud computing
Adding an sample node js application to create webserver using cloud run

gcloud config set compute/region asia-south1
LOCATION="asia-south1"

git clone https://github.com/prakashgole/PracticeCloud


Package.json -- Contains JSON variables
the file above contains a start script command and a dependency on the Express web application framework.

index.js --> Main JS file that contains code which creates a basic web server that listens on the port defined by the PORT environment variable. 

Dockerfile is needed to containerize the sample app

Build container image using cloud build command
gcloud builds submit --tag gcr.io/$GOOGLE_CLOUD_PROJECT/helloworld

It executes a series of build steps, where each build step is run in a Docker container to produce your application container (or other artifacts) and push it to Cloud Registry


Deploying your containerized application to Cloud Run is done using the following command 

gcloud run deploy --image gcr.io/$GOOGLE_CLOUD_PROJECT/helloworld --allow-unauthenticated --region=$LOCATION


