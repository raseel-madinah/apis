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



```markdown
Syntax highlighted code block

# Header 1
## Header 2
### Header 3

- Bulleted
- List

1. Numbered
2. List

**Bold** and _Italic_ and `Code` text

[Link](url) and ![Image](src)
```

For more details see [Basic writing and formatting syntax](https://docs.github.com/en/github/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax).

### Jekyll Themes

Your Pages site will use the layout and styles from the Jekyll theme you have selected in your [repository settings](https://github.com/raseel-public/apis/settings/pages). The name of this theme is saved in the Jekyll `_config.yml` configuration file.

### Support or Contact

Having trouble with Pages? Check out our [documentation](https://docs.github.com/categories/github-pages-basics/) or [contact support](https://support.github.com/contact) and we’ll help you sort it out.
