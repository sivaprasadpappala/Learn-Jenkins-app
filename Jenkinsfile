pipeline {
agent any

```
stages {
    stage('Build') {
        agent {
            docker {
                image 'node:18-alpine'
                reuseNode true
                args "-e NPM_CONFIG_CACHE=${WORKSPACE}/.npm_cache"
            }
        }
        steps {
            sh '''
                mkdir -p ${WORKSPACE}/.npm_cache

                ls -la
                node --version
                npm --version

                npm ci
                npm run build

                ls -la
            '''
        }
    }
}
```

}
