# Abraxas scala backend exercise

## Intro
Thank you for your interest and participation in our recruitment process for our scala backend developer position, 
to continue with the process we ask you to take the following technical test and share your result with us.

If you have any questions or comments during the test, do not hesitate to contact us by email at 
reclutamiento@grupoabraxas.com

## Get your environment ready
You'll need:
1. [Scala](https://scala-lang.org/)
2. [Sangria](https://sangria-graphql.org/learn/)
3. [AkkaHttp](https://doc.akka.io/docs/akka-http/current/index.html?language=scala)
4. The database of your choose*
5. Fork this repository

## Ready for action?
Great!! 

In order to complete this test you'll have to implement a GraphQL API given the following schema:

```graphql
type User {
    id: ID
    name: String
    email: String
    posts: [Post]
    comments: [Comment]
}

type Post {
    id: ID
    title: String
    body: String
    comments: [Comment]
    author: User
}

type Comment {
    id: ID
    comment: String
    post: Post
    user: User
}

type Query {
    posts: [Post]
    authors: [Author]
}

type Mutation {
    createUser(name: String, email: String): User
    post(title: String, body: String, author: ID): Post
    comment(post: ID, user: ID, comment: String): Comment
    updateUser(id: ID, name: String, email: String): User
    updatePost(id: ID, title: String, body: String): Post
    updateComment(id: ID, comment: String): Comment
    deleteUser(id: ID): ID
    deletePost(id: ID): ID
    deleteComment(id: ID): ID
}
```

The API should be served as a webservice using AkkaHttp.

### Extra points
- \* Use [neo4j](https://neo4j.com/) as the database of your webservice.
- Use [docker](https://www.docker.com/) to package your application.

## Deliverables
- The source code of your solution should be on your fork of this repository, let us the link when you are ready.
- Any other file that you consider relevant.

## General guidelines
Your code should be as simple as possible, yet well documented and robust. Spend some time on designing your solution.

Have fun!!