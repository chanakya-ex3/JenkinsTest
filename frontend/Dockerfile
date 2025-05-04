# Step 1: Use an Nginx base image
FROM nginx:alpine

# Step 2: Set working directory
WORKDIR /usr/share/nginx/html

# Step 3: Remove the default static files
RUN rm -rf ./*

# Step 4: Copy your static website files into the Nginx html directory
COPY . .

# Step 5: Copy custom nginx configuration
COPY nginx.conf /etc/nginx/conf.d/default.conf

# Expose port 8000 instead of default 80
EXPOSE 8000

# Nginx will start automatically via CMD in base image
