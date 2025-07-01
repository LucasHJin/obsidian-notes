2025-06-29 13:43

Status:


Tags:
[[cs]] 
[[webdev]] 


___________________________________________________________________________
# Prisma ORM explained

**Prisma ORM:** modern TypeScript ORM (generates Typescript types from DB schema)
- Has several libraries → install the ones you need
- Lets you query and manipulate data using a fluent API

**How it works:** 
- Prisma generates and runs SQL under the hood (but can still use SQL if needed)
	- `$queryRaw` 
- Instead → type safe + auto completable methods
	- I.e. `const users = await prisma.user.findMany();` instead of `SELECT * FROM "User"` 

**Prisma schema:** file where you will define your models
- *Example: message in chat app*
```
model Message {
   id        Int      @id @default(autoincrement())
   content   String   @db.VarChar(255) 
   createdAt DateTime @default(now())
   author    User     @relation(fields: [authorId], references: [id])
   authorId  Int     
}

model User {
   // user's fields
}
```
- Lives in code base + tracked by version control
	 - Can define types + relations to other models (tables
- *Note*:
	- Uses `SERIAL` instead of `IDENTITY` for PostgresSQL ([link](https://stackoverflow.com/questions/55300370/postgresql-serial-vs-identity/55300741#55300741))

**Prisma client:** a separate library that you will use to interact with your database
- *Special feature* → customized to your schema
	- Just run `npx prisma generate` → and client is generated
- Features:
	- joins, filters, sorting, pagination, and more
- Also supports raw queries if necessary

**Prisma migrate:** tool to help with database migrations
- If schema is changed → run a Prisma migration to apply the schema changes to the database
	- ==All changes are tracked (`migrations` folder)== 

**Prisma.js vs lib/Prisma.js** 
- Use `lib/Prisma.js` for Next.js only or Next.js + Express
- *Both* → export a configured `PrismaClient` 
I.e.
```js
// Import the PrismaClient constructor from the @prisma/client package
import { PrismaClient } from '@prisma/client';

// Declare a variable to hold the Prisma client instance
let prisma;

// Check if the environment is production
if (process.env.NODE_ENV === 'production') {
  // In production, create a new PrismaClient instance directly
  prisma = new PrismaClient();
} else {
  // In development, use a global variable to persist the PrismaClient instance
  // across hot reloads (which can cause multiple instances to be created)
  if (!global.prisma) {
    // If there isn't already a global Prisma client, create one
    global.prisma = new PrismaClient();
  }
  // Use the existing global Prisma client
  prisma = global.prisma;
}

// Export the Prisma client instance for use throughout the app
export default pr
```
- Prevents multiple DB connections in development + only one PrismaClient at a time

*Note:* Whenever you change Prisma schema → need to update client with `prisma generate` 
![[Screenshot 2025-06-29 at 6.44.17 PM.png]]

# References
- https://www.prisma.io/orm
- [Getting started](https://www.prisma.io/docs/getting-started/setup-prisma/start-from-scratch/relational-databases-node-postgresql)
