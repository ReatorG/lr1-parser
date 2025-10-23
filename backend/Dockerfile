# Use an official Python image with apt-get enabled
FROM python:3.11-slim

# Install system Graphviz package
RUN apt-get update && apt-get install -y graphviz && rm -rf /var/lib/apt/lists/*

# Create app directory
WORKDIR /app

# Copy requirements and install dependencies
COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt

# Copy your FastAPI app code
COPY . .

# Expose port (Render uses $PORT internally)
ENV PORT=10000
EXPOSE 10000

# Run FastAPI with Uvicorn
CMD ["uvicorn", "main:app", "--host", "0.0.0.0", "--port", "10000"]
