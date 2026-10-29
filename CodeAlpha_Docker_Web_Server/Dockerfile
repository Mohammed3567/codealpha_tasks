# Small, pinned base image that already contains the nginx web server
FROM nginx:1.27-alpine

# Put our web page where nginx serves files from
COPY index.html /usr/share/nginx/html/index.html

# nginx listens on port 80 inside the container
EXPOSE 80

# Docker will mark the container "healthy" only if the page answers
HEALTHCHECK --interval=15s --timeout=3s --start-period=5s --retries=3 \
  CMD wget -qO- http://127.0.0.1/ > /dev/null || exit 1
