# Use latest Python runtime as a parent image
FROM python:3.12-slim

# Set the working directory to /app and copy current dir
WORKDIR /app
#copy the requirements file to the container
COPY requirements.txt .

# Install python dependencies
RUN pip install --no-cache-dir -r requirements.txt
# Copy the current directory contents into the container at /app
COPY . .

# Make port 9696 available to the world outside this container
EXPOSE 9696

#run the application when the container launches
ENTRYPOINT ["gunicorn", "--bind=0.0.0.0:9696", "main:app"]