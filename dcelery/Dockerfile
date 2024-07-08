# Use the official Python image from the Docker Hub
FROM python:3.12.3

# Set the working directory in the container
WORKDIR /usr/src/app

# Prevent Python from writing .pyc files
ENV PYTHONDONTWRITEBYTECODE 1

ENV PYTHONRUNBUFFERED 1

RUN pip install --upgrade pip

# Copy the requirements file into the container
COPY requirements.txt /usr/src/app/requirements.txt

# Install the dependencies
RUN pip install -r requirements.txt

COPY ./entrypoint.sh /usr/src/app/entrypoint.sh

# Copy the entire project into the container
COPY . /usr/src/app/

ENTRYPOINT [ "/usr/src/app/entrypoint.sh" ]

# # Expose the port the app runs on
# EXPOSE 8000

# # Define the command to run the app
# CMD ["sh", "-c", "python manage.py migrate && python create_superuser.py && python manage.py runserver 0.0.0.0:8000"]
