FROM python:3.10-slim-buster

# Inside container
# Make a new folder inside container
WORKDIR /backend-flask

# Outside container -> Inside container
# This contains the libraries we want to install to run the app
COPY requirements.txt requirements.txt

# Inside container
# Install the Python libraries used for the app
RUN pip3 install -r requirements.txt

# Outside container -> Inside container
# . means everything in the current directory
# First period "." /backend-flask (outside container)
# Second period "." /backend-flask (inside container)
COPY . .

# Set environment  variables (env vars)
# Inside container and will remain set when the container is run
ENV FLASK_ENV=development

EXPOSE ${PORT}

# CMD (command)
# python3 -m flask run --host=0.0.0.0 --port=4567
CMD [ "python3", "-m" , "flask", "run", "--host=0.0.0.0", "--port=4567"]