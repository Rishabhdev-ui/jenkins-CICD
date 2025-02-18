FROM jenkins/jenkins:lts

# Install Docker inside Jenkins container
USER root
RUN apt-get update && apt-get install -y docker.io

# Set Jenkins to run Docker
USER jenkins
