# DataTransformer WEB API

DataTransformer is a Web API solution for uploading a csv file and writing it MSSQL Database and JSON file simultaneously.

The solution has 5 project:

## Project 1 - DataTransformerAPI

The actual interface through which clients can work with our API was implemented through ASP.NET Core and Entity Framework Core Code First.
Project for controllers, mapping between domain model and API model, API configuration (DB and JSON DBContext configuration).

### Controllers Folder

This folder is for controller classes. There is only one controller "FileUploaderController" for uploading csv file.

#### Upload File Request URL: 

POST http://localhost:52825/api/fileuploader

#### Upload File Request BODY 

{
	"Path":"C:\\Users\\etimtez\\Desktop\\iru-assignment-2018.csv"
}

### APITransformerExecuter Folder

This folder is for executing for fileuploader, calling Business projects classess for converting API models to Logic (Domain) and and Logic (Domain) models to Data Models.

## Project 2 - DataTransformer.Api.Model

Project for API models.

## DataTransformer.Business

Project for all logic processes.

### FileReader Folder
This folder is for reading file operation.

### APIModelToDomainModelConverter Folder
This folder is for converting CSV files to Domain models.

### DomainModelToDataModelConverter Folder
This folder is for convering Domain models to Data models for storage interaction.

### DataModelToDomainModelConverter Folder
This folder is for convering Data models to Domain models for API.


## Project 3 - DataTransformer.Data.Model

Project for Data models.

## Project 4 - DataTransformer.Api.Access

Projects for interfaces and implementations of Repository pattern and Unit Of Work pattern, implementation Database Contexts for DB and JSON and accessing storages.

### Context Folder 
This folder is for implementation of DBContexts.

### Repository and UnitOfWork Folders 
These folders are for implementation of Repository and Unit Of Work patterns.

### DataStorageExecuter Folder 
This folder is for every data models database accessing by using their own repositories and their own dbcontexts. Dependecy Injection was used this implementations.


