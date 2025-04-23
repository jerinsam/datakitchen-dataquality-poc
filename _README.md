### **Test Data Kitchen for Data Quality**
In this POC, Open-Source Data Kitchen service is used to understand the execution of Data Quality on the source data. For this DataKitchen's TestGen service is used.

#### What is Data Kitchen
DataKitchen is a service for DataOps, streamlining and automating data analytics workflows. It enables data teams to:
- Orchestrate Data Pipelines
- Ensure Data Quality

DataKitchen offers multiple services - 
- **DataOps Data Quality TestGen** - DataKitchen's DataOps Data Quality TestGen is a data quality tool that profiles databases and generates tests.
- **DataOps Observability** - DataOps Observability monitors every data journey from data source to customer value, from any team development environment into production, across every tool, team, environment, and customer
- **DataOps Automation** - DataKitchen's DataOps Automation helps orchestrate tools, technologies, workflows, operations, tests, and environments


#### Data Kitchen TestGen installation

In this POC, DataKitchen's TestGen service is used. Follow below steps to install the service - 

**Refer below URL for installation steps** - 
- https://docs.datakitchen.io/articles/?hsCtaAttrib=185465269285#!dataops-testgen-help/install-testgen-open-source

**Prerequisites**  - 
- Python3
- Docker and Docker Compose

**Environment** - 
- Windows with WSL Ubuntu enabled
- Python3, Docker and Docker Compose installed in WSL Ubuntu


**Installation Steps** - 
Execute below commands in WSL shell - 

- *Download the latest version of dk-installer*
    ```
    curl -o dk-installer.py 'https://raw.githubusercontent.com/DataKitchen/data-observability-installer/main/dk-installer.py'
    ```
    After the successful execution of above step, a python file will be downloaded which will be further used to downlaod the docker image and start the DataKitchen's TestGen docker container.
    
    <br>

- *Run the install command usin the python file created in above step, this will download the docker compose files and will start the docker container for DataKitchen TestGen and Postgres*
    ```
    python3 dk-installer.py tg install
    ```
    After the successful execution of above step - 
    - DataKitchen's TestGen docker image and Postgres docker image will be downloaed and will start the containers.
    - A UserName and Password will be generated and can be seen on the console and also saved in file "dk-tg-credentials.txt". This credential is required to log into the TestGen's UI.
    - DataKitchen's TestGen UI can be accessed using URL "http://localhost:8501", This info can also be found in file "dk-tg-credentials.txt".

    <br>

- *Run the demo setup command, this will create a DB in Postgres and loads dummy data with connection in DataKetchen's TestGen UI*
    ```
    python3 dk-installer.py tg run-demo
    ```
    After the successful execution of above step - 
    - This will create a DB in Postgres and loads dummy data with connection in DataKetchen's TestGen UI

    <br>
    
- *Open TestGen UI using URL http://localhost:8501 and explore the UI* 
   Features in UI - 
   - Data profiling on Database Tables
   - Apply automatic Data Quality rules on Tables 

    <br>

- *Manage TestGen and Postgres Docker Containers*  - 
   TestGen and Postgres Dockers Containers and Images can be managed using Docker CLI commands. Refer github repo https://github.com/jerinsam/docker-learn-hands-on to understand the basics of Docker.


#### Important Links
- https://datakitchen.io/dataops-observability-product/
- https://docs.datakitchen.io/articles/?hsCtaAttrib=185465269285#!dataops-testgen-help/install-testgen-open-source
- https://docs.datakitchen.io/articles/#!dataops-observability-help/install-observability-open-source