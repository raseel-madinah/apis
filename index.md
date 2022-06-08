## Welcome to Raseel API development guidelines

This document illustrates most of the rules to follow by backend developers and integrators to write the APIs.

### Terminologies
- **Resource** is an object with associated data, represents something, and a set of methods can operate on it.
- **Collections** are set of resources.

### The 9 main rules

Let's talk about the main 9 best practises about REST APIs developement.
# Rule 1: Use Json
JSON format is the standard for data transmission for both the payload and the response.

**Example:**
```markdown
{
  "data": [
    {
      "id": 121,
      "title": "Rest APIs for dummies"
    }
  ]
}
```
# Rule 2: Use Nouns for Resource Identification
**Nouns** are used for naming the resources in the endpoint paths. The actions on the resources are defined by a few standard HTTP methods such as (GET, POST, PUT, PATCH, and DELETE).

Here are some examples to show how the endpoints should look like:

```markdown
GET /books  -Returns a list of books
GET /books/{id}  -Returns a specific book
POST /books  -Creates a new book
PUT /books/{id}  -Updates a specific book
PATCH /books/{id}  -Partial updates a specific book
DELETE /books/{id}  -Deletes a specific book
```

# Rule 3: Name the collections using Plural Nouns
For the collections in REST API development use plural nouns.

**Do's**

```markdown
GET /books
GET /books/{id}
POST /books
```

**Don'ts**

```markdown
GET /book
GET /book/{id}
POST /book
```

# Rule 4: Use resource nesting to show hierarchy
Resources sometimes have some kind of functional hierarchy or are related to each other. Nesting to one level is one of the best practices to group resources that are logically coherent.

For example in the Employee Management System, we have ‘departments’ and ‘employees’. Employees always belong to some department, therefore we may have the following endpoints structure:


```markdown
GET /departments -department's list
GET /departments/{id} -specific department
GET /departments/{id}/employees -employees list that belongs to a specific department
GET /departments/{id}/employees/{id} -specific employee of a specific department
```

# Rule 5: Error Handling
To eliminate confusion for API users when an error occurs, the errors should be handled and returns HTTP codes that provide enough information to know what has happened and possibly why.

There are 71 distinct HTTP status codes that we can rely on, but sometimes it is better to provide a more detailed explanation using specific error messages and internal code references.

**The ideal error message would consist of:**
- HTTP Status Code
- Code ID, which is an internal reference
- Clear and short messages briefly describing the problem

**Example:**
```markdown
{
  "status": 400,
  "message": 'Employee already exists',
  "code" "10212"
}
```

# Rule 6: Filtering, sorting, paging, and field selection
The collections are often enormous and managing them is a great challenge. It is not efficient to get a full list when retrieving only the requested data. Therefore, we need ways to filter items. REST API provides 4 types of filtering options.

**The REST API filtering options include:**

### Filtering
Using filtering we can narrow down the received results that satisfy the required conditions by specific parameters.

```markdown
GET /employees?projects=value
```

##### One way to encode operators and do range-based filtering is the use of square brackets `[]` on the key name. We can have as many operators as needed such as `lte`, `gte`, `before`, and `after`.

```markdown
GET /employees?salary[gte]=value&salary[lte]=value
GET /employees?start_date[before]=value&start_date[after]=value
```

### Sorting
The received results can be sorted ascending or descending by a chosen parameter.

```markdown
GET /employees?sort=start_date:asc
```

### Paging
The received results can be limited by a required number using `limit` query parameter.

```markdown
GET /employees?limit=10
```

### Field selection
Using field selection you can request only specific parts (fields) of the received objects by the `field` query parameter.

```markdown
GET /employees?fields=email,phone_num (for a full list of employees)
```

# Rule 7: Versioning
Making any changes to the APIs maybe cause breaking the clients and this is the main reason for the need to have different APIs versions. The more often used route to implement the versioning is in the endpoint URI.  

```markdown
https://raseel-public.github.io/apis/v1/
```

# Rule 8: API Documentation
The API documentation needs to be readable enough for both technical and non-technical people to understand it. Where these documents provide information about the used endpoints and methods, examples of request and response, authorization details, and so on.

# Rule 9: Using SSL/TLS
Using SSL/TLS to encrypt the communication between client and server is a must. The APIs should be secured and the sending and receiving data should not be compromised.







### Contact us

We would like to hear from you! [contact](raseel.mda@gmail.com)
