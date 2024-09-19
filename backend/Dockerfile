# Use an official Python runtime as a parent image
FROM python:3.12-slim

# Set the working directory in the container
WORKDIR /app

# Install any needed packages 
RUN apt-get update && apt-get install -y \
    build-essential \
    libhdf5-dev \
    pkg-config \
    && rm -rf /var/lib/apt/lists/*

# Copy the requirements.txt file to install dependencies
COPY requirements.txt .

# Install any dependencies specified in requirements.txt
RUN pip install --no-cache-dir -r requirements.txt

# Copy the current directory contents into the container at /app
COPY . .

# Expose port 5000 to be accessible from outside the container
EXPOSE 5000

# Set the environment variable to tell Flask to run in production
ENV FLASK_ENV=production

# Set the default command to run the application
CMD ["flask", "run", "--host=0.0.0.0", "--port=5000"]