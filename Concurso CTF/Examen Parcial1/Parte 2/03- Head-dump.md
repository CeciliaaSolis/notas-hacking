
## Descripción

*Welcome to the challenge! In this challenge, you will explore a web application and find an endpoint that exposes a file containing a hidden flag.The application is a simple blog website where you can read articles about various topics, including an article about API Documentation. Your goal is to explore the application and find the endpoint that generates files holding the server’s memory, where a secret flag is hidden.The website is running [picoCTF News](http://verbal-sleep.picoctf.net:53129/).*


## Pistas

*Explore backend development with us*

*The head was dumped.*
## Solución


```
## picoCTF News API 1.0.0 

OAS 3.0

Welcome to the picoCTF News API documentation! This documentation provides a detailed overview of the available API endpoints for managing and retrieving news posts.

### [Free](http://verbal-sleep.picoctf.net:53129/api-docs/#/Free)

API endpoints for navigating the website.

GET

[/](http://verbal-sleep.picoctf.net:53129/api-docs/#/Free/get_)

Welcome page

#### Parameters

Try it out

No parameters

#### Responses

|Code|Description|Links|
|---|---|---|
|200|Returns a welcome message.|_No links_|

GET

[/about](http://verbal-sleep.picoctf.net:53129/api-docs/#/Free/get_about)

About Us

#### Parameters

Try it out

No parameters

#### Responses

|Code|Description|Links|
|---|---|---|
|200|Returns information about us.|_No links_|

GET

[/services](http://verbal-sleep.picoctf.net:53129/api-docs/#/Free/get_services)

Services

#### Parameters

Try it out

No parameters

#### Responses

|Code|Description|Links|
|---|---|---|
|200|Returns a list of services.|_No links_|

### [Posts](http://verbal-sleep.picoctf.net:53129/api-docs/#/Posts)

API endpoints for managing posts.

GET

[/api/posts](http://verbal-sleep.picoctf.net:53129/api-docs/#/Posts/get_api_posts)

Get all posts

#### Parameters

Try it out

No parameters

#### Responses

|Code|Description|Links|
|---|---|---|
|200|Returns a list of all posts.<br><br>Media type<br><br>application/json<br><br>Controls `Accept` header.<br><br>- Example Value<br>- Schema<br><br>```json<br>[<br>  {<br>    "id": "1",<br>    "title": "My First Post",<br>    "content": "This is the content of my first post.",<br>    "author": "John Doe",<br>    "createdAt": "2024-07-02T00:00:00Z",<br>    "updatedAt": "2024-07-02T00:00:00Z"<br>  }<br>]<br>```|_No links_|

POST

[/api/posts](http://verbal-sleep.picoctf.net:53129/api-docs/#/Posts/post_api_posts)

Create a new post

#### Parameters

Try it out

No parameters

#### Request body

application/json

- Example Value
- Schema

```json
{
  "title": "My New Post",
  "content": "Content of the new post.",
  "author": "Alice"
  


#### Responses

|Code|Description|Links|
|---|---|---|
|201|Post created successfully.<br><br>Media type<br><br>application/json<br><br>Controls `Accept` header.<br><br>- Example Value<br>- Schema<br><br>```json<br>{<br>  "id": "3",<br>  "title": "My New Post",<br>  "content": "Content of the new post.",<br>  "author": "Alice",<br>  "createdAt": "2024-07-02T00:00:00Z",<br>  "updatedAt": "2024-07-02T00:00:00Z"<br>}<br>```|_No links_|

GET

[/api/posts/{id}](http://verbal-sleep.picoctf.net:53129/api-docs/#/Posts/get_api_posts__id_)

Get a post by ID

#### Parameters

Try it out

|Name|Description|
|---|---|
|id *<br><br>string<br><br>(path)|The ID of the post to retrieve|

#### Responses

|Code|Description|Links|
|---|---|---|
|200|Returns a post by ID.<br><br>Media type<br><br>application/json<br><br>Controls `Accept` header.<br><br>- Example Value<br>- Schema<br><br>```json<br>{<br>  "id": "1",<br>  "title": "My First Post",<br>  "content": "This is the content of my first post.",<br>  "author": "John Doe",<br>  "createdAt": "2024-07-02T00:00:00Z",<br>  "updatedAt": "2024-07-02T00:00:00Z"<br>}<br>```|_No links_|
|404|Post not found.|_No links_|

PUT

[/api/posts/{id}](http://verbal-sleep.picoctf.net:53129/api-docs/#/Posts/put_api_posts__id_)

Update a post by ID

#### Parameters

Try it out

|Name|Description|
|---|---|
|id *<br><br>string<br><br>(path)|The ID of the post to update|

#### Request body

application/json

- Example Value
- Schema

```json
{
  "title": "Updated Title",
  "content": "Updated content of the post.",
  "author": "John Doe"
}


#### Responses

|Code|Description|Links|
|---|---|---|
|200|Post updated successfully.<br><br>Media type<br><br>application/json<br><br>Controls `Accept` header.<br><br>- Example Value<br>- Schema<br><br>```json<br>{<br>  "id": "1",<br>  "title": "Updated Title",<br>  "content": "Updated content of the post.",<br>  "author": "John Doe",<br>  "createdAt": "2024-07-02T00:00:00Z",<br>  "updatedAt": "2024-07-02T00:00:00Z"<br>}<br>```|_No links_|
|404|Post not found.|_No links_|

DELETE

[/api/posts/{id}](http://verbal-sleep.picoctf.net:53129/api-docs/#/Posts/delete_api_posts__id_)

Delete a post by ID

#### Parameters

Try it out

|Name|Description|
|---|---|
|id *<br><br>string<br><br>(path)|The ID of the post to delete|

#### Responses

|Code|Description|Links|
|---|---|---|
|200|Post deleted successfully.|_No links_|
|404|Post not found.|_No links_|

### [Diagnosing](http://verbal-sleep.picoctf.net:53129/api-docs/#/Diagnosing)

GET

[/heapdump](http://verbal-sleep.picoctf.net:53129/api-docs/#/Diagnosing/get_heapdump)

Diagnosing the memory allocation.

#### Parameters

Cancel

No parameters

ExecuteClear

#### Responses

#### Curl

```bash
curl -X 'GET' \
  'http://verbal-sleep.picoctf.net:53129/heapdump' \
  -H 'accept: */*'


#### Request URL

http://verbal-sleep.picoctf.net:53129/heapdump

#### Server response

|Code|Details|
|---|---|
|200|##### Response body<br><br>[Download file](blob:http://verbal-sleep.picoctf.net:53129/c7b4b4df-7b2e-4452-93f7-bd6a129b6609)<br><br>##### Response headers<br><br> accept-ranges: bytes cache-control: public,max-age=0  connection: keep-alive  content-disposition: attachment; filename="heapdump-1744598289053.heapsnapshot"  content-length: 9076973  content-type: application/octet-stream  date: Mon,14 Apr 2025 02:38:11 GMT  etag: W/"8a80ed-1963229547b"  keep-alive: timeout=5  last-modified: Mon,14 Apr 2025 02:38:11 GMT x-powered-by: Express|

#### Responses

| Code | Description                         | Links      |
| ---- | ----------------------------------- | ---------- |
| 200  | Returns a memory allocation status. | _No links_ |
```
picoCTF{Pat!3nt_15_Th3_K3y_305d5b9a}
## Notas Adicionales 

*Encontramos que hay un apidocs que nos muestra la documentacion, al entrar hasta abajo nos aparece lo que buscamos head dump, lo ejectutamos y nos da un archivo para descargar, lo descargamos, lo abrimos y con ctrl +b buscamos pico y enter y nos sale la bandera.*
## Referencias 
http://verbal-sleep.picoctf.net:53129/
http://verbal-sleep.picoctf.net:53129/api-docs

