---
sidebar_position: 1
---

# Guide

Below you'll find examples using Fetch API but you can JSONPlaceholder with any other language.

These examples were all properly tested in **POSTMAN**.

### [GET] - Getting a resource

This reference gets a specific resource from a database.

Schema
```js
// Endpoint
  https://jsonplaceholder.typicode.com/posts/{id}

// Query Parameters
  id: int()
  
// Response
{
  result: array()
}   
```

**Example** 

Request URL
```js
https://jsonplaceholder.typicode.com/posts/1
```

👇 *Output*
```js
{
    "userId": 1,
    "id": 1,
    "title": "sunt aut facere repellat provident occaecati excepturi optio reprehenderit",
    "body": "quia et suscipit\nsuscipit recusandae consequuntur expedita et cum\nreprehenderit molestiae ut ut quas totam\nnostrum rerum est autem sunt rem eveniet architecto"
}
```

### [GET] - Listing all resources

This reference shows how to list all resources from a database.

Schema
```js
// Endpoint
  https://jsonplaceholder.typicode.com/posts

// Doesn't have parameters

// Resposnse
{ 
  result: array()
}
```

**Example**

Request URL
```js
https://jsonplaceholder.typicode.com/posts
```

👇 *Output*
```js
[
    {
        "userId": 1,
        "id": 1,
        "title": "sunt aut facere repellat provident occaecati excepturi optio reprehenderit",
        "body": "quia et suscipit\nsuscipit recusandae consequuntur expedita et cum\nreprehenderit molestiae ut ut quas totam\nnostrum rerum est autem sunt rem eveniet architecto"
    },

/* ... */
    
    {
        "userId": 10,
        "id": 100,
        "title": "at nam consequatur ea labore ea harum",
        "body": "cupiditate quo est a modi nesciunt soluta\nipsa voluptas error itaque dicta in\nautem qui minus magnam et distinctio eum\naccusamus ratione error aut"
    }
]
```

### [POST] - Creating a resource

This reference shows how to use API to create a resource.

Schema
```js
// Endpoint
  https://jsonplaceholder.typicode.com/posts

// Body parameters
  title: str(), // Optional
  body: str(),  // Optional
  userId: int() // Optional

// Response
{
  result: array()
} 
```

**Example**

Request URL
```js
https://jsonplaceholder.typicode.com/posts
```

Body Parameters
```js
{
    "title": "foo",
    "body": "bar",
    "userId": "1"
}
```

👇 *Output*
```js
{
  id: 101,
  title: 'foo',
  body: 'bar',
  userId: 1
}
```
**Important**: resource will not be really updated on the server but it will be faked as if.

### [PUT] - Updating a resource

This reference shows how to update a resource of a database.

Schema
```js
// Endpoint
  https://jsonplaceholder.typicode.com/posts/{id}

// Query Parameters
  id: int()

// Body parameters
  id: int(), // Optional
  title: str(), // Optional
  body: str(), // Optional
  userId: int() // Optional

// Response
{
  result: array()
}  
```

**Example**

Request URL
```js
https://jsonplaceholder.typicode.com/posts/1
```

Body Parameters
```js
{    
    "id": "1",
    "title": "foo",
    "body": "bar",
    "userId": "5"
}
```

👇 *Output*
```js
{
    "id": 1,
    "title": "foo",
    "body": "bar",
    "userId": "5"
}
```
**Important**: resource will not be really updated on the server but it will be faked as if.


### [PATCH] - Patching a resource

This reference patches a resource from a database. 

Schema 
```js
// Endpoint
  https://jsonplaceholder.typicode.com/posts/{id}

// Query Parameters
  id: int()
  
// Body Parameters  
  title: str() // Optional

// Response
{
  result: array()
}
```

**Example**

Request URL
```js
https://jsonplaceholder.typicode.com/posts/12
```

Body Parameters
```js
{
  "title": "foo"
} 
```

👇 *Output*
```js
{
  "userId": 2,
  "id": 12,
  "title": "foo",
  "body": "itaque id aut magnam\npraesentium quia et ea odit et ea voluptas et\nsapiente quia nihil amet occaecati quia id voluptatem\nincidunt ea est distinctio odio"
}
```
**Important**: resource will not be really updated on the server but it will be faked as if.

### [DELETE] - Deleting a resource

This reference deletes a resource from the database.

Schema
```js
// Endpoint
  https://jsonplaceholder.typicode.com/posts/{id}

// Query Parameters
  id: int() // Required

// Response 
{
  result: array()
}
```

**Example**

Request URL
```js
https://jsonplaceholder.typicode.com/posts/9
```

👇 *Output*
```js
{}
```
**Important**: resource will not be really updated on the server but it will be faked as if.

### [GET] - Filtering resources

This reference shows how to filter resources by using query parameters.

Schema
```js
// Endpoint
  https://jsonplaceholder.typicode.com/posts{?userId{int}}

// Query Parameters
  userId: int() // Required

// Response
{
  result: array()
}
```

**Example**

Request URL
```js
https://jsonplaceholder.typicode.com/posts?userId=3
```

