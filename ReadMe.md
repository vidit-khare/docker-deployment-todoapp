# Docker Deployment Todo App

This repository contains a simple Todo application that is containerized using Docker and Docker Compose. The application is designed to demonstrate how to deploy a web application using Docker and automate the deployment process using Azure Pipelines.

## Table of Contents

- Prerequisites
- Installation
- Usage
- CI/CD with Azure Pipelines
- Contributing
- License

## Prerequisites

Before you begin, ensure you have met the following requirements:

- You have installed Docker and Docker Compose if you want to run it directly.

For running it using Azure DevOps pipeline. Please Ensure following.

- You have an Azure DevOps account and have set up a project.
- You have a basic understanding of Docker, Docker Compose, and Azure YAML concepts.

Please refer this article to setup and run it using Azure DevOps pipeline.

## Installation

1. **Clone the repository:**

    ```sh
    git clone https://github.com/vidit-khare/docker-deployment-todoapp.git
    ```

    ```sh
    cd docker-deployment-todoapp
    ```

2. **Define Environment Variables**

This project uses a `.env` file to manage environment variables. Follow these steps to set up your environment variables:

- **Create a `.env` file in the root directory of the project:**

    ```sh
    touch .env
    ```

- **Add your environment variables to the `.env` file:**

    ```env
    POSTGRES_DB=your_database_name
    POSTGRES_USER=your_database_user
    POSTGRES_PASSWORD=your_database_password
    ```

#### Using Environment Variables in Docker Compose

Docker Compose will automatically load the variables from the `.env` file. Ensure your `docker-compose.yml` file references these variables:


3. **Build and run the Docker containers using Docker Compose:**

    ```sh
    docker-compose up --build -d
    ```

## Usage

Once the containers are running, you can access the Todo application by navigating to `http://localhost:5001` in your web browser.

### Stopping the Containers

To stop the running containers, use the following command:

```sh
docker-compose down
```

## CI/CD with Azure Pipelines

This project uses Azure Pipelines for continuous integration and continuous deployment.

### Setting Up Azure Pipelines

1. **Create a new pipeline in your Azure DevOps project.**
2. **Configure the pipeline to use the `azure-pipelines.yml` file from this repository.**
3. **Add your environment variables as pipeline variables:**
    - Navigate to your pipeline in Azure DevOps.
    - Go to the **Variables** tab.
    - Add the variables `POSTGRES_DB`, `POSTGRES_USER`, and `POSTGRES_PASSWORD` with their respective values. 
4. **Run the pipeline to build and deploy the application.**

The `azure-pipelines.yml` file contains the necessary steps to build the Docker images, push them to a container registry, and deploy the application.

## Contributing

Contributions are always welcome! Please follow these steps to contribute:

1. **Fork the repository.**
2. **Create a new branch:**

    ```sh
    git checkout -b feature-branch
    ```

3. **Make your changes.**
4. **Commit your changes:**

    ```sh
    git commit -m 'Add some feature'
    ```

5. **Push to the branch:**

    ```sh
    git push origin feature-branch
    ```

6. **Open a pull request.**

## License

This project is licensed under the MIT License. See the LICENSE file for details.
