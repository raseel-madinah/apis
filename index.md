## Welcome to Raseel API development guidelines

This document illustrates most of the rules to follow by backend developers and integrators to write the APIs.

### Terminologies
- **Resource** is an object with associated data, represents something, and the set of methods can operate on it.
- **Collections** are set of resources.

### The 9 main rules

Let's talk about the main 9 best practises about REST APIs developement.
# Rule 1: Using Json
JSON is used as the data format for both the payload and the response.
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
# Rule 2: Using Nouns
**Nouns** are used for naming the resources. The actions on the resources are defined by a few standard HTTP methods such as (GET, PUT, POST, PATCH, and DELETE).
Here are a few examples to show how the endpoints should look like:


```markdown
GET  /books    - Returns a list of books
GET  /books/{id}    - Returns a specific book
POST  /books    - Create a new book
PUT  /books/{id}    - Updates a specific book
PATCH  /books/{id}    - Partial update a specific book
DELETE  /books/{id}    - Deletes a specific book
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
