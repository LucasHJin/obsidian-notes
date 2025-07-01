2025-06-29 14:10

Status:


Tags:
[[cs]] 
[[webdev]]


___________________________________________________________________________
# Express - Repository Pattern

Pattern for writing SQL queries using utility functions
**Goal:** 
- 1 Database
- 1 connection pool
- Multiple “repositories” talking to that database
	- I.e. each repository, initialize the pool which is passed in as a parameter so you can make all the helper functions from that
- *Usually* → one repository per table

*Example:*
```js
// db.js
import { Pool } from 'pg';

export const pool = new Pool({
  connectionString: process.env.DATABASE_URL,
});
```

```js
// repositories/BookRepository.js
export default class BookRepository {
  constructor(pool) {
    this.pool = pool;
  }

  async getById(id) {
    const { rows } = await this.pool.query(
      'SELECT * FROM books WHERE id = $1',
      [id]
    );
    return rows[0];
  }
}
```

```js
// repositories/MovieRepository.js
export default class MovieRepository {
  constructor(pool) {
    this.pool = pool;
  }

  async getById(id) {
    const { rows } = await this.pool.query(
      'SELECT * FROM movies WHERE id = $1',
      [id]
    );
    return rows[0];
  }
}
```

```js
import express from 'express';
import { pool } from './db.js';
import BookRepository from './repositories/BookRepository.js';
import MovieRepository from './repositories/MovieRepository.js';

const app = express();
app.use(express.json());

const books = new BookRepository(pool);
const movies = new MovieRepository(pool);

app.get('/books/:id', async (req, res) => {
  const book = await books.getById(req.params.id);
  res.json(book);
});

app.get('/movies/:id', async (req, res) => {
  const movie = await movies.getById(req.params.id);
  res.json(movie);
});
```

# References

