# docker commands

**1. FROM**
Specifies the base image for your Docker container.
Every dockerfile must begin with a FROM instruction.
Example:

FROM python:3.9-slim
This sets the base image to a lightweight Python 3.9 image.

**2. RUN**
Executes commands inside the container during the build process.
Often used to install packages, update systems, or configure dependencies.
Example:
RUN apt-get update && apt-get install -y curl

**3. COPY**
Copies files or directories from the local system into the container.
Example:
COPY requirements.txt /app/

**4. ADD**
Similar to COPY but with additional features:
Can handle remote URLs.
Automatically extracts .tar files.
Example:
ADD archive.tar.gz /app/

**5. EXPOSE**
Declares the network ports the container listens on.
Does not publish the port; this is used as documentation.
Example:
EXPOSE 8080

**6. ENV (Environment)**
Sets environment variables in the container.
Syntax:
ENV <key>=<value>
Example:
ENV APP_ENV=production

**7. LABEL**
Adds metadata to the image for documentation or automation tools.
Example:
LABEL maintainer="dev@example.com"

**8. ARG**
Defines build-time variables that can be passed during the build process.
Example:
ARG VERSION=1.0
RUN echo "Building version $VERSION"

**9. ENTRYPOINT**
Defines the command that always runs when the container starts.
Example:
ENTRYPOINT ["python", "app.py"]

**10. USER**
Sets the user for running the container.
Example:
USER 1001

**11. WORKDIR**
Sets the working directory inside the container.
Example:
WORKDIR /app

**12. ONBUILD**
Specifies instructions that should execute when the image is used as a base for another .
Example:
ONBUILD COPY . /app/
