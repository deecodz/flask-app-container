# Use Python slim image for smaller size while maintaining compatibility
FROM python:3.9-slim

# Create working directory
WORKDIR /app

# Copy requirements first to leverage Docker cache
COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt

# Copy application code
COPY main.py .
COPY .env .

# Copy service account key
COPY service-account-key.json .
RUN chmod 600 service-account-key.json

# Adding port 
EXPOSE 5000

# Adding a command to run python file
CMD ["python", "./main.py"]
