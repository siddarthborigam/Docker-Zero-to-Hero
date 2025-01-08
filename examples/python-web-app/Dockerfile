# Use Ubuntu as the base image
FROM ubuntu:latest

# Set the working directory
WORKDIR /app

# Copy application files
COPY requirements.txt /app
COPY devops /app

# Install necessary system packages
RUN apt-get update && \
    apt-get install -y python3 python3-pip python3-venv && \
    apt-get clean

# Create and activate a Python virtual environment
RUN python3 -m venv /app/venv
ENV PATH="/app/venv/bin:$PATH"

# Upgrade pip and install dependencies inside the virtual environment
RUN pip install --upgrade pip && \
    pip install -r requirements.txt

# Set entry point and command
ENTRYPOINT ["python3"]
CMD ["manage.py", "runserver", "0.0.0.0:8000"]



#FROM ubuntu
#
#WORKDIR /app
#
#COPY requirements.txt /app
#COPY devops /app
#
#RUN apt-get update && \
#    apt-get install -y python3 python3-pip && \
#    pip install -r requirements.txt && \
#    cd devops
#
#ENTRYPOINT ["python3"]
#CMD ["manage.py", "runserver", "0.0.0.0:8000"]




