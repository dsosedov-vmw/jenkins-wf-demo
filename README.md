# Jenkins Demo

## Demo 0
Create Freestyle project
```bash
echo 'Hello Jenkins Demo 0!'
```

## Demo 1
Create Pipeline project
### Step 1
```groovy
pipeline {
    agent any

    stages {
        stage('Hello') {
            steps {
                sh 'echo "Hello Jenkins Demo 1!"'
            }
        }
    }
}
```
### Step 2
```groovy
pipeline {
    agent any

    stages {
        stage('Hello') {
            steps {
                echo 'Hello Jenkins Demo 1!'
            }
        }
    }
}
```
### Step 3
```groovy
pipeline {
    agent any

    environment {
        NAME = 'Jenkins'
    }

    stages {
        stage('Hello') {
            steps {
                echo "Hello $NAME Demo 1!"
            }
        }
    }
}
```
### Step 4
```groovy
pipeline {
    agent any

    environment {
        NAME = credentials('foo')
    }

    stages {
        stage('Hello') {
            steps {
                echo "Hello $NAME Demo 1!"
            }
        }
    }
}
```
### Step 5
Use Jenkinsfile
