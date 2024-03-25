# Use a Node.js image based on Alpine for its lightweight nature
FROM node:16-alpine

# Set the working directory in the container
WORKDIR /app

# Copy application configuration files (package.json and package-lock.json) into the working directory
COPY package*.json ./

RUN npm config set unsafe-perm true

# Install project dependencies
RUN npm install

# Change permissions for the node_modules folder to allow writing by any user
RUN chmod -R 777 /app/

# Copy other project files and folders into the container's working directory
COPY . .

# Expose the port on which Vite runs by default (3000)
EXPOSE 5173

# Start the Vite development server
CMD ["npm", "run", "dev"]
