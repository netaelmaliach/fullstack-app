## The task
The task is to add [pagination](https://www.w3schools.com/css/css3_pagination.asp) to the website:
1. Populate your database with 1 million fake examples.(See example in 'prisma/seed.ts')
2. Front end component: show 10 posts on each page.
3. Reduce number of posts sent from backend to 10. Read about api routes below
4. Add videos to our posts website
5. The video metadata will be saved in mongoDB. Required metadata: user, date uploaded, id of post (sqlite), link to video (cloudinary)
6. Automatic focus on the title text box in the create post page, instead of the current html tag, implement it yourself using an effect.
7. If a video exists, it should appear, in every page where the post content is shown.
8. Implement light/dark theme button for all frontent components
9. support user management with authentication using cookies
10. Add profiles to our posts website
    
## Intro
This example shows how to implement a **fullstack app in TypeScript with [Next.js](https://nextjs.org/)** using [React](https://reactjs.org/) (frontend), [Next.js API routes](https://nextjs.org/docs/api-routes/introduction) and [Prisma Client](https://www.prisma.io/docs/reference/tools-and-interfaces/prisma-client) (backend). It also demonstrates how to implement authentication using [NextAuth.js](https://next-auth.js.org/). The example uses an SQLite database file with some initial dummy data which you can find at [`./prisma/dev.database`](./prisma/dev.database).

This example demonstrates a website, which shows posts for many users. Some examples of what a user can do:
1. Authenticate with [OAuth](https://www.youtube.com/watch?v=KT8ybowdyr0) in front of Github.
2. Get a list of posts from an external database (Called Prisma).
3. Some posts are private drafts, and can only be seen by the author.
4. Some posts are public and can be seen by all users.

## Getting started

### 1. Download the example and install dependencies


```bash
git clone git@github.com:bgu-frontend/hw1-blog.git
```

Install npm dependencies:

```bash
cd hw1-blog
npm install
```

### 2. Create and seed the database

Run the following command to create your SQLite database file. This also creates the `User` and `Post` tables that are defined in [`prisma/schema.prisma`](./prisma/schema.prisma):

```bash
npx prisma migrate dev --name init
```

When `npx prisma migrate dev` is executed against a newly created database, seeding is also triggered. The seed file in [`prisma/seed.ts`](./prisma/seed.ts) will be executed and your database will be populated with the sample data.

### 3. Start the app

```bash
npm run dev
```

The app is now running, navigate to [`http://localhost:3000/`](http://localhost:3000/) in your browser to explore its UI.

- Create issues and ask questions on [GitHub](https://github.com/bgu-frontend/hw1-blog/issues) or in [Moodle](https://moodle.bgu.ac.il/moodle/mod/forum/view.php?id=2453924).


## Good luck!



