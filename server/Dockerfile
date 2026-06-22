FROM node:14.4.0-alpine
# Set the working directory
WORKDIR /usr/app
# Copy the package.json and install dependencies
COPY package.json ./

RUN npm install 

# Copy the rest of the application code
COPY . .

# Start the application
CMD ["npm", "run", "start"] 