# 1. Start from an existing Python image
FROM python:3.10-slim

# 2. Set working directory inside container
WORKDIR /app

# 3. Copy dependency list into container
COPY requirements.txt .

# 4. Install required Python packages
RUN pip install --no-cache-dir -r requirements.txt

# 5. Copy application code into container
COPY app.py .

# 6. Inform Docker the app uses port 5000
EXPOSE 5000

# 7. Command to run when container starts
CMD ["python", "app.py"]
