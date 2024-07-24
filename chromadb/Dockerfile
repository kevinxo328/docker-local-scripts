# Base image
FROM node:18-slim

# Install git
RUN apt-get update && apt-get install -y git

# Set working directory
WORKDIR /app

# Clone the repository
RUN git clone https://github.com/thakkaryash94/chroma-ui.git .

# Install dependencies
RUN npm install

# Expose the port the app runs on
EXPOSE 3000

# Command to run the application
CMD ["npm", "run", "dev"]