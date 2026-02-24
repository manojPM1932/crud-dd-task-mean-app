FROM node:18-alpine

# Create app directory
WORKDIR /app

# Copy package files
COPY package*.json ./

# Install dependencies
RUN npm install --only=production

# Copy source
COPY . .

# Expose port
EXPOSE 8000

# Start server
CMD ["node", "server.js"]