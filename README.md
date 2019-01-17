## Demo - demonstrates an application and tests

#### dependencies: 
    Java 8.  
    Postgresql

It *has* to be Java 8.  Don't use Java 10, it will error out because Mockito doesn't work with Java 10.

Configure Postgresql using the steps at CONFIGURE POSTGRESQL in [jenkins_box_guide.txt](https://github.com/7ep/demo/blob/with_database/docs/jenkins_box_guide.txt).
Succinctly, you want to have a database called "training", and you want access to it.

#### To build with tests:
On Linux

    ./gradlew clean build

On Windows

    gradlew clean build

#### To run:
On Linux

    ./gradlew appRun

On Windows

    gradlew appRun
    
#### If you want to make it sing

Follow the directions to [create a Jenkins box](https://github.com/7ep/demo/blob/with_database/docs/jenkins_box_guide.txt) and [a UI-testing-box](https://github.com/7ep/demo/blob/with_database/docs/ui_test_box.txt), per the instructions
in docs.  

Features:
* Instructions for setting up virtual machines (with VirtualBox).
* A fully functioning demonstration CI/CD pipeline using Jenkins.
* Beginnings of a pretty neat micro-ORM (See PersistenceLayer.java and SqlData.java).
* Uses Gretty (https://github.com/akhikhl/gretty) which allows us to hot swap Java code at runtime.
* Incorporates static analysis using SonarQube
* Reviews security of the dependencies on a nightly basis using Dependency Check
* Disallows use of null (unless you provide an annotation), preventing a whole class of errors.
* A nice head start of good tests of various types - unit tests, integration tests, automated acceptance tests, UI tests

Note: I've stored an appliance for running
 the pipeline [on Dropbox](https://www.dropbox.com/s/k7eb9esw2jvglhp/Demo_Pipeline_and_test_box_Appliance.ova?dl=0).
 The Readme for the appliance is [here](https://www.dropbox.com/s/d45b04iy9qelyo1/README.docx?dl=0)

Screenshots:
![alt Cucumber report](https://raw.githubusercontent.com/7ep/demo/with_database/screenshots/cucumber_report.png)
![Feature file](https://raw.githubusercontent.com/7ep/demo/with_database/screenshots/feature_file.png)
![Jenkins pipeline](https://raw.githubusercontent.com/7ep/demo/with_database/screenshots/jenkins_pipeline.png)
![Webapp](https://raw.githubusercontent.com/7ep/demo/with_database/screenshots/webapp.png)
![Zap attach proxy](https://raw.githubusercontent.com/7ep/demo/with_database/screenshots/zap.png)
![SonarQube analysis](https://raw.githubusercontent.com/7ep/demo/with_database/screenshots/sonar.png)
