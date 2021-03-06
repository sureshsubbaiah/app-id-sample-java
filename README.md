# IBM Cloud App ID
Java Liberty Sample App Template for the IBM Cloud App ID service. The App ID Dashboard overwrites the Liberty/manifest.yml and Liberty/server.xml files with the user's information when they download a Java sample app. When downloaded, you can either run the application locally or in IBM Cloud.

[![IBM Cloud powered][img-ibmcloud-powered]][url-ibmcloud]
[![Java Badge][img-java-badge]][url-java-badge]
[![Travis][img-travis-master]][url-travis-master]
[![Coveralls][img-coveralls-master]][url-coveralls-master]
[![Codacy][img-codacy]][url-codacy]

[![GithubWatch][img-github-watchers]][url-github-watchers]
[![GithubStars][img-github-stars]][url-github-stars]
[![GithubForks][img-github-forks]][url-github-forks]

## Table of Contents
<!---
* [Contents](#contents)
-->
* [Requirements](#requirements)
* [Running Locally](#running-locally)
* [Running in IBM Cloud](#running-in-ibm-cloud)
* [License](#license)

<!---
## Contents
-->

## Requirements
* Java 8.x
* [Maven](https://maven.apache.org/download.cgi)

## Running Locally

Navigate to the WebApplication directory and run the following command:
```bash
./finalize.sh
```
Use the link http://localhost:9080/appidSample to load the web application in browser.

## Running in IBM Cloud

### Prerequisites
Before you begin, make sure that IBM Cloud CLI is installed.
For more information visit: https://console.bluemix.net/docs/cli/reference/bluemix_cli/get_started.html#getting-started.

### Deployment

**Important:** Before going live, remove https://localhost:9443/* from the list of web redirect URLs located in "Identity Providers" -> "Manage" page in the AppID dashboard.

1. Navigate to the WebApplication directory.

2. Generate your ‘war’ file and upload it using the following command:

  `mvn clean install`

3. Navigate to the Liberty directory.

4. Login to IBM Cloud.

  `bx login https://api.{{domain}}`

5. Target a Cloud Foundry organization and space in which you have at least Developer role access:

  Use `bx target --cf` to target Cloud Foundry org/space interactively.

6. Bind the sample app to the instance of App ID:

  `bx resource service-alias-create "appIDInstanceName-alias" --instance-name "appIDInstanceName" -s {{space}}`

7. Deploy the sample application to IBM Cloud.

  `bx app push`

8. Open your IBM Cloud app route in the browser.

## License

Copyright (c) 2018 IBM Corporation

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.

[img-ibmcloud-powered]: https://img.shields.io/badge/ibm%20cloud-powered-blue.svg
[url-ibmcloud]: https://www.ibm.com/cloud/

[img-java-badge]: https://img.shields.io/badge/platform-java-lightgrey.svg?style=flat
[url-java-badge]: https://developer.java.com/index.html

[img-travis-master]: https://travis-ci.org/ibm-cloud-security/app-id-sample-java.svg?branch=master
[url-travis-master]: https://travis-ci.org/ibm-cloud-security/app-id-sample-java?branch=master

[img-coveralls-master]: https://coveralls.io/repos/github/ibm-cloud-security/app-id-sample-java/badge.svg
[url-coveralls-master]: https://coveralls.io/github/ibm-cloud-security/app-id-sample-java

[img-codacy]: https://api.codacy.com/project/badge/Grade/435ead3215584ffc9e530d504e240fca
[url-codacy]: https://www.codacy.com/app/ibm-cloud-security/app-id-sample-java

[img-github-watchers]: https://img.shields.io/github/watchers/ibm-cloud-security/app-id-sample-java.svg?style=social&label=Watch
[url-github-watchers]: https://github.com/ibm-cloud-security/app-id-sample-java/watchers
[img-github-stars]: https://img.shields.io/github/stars/ibm-cloud-security/app-id-sample-java.svg?style=social&label=Star
[url-github-stars]: https://github.com/ibm-cloud-security/app-id-sample-java/stargazers
[img-github-forks]: https://img.shields.io/github/forks/ibm-cloud-security/app-id-sample-java.svg?style=social&label=Fork
[url-github-forks]: https://github.com/ibm-cloud-security/app-id-sample-java/network
