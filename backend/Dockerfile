# Use official Node.js image
FROM node:18-slim

# Set working directory
WORKDIR /app

# Copy package.json and package-lock.json first for better caching
COPY package*.json ./

# Install dependencies
RUN npm install

# Copy the rest of the project files
COPY . .

# Expose the port your Express app listens on
EXPOSE 5000

# Command to run your Express app
CMD ["node", "index.js"]
