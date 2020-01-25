# Postman Api Demo (Reqres)

This is a sample framework using postman to automate test to the reqres api, this framework has also being integrated with newman to aid with integration to a CI/CD pipeline.

## Folder Structure Explanation


[GLOBAL SETUP]() - This folder contains a script which is executed first and is responsible for any global set up required before the first test is run,a function called commonTests has being created and its purpose is to create a set of reusable tests that can be applied to all api requests in the entire collection. 

[GET Test]() - This folder has a set up method performs the same function as the global set up but is more geared towards more specific scenarios related to the get endpoints

The rest of the test folders follow the same pattern 

[GLOBAL TEARDOWN]() - This folder contains clean up tasks for an entire collection like unsetting environment variables that have being created.

## Installation
```python
a simple git clone of the repo should pull down the v2 json format
which can be run by newman or postsman inbuilt collection runner
```

## Usage

In this section i will list out a 
few of the postman features that have being implemented 

and where they where implemented.
#### Random User API
An api called random user was used to generate random user details like name and email which was used in the post request the code can be found in [POST TEST/POST SET UP - Pre-request Script tab]()
#### Varibles
The variables created by the random api where saved in an environment variables and passed into the post body request the code can be found in
[POST TEST/register with invalid credentials - Body tab]()
#### Conditional Workflow
Postman has a feature where instead of making use of its default linear workflow of script execution you can change it, this feature has being implemented in [POST TEST/register with invalid credentials - line 9 in the Test tab]() where if the test returns a 400 because the user details is not allowed a request with the right user credentials gets executed next.
#### Newman 
This is a bit hard to show, but newman is a commandline tool which has being created to help in executing tests in a commandline which makes it possible to add postman test to a CI/CD pipeline.
#### Html Extra Reports
Has being used to create a good looking and understandable html report which is customisable 






## License
[MIT](https://choosealicense.com/licenses/mit/)
