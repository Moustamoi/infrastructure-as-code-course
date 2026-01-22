FROM node:20-slim

WORKDIR /app

# Copy backend package files
COPY package*.json ./

# Install dependencies
RUN npm install

# Copy backend source code
COPY src ./src

# Expose backend port
EXPOSE 3000

# Start backend server
CMD ["npm", "start"]
