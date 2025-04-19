# Helm Charts
The package manager for Kubernetes

Helm is the best way to find, share, and use software built for Kubernetes.

Its a homebrew of Kubernetes in mac, or apt for kubernetes in linux 

> Helm helps you manage Kubernetes applications — Helm Charts help you define, install, and upgrade even the most complex Kubernetes application.

> Charts are easy to create, version, share, and publish

> Helm is a graduated project in the CNCF and is maintained by the Helm community

> Helm Packages are referred to as *Charts* - deployable unit for Kubernetes bound applications. 

## Helm started in 2015
![](images/2025-04-19-13-50-34.png)

## Helm users Semantic Versioning 
```
https://semver.org/spec/v2.0.0.html
```
- When you break existing API, increment the **major** version  
- When you add a feature, increment the **minor** version  
- For bugs or non-feature changes, increment the **patch** version  

![](images/2025-04-19-13-52-33.png)

## Security - Helm Provenance and Integrity / signing charts
- Provenance - place of origin 
- Provenance records are stored in provenance files, which are stored alongside a packaged chart. For example, if a chart is named myapp-1.2.3.tgz, its provenance file will be myapp-1.2.3.tgz.prov
- Integrity / signing charts 
- Provenance files are generated at packaging time (helm package --sign ...), and can be checked by multiple commands, notably helm install --verify

## Supported for all 3 major Platforms 
![](images/2025-04-19-14-03-46.png)

## Website 
```
https://helm.sh/
```

## Artifacts 
```
https://artifacthub.io/
```
![](images/2025-04-19-14-48-06.png)

### Search a repo from command prompt helm 
```
helm search hub <name-of-chart>
```


## Install 

### MAC
```
brew install helm
```

### Windows
```
choco install kubernetes-helm
```

### Install from Source 
```
https://helm.sh/docs/intro/install/
```

## Current Version 

```
v3
```

## Helm chart from 1000 feet 

![](images/2025-04-19-14-08-30.png)

![](images/2025-04-19-14-09-05.png)

### Chart.yaml 
- Mainly for metadata
- Also can add dependencies 

![](images/2025-04-19-14-10-55.png)

### Values.yaml
- specify default settings for your chart

![](images/2025-04-19-14-12-12.png)

![](images/2025-04-19-14-25-42.png)

#### Override chart values from left to right

![](images/2025-04-19-14-36-01.png)


### Template directory 
- Anything here is treated as yaml template
- it has GO-LANG templating language
- Take the values.yaml file, apply to this template and convert it in kube yaml

![](images/2025-04-19-14-15-00.png)

![](images/2025-04-19-14-25-06.png)

![](images/2025-04-19-14-28-14.png)




### Templates / helper file (optional)
- this is for section of yaml that you may want to repete it in all the templates 
- like a specific label for that application

![](images/2025-04-19-14-17-09.png)

### Templates / Test 
- any file which has test in the name is treated as helm test file 
- once you install the application using helm then you can use these files to check, eg:- if my databas is up 

![](images/2025-04-19-14-19-22.png)

### Templates / NOTES.txt
- Once the application is completely installed, it will pring the message
- how to use the application
- application is installed
- we can add ASCII turtle 

![](images/2025-04-19-14-23-17.png)

## Installing a Helm chart 
- Can install from local developer machine where chart is present
- Can intall from chart repository 

![](images/2025-04-19-14-34-03.png)

## Check Release status 
- Also we get the notes here from the template/NOTES.txt
![](images/2025-04-19-14-37-52.png)

## list what is running
![](images/2025-04-19-14-40-09.png)

## Upgrade a specific helm release
```
helm upgrade myrelease ./myapp --set image.tag=1.16.1-alpine
```

![](images/2025-04-19-14-41-23.png)

## Rollback to previous version 

```
helm rollback myrelease 1
```

![](images/2025-04-19-14-44-09.png)

## Delete a release

![](images/2025-04-19-14-44-42.png)

