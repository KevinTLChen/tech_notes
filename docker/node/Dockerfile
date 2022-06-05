# syntax=docker/dockerfile:1
FROM node:14.19.3-buster as build
WORKDIR /vuexy-react-app
COPY package.json .
COPY yarn.lock .
RUN yarn install
COPY . .
CMD [ "yarn", "start" ]
EXPOSE 3000

# FROM creates a layer from the node:14.19.3-buster Docker image.
# WORKDIR sets the working directory for any RUN, CMD, ENTRYPOINT, COPY and ADD instructions that follow it in the Dockerfile
# COPY adds files from your Docker client's current directory.
# RUN builds your application with yarn.
# CMD specifies what command to run within the container.

# The CMD instruction has three forms:
# CMD ["executable","param1","param2"] (exec form, this is the preferred form)
# CMD ["param1","param2"] (as default parameters to ENTRYPOINT)
# CMD command param1 param2 (shell form)

# unzip full-version.zip
# cd vuexy-react-app
# docker build -t vuexy-react-app:8.1.0 .

# Tag local vuexy-react-app:8.1.0 image with an additional tag - local repository address
# docker tag vuexy-react-app:8.1.0 localhost:5000/vuexy-react-app:8.1.0

# Log in to the local registry
# docker login --username kevinchen localhost:5000

# Push image to the local repository
# docker push localhost:5000/vuexy-react-app:8.1.0

# Remove local images
# docker image remove vuexy-react-app:8.1.0
# docker image remove localhost:5000/vuexy-react-app:8.1.0

# Pull vuexy-react-app:8.1.0 image from local repository
# docker pull localhost:5000/vuexy-react-app:8.1.0

# run container
# docker run --name vuexy-react-app -dp 3000:3000 localhost:5000/vuexy-react-app:8.1.0