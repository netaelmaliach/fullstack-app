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

### 3. Configuring your authentication provider

To get this example to work, you need to configure the [GitHub](https://next-auth.js.org/providers/github) authentication providers from NextAuth.js.

#### Configuring the GitHub authentication provider

<details><summary>Expand to learn how you can configure the GitHub authentication provider</summary>

First, log into your [GitHub](https://github.com/) account.

Then, navigate to [**Settings**](https://github.com/settings/profile), then open to [**Developer Settings**](https://github.com/settings/apps), then switch to [**OAuth Apps**](https://github.com/settings/developers).

![Github Developer Settings: OAuth Apps](https://res.cloudinary.com/practicaldev/image/fetch/s--fBiGBXbE--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_880/https://i.imgur.com/4eQrMAs.png)

Clicking on the **Register a new application** button will redirect you to a registration form to fill out some information for your app. The **Authorization callback URL** should be the Next.js `/api/auth` route.

For **Homepage URL** use the localhost path on your machine.

An important thing to note here is that the **Authorization callback URL** field only supports a single URL, unlike e.g. Auth0, which allows you to add additional callback URLs separated with a comma. This means if you want to deploy your app later with a production URL, you will need to set up a new GitHub OAuth app.

![Github: Register a new OAuth application](https://res.cloudinary.com/practicaldev/image/fetch/s--v7s0OEs_--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_880/https://i.imgur.com/tYtq5fd.png)

Click on the **Register application** button, and then you will be able to find your newly generated **Client ID** and **Client Secret**. Copy and paste this info into the [`.env`](./env) file in the root directory.

The resulting section in the `.env` file might look like this:

```env
# GitHub OAuth
GITHUB_ID=6bafeb321963449bdf51
GITHUB_SECRET=509298c32faa283f28679ad6de6f86b2472e1bff
```

</details>

### 4. Start the app

```bash
npm run dev
```

The app is now running, navigate to [`http://localhost:3000/`](http://localhost:3000/) in your browser to explore its UI.

- Create issues and ask questions on [GitHub](https://github.com/bgu-frontend/hw1-blog/issues) or in [Moodle](https://moodle.bgu.ac.il/moodle/mod/forum/view.php?id=2453924).

## Checking the coding task:

The tester will:
1. Clone your submitted repo.
2. Run the starter scripts.
3. The tester will fill the database with fake records: it could be empty, small, or large database. 
4. Manually test that the pages show correctly, by testing a few pages and see that they appear correctly.

There are going to be 5 pass/no pass tests for this part.



## Good luck!



