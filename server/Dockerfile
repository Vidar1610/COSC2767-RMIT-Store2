# Use official Node.js LTS image
FROM node:20-alpine

# Set working directory
WORKDIR /app

# Copy package.json and package-lock.json
COPY package*.json ./

# Install dependencies
RUN npm install --production

# Copy all backend source code
COPY . .

# Expose port your server listens on
EXPOSE 5000

# Start the server
CMD ["node", "index.js"]
