pipeline {
    agent any

    stages {
        stage('Query 1') {
            when { changeset "1.sql" }
            steps {
                sh "curl 'https://raw.githubusercontent.com/Vanhall/sf-jenkins-11-5/main/1.sql' > /tmp/1.sql"
                sh "mysql --user rfamro --host mysql-rfam-public.ebi.ac.uk --port 4497 --database Rfam < /tmp/1.sql"
            }
        }
        stage('Query 2') {
            when { changeset "2.sql" }
            steps {
                sh "curl 'https://raw.githubusercontent.com/Vanhall/sf-jenkins-11-5/main/2.sql' > /tmp/2.sql"
                sh "mysql --user rfamro --host mysql-rfam-public.ebi.ac.uk --port 4497 --database Rfam < /tmp/2.sql"
            }
        }
    }
}
