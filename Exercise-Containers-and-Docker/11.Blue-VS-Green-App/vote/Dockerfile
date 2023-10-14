# Using official python runtime base image
FROM python

# Set the application directory
WORKDIR /app

COPY vote/requirements.txt .

# Install our requirements.txt
RUN pip install -r requirements.txt

# Copy our code from the current folder to /app inside the container
COPY vote/. .

# Make port 80 available for links and/or publish
EXPOSE 80

# Define our command to be run when launching the container
ENTRYPOINT python app.py