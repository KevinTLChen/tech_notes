# This Dockerfile is to be run as one of drone pipeline steps
# That means static assets from builder stage are persisted in Drone workspace.
# Within the image build process, use relative path './' to fetch source
# All we need to do in this docker image build are:
# - 1. Copy nginx configuration file from ./.nginx/nginx.conf
# - 2. Copy static assets from ./build

FROM nginx:1.22.0

# Set working directory (within container)
WORKDIR /app

# Remove default nginx static assets
RUN rm -rf /usr/share/nginx/html/*

# Copy config nginx
COPY ./.nginx/nginx.conf /etc/nginx/nginx.conf

# Copy static assets from builder stage
COPY ./build /usr/share/nginx/html

# Containers run nginx with global directives and daemon off
ENTRYPOINT ["nginx", "-g", "daemon off;"]