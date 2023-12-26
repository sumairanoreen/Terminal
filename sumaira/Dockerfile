# Use a base image with a minimal web server
FROM alpine:3.5

#install python and pip
RUN apk add --update py2-pip

# install pipeline module needed by the python app
COPY requirement.txt /usr/src/app/
RUN pip install --no-cache-dir -r /usr/src/app/requirements.txt

#copy files required for the app to run
COPY app.py /usr/src/app/ 
COPY templates/index.html /usr/src/app/templates/

# tell the port number the container should expose
EXPOSE 5000

#run the application
CMD [ "python", "/usr/src/app/app.py" ]
