# Use an official Node.js runtime as a parent image
FROM node:18-alpine

# Set the working directory inside the container
WORKDIR /app

# Copy package.json and package-lock.json to install dependencies
COPY package*.json ./

# Install the dependencies
RUN npm install

# Copy the rest of the application files into the container
COPY . .

# Build the React application for production
RUN npm run build

# Install a simple HTTP server to serve static files
RUN npm install -g serve

# Expose port 3000 for the app
EXPOSE 3000

# Command to serve the application on port 3000
CMD ["serve", "-s", "build", "-l", "3000"]