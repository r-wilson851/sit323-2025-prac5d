# sit323-2025-prac5d



At a  high level, to deploy the microservice to the cloud we need to: 
1.	Signup for Google Cloud via a web browser and set up a private container registry (via following the instructions on the website) 
2.	Authenticate/ Sign  in  into google cloud via your terminal 
3.	Take your Dockerfile , tag it then ‘push’ it to google cloud repo via google cloud terminal
4.	To confirm it’s working you can then ‘pull’ it from the google cloud & then run it via mapping to a unique port and testing the app 


## DETAILED STEPS:
1.	In Google Cloud on web browser follow instructions to sign up 
2.	Download Google Cloud  Command Line Interface (follow instructions for your operating system)	https://cloud.google.com/sdk/docs/install
3.	Sign in / authenticate via Googe Cloud CLI & set it up with docker
   - 	`gcloud auth configure-docker australia-southeast1-docker.pkg.dev`
5.	Set the project ID in your CLI via taking the project ID in console.google.com and copying it into the following command 
 	- `gcloud config set project <projectID>` 
6.	enable the artifact registry via: 
  -	`gcloud services enable artifactregistry.googleapis.com`
7.	Tag the image with your gcp project url 
    -	`docker tag  <your-image-name> australia-southeast1-docker.pkg.dev/<rest-of-your-GCP-url>`
8.	Push the image to GCP 
   -	`docker push <your-image-name> australia-southeast1-docker.pkg.dev/<rest-of-your-GCP-url>`
9.	Pull & run the image to test if it works 
  -	`docker pull <your-image-name> australia-southeast1-docker.pkg.dev/<rest-of-your-GCP-url>`
  - `docker run -p 8080:3000 <your-image-name> australia-southeast1-docker.pkg.dev/<rest-of-your-GCP-url>`
10.	View your localhost to your mapped port, e.g. localhost:3030 in your web browser and see if your app works at that url 
