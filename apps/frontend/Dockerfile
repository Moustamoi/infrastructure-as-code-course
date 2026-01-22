FROM node:20-slim as builder

WORKDIR /app

# Copy frontend package files
COPY package*.json ./

# Install dependencies
RUN npm install

# Copy frontend source code
COPY src ./src
COPY public ./public
COPY index.html ./
COPY vite.config.js ./

# Build the frontend
RUN npm run build

# Production stage
FROM node:20-slim

WORKDIR /app

# Install serve to serve static files
RUN npm install -g serve

# Copy built files from builder
COPY --from=builder /app/dist ./dist

# Expose frontend port
EXPOSE 5173

# Serve the built frontend
CMD ["serve", "-s", "dist", "-l", "5173"]
