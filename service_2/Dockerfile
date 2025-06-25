# Use a minimal Python base image
FROM python:3.11-slim

# Set the working directory
WORKDIR /app

# Copy the project files into the container
COPY . .

# Install uv and Flask
# Also install build dependencies needed for uv if not already cached
RUN pip install --upgrade pip \
    && pip install --no-cache-dir uv flask

# Expose the port the Flask app runs on
EXPOSE 8002

# Run the Flask app using uv
CMD ["uv", "run", "app.py"]
