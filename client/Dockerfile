# Use official node image
FROM node:16

# Set working directory
WORKDIR /usr/src/app

# Copy package.json and install dependencies
COPY package*.json ./
RUN npm install

# Copy the entire project
COPY . .

# Build the project
RUN npm run build

# Expose Nuxt.js default port
EXPOSE 3000

# Start the app
CMD ["npm", "run", "start"]

