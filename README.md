# Simple Todo list's server based on JSON Server


## Instructions

Install dependencies

```bash
$ npm install
```

Start Server

```bash
$ npm start --watch db.json
```

Now if you go to [http://localhost:3000/lists/1](), you'll get

```json
{ id: 1, name: "test list" }
```

Also when doing requests, its good to know that
- If you make POST, PUT, PATCH or DELETE requests, changes will be automatically and safely saved to `db.json` using [lowdb](https://github.com/typicode/lowdb).
- Your request body JSON should be object enclosed, just like the GET output. (for example `{"name": "Foobar"}`)
- Id values are not mutable. Any `id` value in the body of your PUT or PATCH request wil be ignored. Only a value set in a POST request wil be respected, but only if not already taken.
- A POST, PUT or PATCH request should include a `Content-Type: application/json` header to use the JSON in the request body. Otherwise it will result in a 200 OK but without changes being made to the data.


## Routes

Based on the previous `db.json` file, here are all the default routes. 


```
GET    /lists
GET    /lists/1
GET    /lists/1/todos
POST   /lists
PUT    /lists/1
PATCH  /lists/1
DELETE /lists/1

GET    /todos
GET    /todos/1
PUT    /todos/1
PATCH  /todos/1
DELETE /todos/1

¿POST   /todos?
```

### Database

```
GET /db
```

### Homepage

Returns default index file or serves `./public` directory

```
GET /
```


## Extras

### POSTMAN collection

Following this link you can install a [POSTMAN](https://www.getpostman.com/) collection with some example API REST calls to this API:

[https://www.getpostman.com/collections/6a2704caca985e99a2dc](https://www.getpostman.com/collections/6a2704caca985e99a2dc)


### Alternative port

You can start JSON Server on other ports with the `--port` flag:

```bash
$ json-server --watch db.json --port 3004
```

## License

MIT - [Typicode](https://github.com/typicode)
