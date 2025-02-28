# Flask on Docker with Postgres

## Overview

This repository contains a step-by-step tutorial for configuring a Flask application to run on Docker with Postgres. It is enhanced for production environments by integrating Nginx and Gunicorn to efficiently serve static and user-uploaded media files. Below is a short animated GIF showcasing the process of uploading an image:

![Image Upload Process](images/oogway.gif)

## Build Instructions

Follow these steps to build and run the services:

1. **Clone the Repository**

   ```bash
   git clone https://github.com/JWise16/flask-on-docker.git 
   cd flask-on-docker
   ```

2. **Build Images (development)**

    ```bash
    docker compose -f docker-compose.yml up -d --build
    ```

2. **Build Images (prod)**

    ```bash
     docker compose -f docker-compose.prod.yml up -d --build
     ```

3. **Useage**

    Hello world sanity check
    ```bash
    curl http://localhost:6969/
    ```

    Upload an image
    ```bash
    curl -F "file=@noodles2.jpg" http://localhost:6969/upload
    ``

    View uploaded image at `http://localhost:6969/media/noodles2.jpg`

4. **Tear Down**

    ```bash
    docker compose down -v
    ```
