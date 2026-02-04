# 1. Use official Python image as base
FROM python:3.12-slim

# 2. Set working directory inside the container
WORKDIR /app

# 3. Copy only requirements first (to leverage Docker cache)
COPY requirements.txt .

# 4. Install dependencies
RUN pip install --no-cache-dir -r requirements.txt

# 5. Copy the rest of the application code
COPY . .

# 6. Expose port 5000 so the container can be accessed from host
EXPOSE 5000

# 7. Command to run the app when the container starts
CMD ["python", "app.py"]
