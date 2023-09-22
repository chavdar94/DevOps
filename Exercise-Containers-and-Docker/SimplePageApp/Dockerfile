FROM python:3.8-slim-buster

WORKDIR /app

# Set enviorment variables
ENV PYTHONDONTWRITEBYTECODE 1
ENV PYTHONUNBUFFERED 1

# Install requeirments.txt
COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt

# Copy project
COPY . .

# Set staticfiles dir
RUN mkdir /app/staticfiles

# Copy the staticfiles
COPY static /app/staticfiles

# Expose port the app runs on
EXPOSE 8000

# Run command to start the application
CMD [ "gunicorn", "SimplePageApp.wsgi:application", "--bind", "0.0.0.0:8000" ]
