# Python v3 base layer

# Official python3 image for Windows Server Core
#FROM python:3-windowsservercore

# Community-provided Nano Server image 
FROM stefanscherer/python-windows:3.6.1-nano  

# Set the working directory in the image's file system
WORKDIR /usr/src/app

# Copy everything in the host working directory to the container's
COPY . .

# Install code dependencies in requirements.txt
RUN pip install --no-cache-dir -r requirements.txt

# Indicate that the server will be listening on port 5000
EXPOSE 5000

# Set the default command to run the app
CMD [ "python", "./src/app.py" ]