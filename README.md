# Jenkins Demo

## Demo 0
```bash
echo 'Hello Jenkins Demo 0!'
```

## Demo 1
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
                echo 'Hello $NAME Demo 1!'
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
                sh """
                    if [ $NAME == 'Jenkins' ]; then
                        echo "Hello Jenkins Demo 1!"
                    else
                        echo "Hello $NAME Demo 1!"
                    fi
                """
            }
        }
    }
}
```
### Step 5
```groovy
pipeline {
    agent any

    environment {
        NAME = credentials('foo')
    }

    stages {
        stage('Hello') {
            steps {
                sh """
                    if [ $NAME == 'Jenkins' ]; then
                        echo "Hello Jenkins Demo 1!"
                    else
                        echo "Hello $NAME Demo 1!"
                    fi
                """
            }
        }
        stage('Build') {
            steps {
                echo 'Building...'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing...'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying...'
            }
        }
    }
}
```
