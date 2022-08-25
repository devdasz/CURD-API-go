# CURD-API-go
A CURD api based on Go lang.
This is a example of movie library where one can get movie details
For this project fake db is made with slice(like array). There are 5 basic operation in this example. One can get all movies list, Create a new movie, Update a existing movie by id, Read a movie by id, and Delete a movie by id.

## Get movie list
---
Call a Get request to **/movies**. 

Client will get a list/array  of json object like below.

_Server response_

```
[
    {
        "id": "1",
        "isbn": "438227",
        "title": "Movie one",
        "director": {
            "firstname": "jhon",
            "lastname": "Doe"
        }
    },
    {
        "id": "2",
        "isbn": "45455",
        "title": "Movie Two",
        "director": {
            "firstname": "Steve",
            "lastname": "Smith"
        }
    }
]
```

## Create a new movie 
---
Call a POST request to **/movie** with below json object in body.

```
{
        
        "isbn": "438228",
        "title": "Movie three",
        "director": {
            "firstname": "jhon",
            "lastname": "Doe"
        }
}
```

__Note:__ id is not necessary to create a new movie as it will genereate a randoom movie name and you can check it via server response. 

_Server response_

```
{
    "id": "131847",
    "isbn": "438228",
    "title": "Movie three",
    "director": {
        "firstname": "jhon",
        "lastname": "Doe"
    }
}
```

## Update a existing movie
---
Call a PUT request to **/movie{id}** with below json object in body.

```
{
        
        "isbn": "438227",
        "title": "Movie one-Updated",
        "director": {
            "firstname": "jhon",
            "lastname": "Doe"
        }
}
```


**Note:**  Partial update is not valid.




_Server response_
```
{
    "id": "727887",
    "isbn": "438227",
    "title": "Movie one-Updated",
    "director": {
        "firstname": "jhon",
        "lastname": "Doe"
    }
}
```
## Read a existing movie details
---
Call a Get request to **/movie/{id}** (here id is movie id). 

Client will get a json object like below.
```
{
    "id": "1",
    "isbn": "438227",
    "title": "Movie one",
    "director": {
        "firstname": "jhon",
        "lastname": "Doe"
    }
}
```

## Delete a existing movie
---
To delete a movie details , a Delete request should be called with id to  **/movie/{id}** (here id is movie id.

Server will response back with remaining movies list.

_Server response_
```
[
    {
        "id": "2",
        "isbn": "45455",
        "title": "Movie Two",
        "director": {
            "firstname": "Steve",
            "lastname": "Smith"
        }
    },
  
  
]
```