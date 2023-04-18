# Use an official Node.js base image
FROM node:14

# Set the working directory in the container
WORKDIR /hello-world

# Copy package.json and package-lock.json to the working directory
COPY package*.json ./

# Install dependencies
RUN npm ci

# Copy the rest of the application code to the working directory
COPY . .

# Build the React app
RUN npm run build

# Install serve to serve the built React app
RUN npm install -g serve

# Expose the port the app will run on
EXPOSE 3000

# Start the app using serve
CMD ["serve", "-s", "build", "-l", "3000"]
