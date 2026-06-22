FROM node:16-alpine as builder
# Set the working directory
WORKDIR /usr/app
# Copy the package.json and install dependencies
COPY package.json ./
# Run npm install to install dependencies
RUN npm install
# Copy the rest of the application code
COPY . .
# Build the React application for production
RUN npm run build

FROM nginx:alpine
EXPOSE 3000
# Copy the default nginx configuration file to the container
COPY nginx/default.conf /etc/nginx/conf.d/default.conf
# Copy the built React application from the builder stage to the nginx html directory   
 COPY --from=builder /usr/app/build /usr/share/nginx/html
