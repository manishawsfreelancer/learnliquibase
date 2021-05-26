pipeline {
    agent any
    parameters {
    string defaultValue: 'jdbc:mysql://ecommercedb.csrmnme0xzyb.us-east-1.rds.amazonaws.com:3306/ecommerce_db', description: '', name: 'DB_URL', trim: false
    string defaultValue: 'admin', description: '', name: 'DB_username', trim: false
    string defaultValue: 'admin123', description: '', name: 'DB_password', trim: false
    string defaultValue: 'com.mysql.cj.jdbc.Driver', description: '', name: 'DB_driver', trim: false
    string defaultValue: 'changelog_Release1.mysql.xml', description: '', name: 'changelogfile', trim: false
    }
    stages {
        stage('Checkout the Git Repository') {
            steps {
                echo 'This step is already being carried out by Jenkins feault stage "Declarative: Checkout SCM"'
            }
        }
        stage('Pre-Check') {
            steps {
                echo 'Performing Pre-check conditions'
                sh '''
                { set +x; } 2>/dev/null
                cd liquibase_demo_project
                liquibase --version
                ls -la
                liquibase --url=${DB_URL} --username=${DB_username} --password=${DB_password} --changeLogFile=${changelogfile} status
                '''
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'

            }
        }
    }
}