👇 *Output*
```js
// This will return all the posts that belong to the first user
[
    {
        "userId": 3,
        "id": 21,
        "title": "asperiores ea ipsam voluptatibus modi minima quia sint",
        "body": "repellat aliquid praesentium dolorem quo\nsed totam minus non itaque\nnihil labore molestiae sunt dolor eveniet hic recusandae veniam\ntempora et tenetur expedita sunt"
    },
    {
        "userId": 3,
        "id": 22,
        "title": "dolor sint quo a velit explicabo quia nam",
        "body": "eos qui et ipsum ipsam suscipit aut\nsed omnis non odio\nexpedita earum mollitia molestiae aut atque rem suscipit\nnam impedit esse"
    },
    {
        "userId": 3,
        "id": 23,
        "title": "maxime id vitae nihil numquam",
        "body": "veritatis unde neque eligendi\nquae quod architecto quo neque vitae\nest illo sit tempora doloremque fugit quod\net et vel beatae sequi ullam sed tenetur perspiciatis"
    },
    {
        "userId": 3,
        "id": 24,
        "title": "autem hic labore sunt dolores incidunt",
        "body": "enim et ex nulla\nomnis voluptas quia qui\nvoluptatem consequatur numquam aliquam sunt\ntotam recusandae id dignissimos aut sed asperiores deserunt"
    },
    {
        "userId": 3,
        "id": 25,
        "title": "rem alias distinctio quo quis",
        "body": "ullam consequatur ut\nomnis quis sit vel consequuntur\nipsa eligendi ipsum molestiae et omnis error nostrum\nmolestiae illo tempore quia et distinctio"
    },
    {
        "userId": 3,
        "id": 26,
        "title": "est et quae odit qui non",
        "body": "similique esse doloribus nihil accusamus\nomnis dolorem fuga consequuntur reprehenderit fugit recusandae temporibus\nperspiciatis cum ut laudantium\nomnis aut molestiae vel vero"
    },
    {
        "userId": 3,
        "id": 27,
        "title": "quasi id et eos tenetur aut quo autem",
        "body": "eum sed dolores ipsam sint possimus debitis occaecati\ndebitis qui qui et\nut placeat enim earum aut odit facilis\nconsequatur suscipit necessitatibus rerum sed inventore temporibus consequatur"
    },
    {
        "userId": 3,
        "id": 28,
        "title": "delectus ullam et corporis nulla voluptas sequi",
        "body": "non et quaerat ex quae ad maiores\nmaiores recusandae totam aut blanditiis mollitia quas illo\nut voluptatibus voluptatem\nsimilique nostrum eum"
    },
    {
        "userId": 3,
        "id": 29,
        "title": "iusto eius quod necessitatibus culpa ea",
        "body": "odit magnam ut saepe sed non qui\ntempora atque nihil\naccusamus illum doloribus illo dolor\neligendi repudiandae odit magni similique sed cum maiores"
    },
    {
        "userId": 3,
        "id": 30,
        "title": "a quo magni similique perferendis",
        "body": "alias dolor cumque\nimpedit blanditiis non eveniet odio maxime\nblanditiis amet eius quis tempora quia autem rem\na provident perspiciatis quia"
    }
]
```

### [GET] - Listing nested resources

This reference lists nested resources from a database.

Schema
```js
// Endpoint
  https://jsonplaceholder.typicode.com/posts/{id}/{category}

// Query Parameters
  id: int() // Required
  category: str() // Optional

// Response
  result: array()
```

**Example**

Request URL
```js
https://jsonplaceholder.typicode.com/posts/23/comments
```

👇 *Output*

Response
```js
[
    {
        "postId": 23,
        "id": 111,
        "name": "possimus facilis deleniti nemo atque voluptate",
        "email": "Stefan.Crist@duane.ca",
        "body": "ullam autem et\naccusantium quod sequi similique soluta explicabo ipsa\neius ratione quisquam sed et excepturi occaecati pariatur\nmolestiae ut reiciendis eum voluptatem sed"
    },
    {
        "postId": 23,
        "id": 112,
        "name": "dolore aut aspernatur est voluptate quia ipsam",
        "email": "Aniyah.Ortiz@monte.me",
        "body": "ut tempora deleniti quo molestiae eveniet provident earum occaecati\nest nesciunt ut pariatur ipsa voluptas voluptatem aperiam\nqui deleniti quibusdam voluptas molestiae facilis id iusto similique\ntempora aut qui"
    },
    {
        "postId": 23,
        "id": 113,
        "name": "sint quo debitis deleniti repellat",
        "email": "Laverna@rico.biz",
        "body": "voluptatem sint quia modi accusantium alias\nrecusandae rerum voluptatem aut sit et ut magnam\nvoluptas rerum odio quo labore voluptatem facere consequuntur\nut sit voluptatum hic distinctio"
    },
    {
        "postId": 23,
        "id": 114,
        "name": "optio et sunt non",
        "email": "Derek@hildegard.net",
        "body": "nihil labore qui\nquis dolor eveniet iste numquam\nporro velit incidunt\nlaboriosam asperiores aliquam facilis in et voluptas eveniet quasi"
    },
    {
        "postId": 23,
        "id": 115,
        "name": "occaecati dolorem eum in veniam quia quo reiciendis",
        "email": "Tyrell@abdullah.ca",
        "body": "laudantium tempore aut\nmaiores laborum fugit qui suscipit hic sint officiis corrupti\nofficiis eum optio cumque fuga sed voluptatibus similique\nsit consequuntur rerum commodi"
    }
]
```

The available nested routes are:

- /posts/1/comments
- /albums/1/photos
- /users/1/albums
- /users/1/todos
- /users/1/posts