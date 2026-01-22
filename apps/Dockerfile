FROM node:20-slim

WORKDIR /app

# Copy the entire app directory
COPY . .

# Install dependencies for both frontend and backend
RUN npm install --prefix backend && npm install --prefix frontend

# Build the frontend
RUN npm run build --prefix frontend

# Expose ports
EXPOSE 5000 5173

# Start backend server
CMD ["npm", "start", "--prefix", "backend"]