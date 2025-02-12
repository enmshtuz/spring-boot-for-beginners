# Basic CI/CD Pipeline for Java Applications


This repository contains a GitHub Actions workflow (main.yml) that defines a basic CI/CD pipeline for Java applications (Core Java and Java frameworks). The pipeline automates testing, building, and pushing your application as a Docker image to Docker Hub.

---

## Features

- **Run Unit Tests**: Automatically runs unit tests to ensure code quality.
- **Build Application**: Compiles and packages the application.
- **Build Docker Image**: Creates a Docker image containing the application build.
- **Push to Docker Hub**: Pushes the image to Docker Hub for further deployment.

---

## Setup Instructions

Follow these steps to set up and run the CI/CD pipeline:

1. **Add the Workflow File**:
   - Copy the `.github/workflows/main.yml` file to your project repository.

2. **Generate a Docker Hub Token**:
   - Log in to your Docker Hub account.
   - Navigate to **Account Settings** > **Security** > **Generate Access Token**.
   - Generate a token with read, write, delete permissions.

3. **Set Up GitHub Secrets**:
   - Go to your GitHub repository.
   - Navigate to **Settings** > **Secrets and variables** > **Actions**.
   - Add the following secrets:
     - `DOCKER_HUB_USERNAME`: Your Docker Hub username.
     - `DOCKER_HUB_ACCESS_TOKEN`: The Docker Hub access token you generated.

4. **Create Unit Tests**:
   - Create unit tests located in the src/test/java directory to fit your project.

5. **Specify Maven Configuration**
   - Copy pom.xml to your repository's root directory or edit pom.xml if you need to change Maven settings.

6. **Customize Dockerfile**
   - Create a Dockerfile tailored to your project. Make sure to include your build file (.jar/.war) in the image. View Dockerfile in this repository as guidance.

7. **Push to GitHub**:
   - Commit and push the files to your repository.

8. **Run the Pipeline**:
   - Go to the **Actions** tab in your GitHub repository.
   - Select the workflow and monitor its execution.

---

## Workflow Details

The `main.yml` workflow performs the following steps:

1. **Checkout Code**: Fetches the latest code from the repository.
2. **Set Up JDK**: Configures the Java environment.
3. **Run Unit Tests**: Executes unit tests to verify code functionality.
4. **Build Application**: Packages the Java application into a JAR/WAR file.
5. **Build Docker Image**: Creates a Docker image using the `Dockerfile`.
6. **Push to Docker Hub**: Uploads the Docker image to Docker Hub.
