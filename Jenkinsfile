pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/ujjawalpandey0901-sys/devops-html-form.git'
            }
        }

        stage('Test HTML Form') {
            steps {
                script {
                    def html = readFile('index.html')

                    if (!html.contains('<form')) {
                        error('Form not found')
                    }

                    if (!html.contains('name="name"')) {
                        error('Name field not found')
                    }

                    if (!html.contains('name="email"')) {
                        error('Email field not found')
                    }

                    if (!html.contains('name="contact"')) {
                        error('Contact field not found')
                    }

                    if (!html.contains('type="submit"')) {
                        error('Submit button not found')
                    }

                    echo 'All HTML form tests passed successfully!'
                }
            }
        }
    }
}
