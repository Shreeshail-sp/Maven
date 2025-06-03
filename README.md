pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/Shreeshail-sp/Maven.git'
            }
        }

        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
        }

        stage('Test') {
            steps {
                sh 'mvn test'
            }
        }
    }
}


git init                   # Initialize a new Git repository (if not already done)
git add .                  # Stage all files
git commit -m "Initial commit"   # Commit with a message
git branch -M main         # (Optional) Rename branch to 'main'
git remote add origin <url>  # (If pushing to GitHub or other remote)
git push -u origin main    # Push to remote
