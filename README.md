# Folder Monitoring System

## What does it do?
This project contains a **scheduled task** which periodically monitors the file content of the audit folder: **src/main/resources/checkFolder** notifying when a new file has been added, and **two REST web services API** for querying and exploring the content of the aforementioned folder.
Note that the System takes care only of the direct files of the folder, so any files belonging to subfolders are not considered.

For all the services, the file information provided are: 
* path;
* name;
* dimension;
* last change datetime;
* the Hash MD5

The scheduling of the local monitoring scheduled task has been configured every **3 seconds**, and the ouput log information are written in a local Json file under the following path:
**src/main/resources/logs/logFile.json**

## Framework
The project is build with **spring boot**, which **contains an integrated tomcat**
The external dependencies are specified in the **pom.xml** file
Under the package which ends with **to** there are the objects for the mapping of the output response, with all the descpriptive info of the file
In **src/main/resources/static** there is the html page **index.html**, which can be viewed under the default Url of the microservice

#Домашнее задание
1. Создать директорию сервис. В ней создать два интерфейса: IFileInfoWritable и IFileMonitoring и два класса: FileInfoJsonToWrite и FileMonitoringService
2. Cоздать директорию web.rest. В ней создать класс FMonitoringSysController c двумя эйндпойнтами (GET-запросы): ("/filesinfo") - метод getFilesInfo; ("/file") - метод getFileFromMD5
3. Запустить полученное приложение (скомпилировать)
