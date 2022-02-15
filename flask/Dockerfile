# Use Python 3.9
FROM python:3.9

# Set the working directory for the container to a folder called app
WORKDIR /app

# Copy the current directory contents tinto the container att /app
ADD . /app

# Install dependencies
RUN pip install -r requirements.txt

# Start the uswgi appserver
CMD ["uwsgi", "app.ini"]
