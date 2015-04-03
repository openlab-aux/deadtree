# deadtree
deadtree will be an API for managing the books in the [hacklib](https://www.librarything.com/catalog/hacklib) (eventually and hopefully).

## Draft of the API

### JSON Responses/Objects

#### Book

| Field   | type   | description |
|---------|--------|-------------|
| `title`       | string  | Title of the book |
| `author`      | string  | Author of the book |
| `owner`       | int     | id of the owning user |
| `releaseYear` | int     | year of release |
| `publisher`   | string  | Publisher of the book e. g. "O'Reilly media" |
| `identifier`  | identifier json object | Identifies the Object uniquely |

#### Identifier

| Field      | type   | description |
|------------|--------|-------------|
| `isbn`     | string or `null`[1] | ISBN of the book if available else `null` |
| `idString` | string or `null`[1] | if `isbn` is specified `null` otherwise a unique String |

#### User

| Field      | type   | description |
|------------|--------|-------------|
| `name`     | string | name of the user |
| `id`       | int    | unique userID |
| `contact`  | string | human readable contact info[2] |

[1]: There should be a better way to represent an ISBN but the type also needs to hold an alternative identifier in the Database.

[2]: Note: Database strings often have length limits

### Endpoints

| Endpoint  | Method | URL parameters | Body Parameter | Description | Responsetype | Note |
|-----------|--------|----------------|----------------|-------------|--------------|------|
| `/books/` | GET | none | none | Returns a list of all Books | Array of Book Objects | |
| todo | todo | todo | todo | Allows to get a specific book | todo | |
| `/books/add` | POST | none | book | Allows addtion of a book | todo | todo: Authentification |
| `/users/` | GET | none | none | Returns a list of all users | Array of User objects | |
| `/users/:id:` | GET | `id`: int | none | Returns the Object of an specific user | User object | |
| `/users/register` | POST | todo | todo | Allows registering of a new user | todo | |

### To do

* Authentification
* ISBN
* Getting of specific books and Identification of books
* Authors
* Publishers?
* Better Relations, RDF?
