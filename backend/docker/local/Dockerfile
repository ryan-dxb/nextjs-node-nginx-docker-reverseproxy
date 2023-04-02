# ARG NODE_VERSION=16-alpine3.12

# FROM node:${NODE_VERSION}

# LABEL name="NEXT Auth"
# LABEL license="MIT"
# LABEL description="NEXT Auth"

# ENV NODE_ENV=development

# ARG APP_HOME=/app

# WORKDIR ${APP_HOME}

# # Run docker as non-root user (user = invoice and group = invoice)
# RUN addgroup --system invoice \
#     && adduser --system --ingroup invoice invoice

# # Copy package.json and package-lock.json
# COPY package*.json ./

# # Install dependencies
# RUN npm install

# # Copy all files
# COPY . ${APP_HOME}

# # Change ownership of the app directory to the non-root user
# COPY --chown=invoice:invoice . ${APP_HOME}

# # Run docker as non-root user (user = invoice and group = invoice) -R for recursive
# RUN chown -R invoice:invoice ${APP_HOME}

# # Switch to non-root user
# USER invoice

# EXPOSE 5000

# CMD ["npm", "run", "dev"]


# Set the base image to Node.js
FROM node:16-alpine3.12

# Set the working directory to /app
WORKDIR /app

# Copy the package.json and package-lock.json files to the container
COPY package*.json ./

# Install dependencies
RUN npm install

# Copy the rest of the application code to the container
COPY . .

# Expose port 3000
EXPOSE 3000

# Start the application
CMD ["npm", "run", "dev"]