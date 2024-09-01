# Continuous-Integration-Pipeline-Using-Jenkins-Nexus-SonarQube-and-Slack

This project demonstrates a Continuous Integration (CI) pipeline implemented using Jenkins, Nexus, SonarQube, and Slack. The pipeline is triggered automatically upon new commits to the GitHub repository and performs various stages including building, code analysis, packaging, and artifact deployment.

![Continuous Integration Using Jenkins,Nexus,Sonarqube  Slack](https://github.com/user-attachments/assets/78c34a4e-a494-4ba2-bb13-dfefd332285d)

## Prerequisites

Before setting up the pipeline, ensure you have the following:

1. **Jenkins Server** - Installed on an EC2 instance.
2. **SonarQube Server** - Installed on an EC2 instance for code quality analysis.
3. **Nexus Repository** - Installed on an EC2 instance for artifact management.

![Screenshot 2024-09-01 130921](https://github.com/user-attachments/assets/89acfa4e-3f53-4592-8cbf-bd556883bd67)
## Jenkins Setup

1. **Jenkins Installation**: Set up Jenkins on an EC2 instance.
2. **Plugins Installed**:
   - **Maven Integration**: For building Java projects.
   - **GitHub Integration**: For connecting Jenkins to your GitHub repository.
   - **SonarQube Scanner**: For code quality analysis.
   - **Slack Notification**: For sending pipeline results to Slack channels.

## Pipeline Configuration

### 1. **GitHub Integration**
   - The pipeline is connected to a GitHub repository.
   - A **GitHub Webhook** is configured to trigger the Jenkins pipeline automatically whenever a new commit is pushed to the repository.

### 2. **Build Process**
   - Jenkins fetches the latest code from the GitHub repository.
   - The project is built using **Maven**, and the resulting artifact is packaged.

### 3. **Code Quality Analysis**
   - The **SonarQube Scanner** plugin is used to analyze the code for quality issues.
   - Code analysis results are sent back to Jenkins and can be viewed within the Jenkins dashboard.

### 4. **Artifact Deployment**
   - Once the build and code analysis stages are complete, the artifact is uploaded to the **Nexus Repository**.
   - This ensures that all built artifacts are stored in a central location for future use.

### 5. **Notifications**
   - **Slack Notifications** are configured to send the outcome of each pipeline run to a specified Slack channel. This helps keep the development team informed of the pipeline status.

###  **Jenkins**
![Screenshot 2024-09-01 130646](https://github.com/user-attachments/assets/3fc8d239-2a8d-42c3-b0d9-4a12bc66cc1d)


###  **SonarQube**
![Screenshot 2024-09-01 123422](https://github.com/user-attachments/assets/a5c4834b-375f-4586-9414-ba4ec776f558)


###  **Nexus Repository**
![Screenshot 2024-09-01 130709](https://github.com/user-attachments/assets/f24f5bbf-a4fb-47bd-82f3-03fc5ca0d383)

## Usage

1. **Triggering the Pipeline**: The pipeline is automatically triggered by new commits to the GitHub repository due to the configured GitHub webhook.

2. **Monitoring Pipeline Progress**: You can monitor the progress of the pipeline in Jenkins, where you’ll see stages such as fetching code, building, running unit tests, performing code analysis, and deploying artifacts.

3. **Notifications**: Upon completion of each stage, notifications are sent to the configured Slack channel, indicating success or failure.

## Conclusion

This setup provides an automated CI pipeline that ensures code is continuously integrated, analyzed for quality, and packaged for deployment, with full visibility provided through Slack notifications.
