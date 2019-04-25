# OpenShift Custom Jenkins

This is a reference repo containing the structure to follow for customizing OpenShift Jenkins Images.

## BuildConfig to customize the Jenkins Image 

```
apiVersion: v1
kind: BuildConfig
metadata:
  name: custom-jenkins-build
spec:
  source:                       
    git:
      uri: https://github.com/williamcaban/openshift-custom-jenkins.git
    type: Git
  strategy:                     
    sourceStrategy:
      from:
        kind: ImageStreamTag
        name: jenkins:latest
        namespace: openshift
    type: Source
  output:                       
    to:
      kind: ImageStreamTag
      name: custom-jenkins:latest
```
