author: Jonas Vannieuwenhuijsen
summary: Onboarding Code Lab
id: index
tags:
categories:
environments:
status: Draft

# Wisemen Backend (NestJS) Onboarding

## Welcome to the Backend team at **Wisemen!**

  <img width="200" src="img/projectSetup/Wisemen_Logo_Acid.png">

### Welcome to the NestJS onboarding 👋!
Strap in and get ready to learn how we build killer apps at wisemen 🔥.

## Getting Started

#### You will learn how to work with
 - [Typescript](https://www.typescriptlang.org/docs/handbook/intro.html): Because a world without types is no world to live in
 - [Node.js](https://nodejs.org/en/learn/getting-started/introduction-to-nodejs): The engine of our backend applications
 - [NestJS](https://docs.nestjs.com/): A HTTP and dependency injection framework on top of Node.js with a lot of cats? 🐈‍⬛
 - [TablePlus](https://docs.tableplus.com/): The database management tool with the best mascot 🐘 (we like elephant themed software)
 - [Figma](https://www.figma.com/): The tool our designers at Wisemen use to take our breath away 🎨
 - [Github](https://github.com/): Where we store our precious code
 - [Linear](https://linear.app/wisemen): Did you get any tickets yet? 🤨
 - [Nats](https://nats.io/): Our event streaming backbone
 - And much more...


#### This onboarding is designed to be completed in roughly 2 to 3 days
People with more experience will be able to complete it faster than people with less experience.
Go at your own pace and be sure to ask for help when needed from your buddy or a member of our circle 🤝.

#### You will be working on a small to-do app 📋
This app wil teach you our core conventions and ways of working in Node.js backends.
We expect you to make **pull request** of your work so your buddy can review your code and keep track of your progress 🫣.
Don't know how to make pull requests yet? No worries more is explained [here](https://wisemen-digital.github.io/backend-playbook/development-environment/pull-requests).

Good luck!!!


## What you'll need ️🛠️

Being a part of our Node team requires you to have ... well, Node.js 😅.
But to get Node.js we'll start by setting up your terminal and installing Homebrew 🍺, a popular package manager for MacOS.

Check our [backend Guidelines](https://wisemen-digital.github.io/backend-playbook/development-environment) for the tools you need to install before starting the onboarding.

- [Terminal Setup](https://wisemen-digital.github.io/backend-playbook/development-environment/terminal)
- [Package Manager](https://wisemen-digital.github.io/backend-playbook/development-environment/package-manager)
- [Node.js & TypeScript](https://wisemen-digital.github.io/backend-playbook/development-environment/node)
- [Docker](https://wisemen-digital.github.io/backend-playbook/development-environment/docker)
- [Git](https://wisemen-digital.github.io/backend-playbook/development-environment/git)
- [IDE](https://wisemen-digital.github.io/backend-playbook/development-environment/ide)
- [Figma](https://wisemen-digital.github.io/backend-playbook/development-environment/figma)

If you have any questions or need help with the setup, don't hesitate to ask your buddy or a member of our circle 🤝.

## What you'll do 📋

### Project requirements

You will be creating the backend for a simple to-do app.
The app should allow the user to create, edit, delete, check and uncheck to-do's.

### Designs

[Todo-app designs](https://www.figma.com/file/hebgv4Qx8VanMAQkO1NFpa/Onboarding-to-do?node-id=407-4095&t=2qdyy89lKwN7dFw3-0)


 <img width="400" src="img/todo-app.png">


_If there's one thing the world needs, it's more todo apps!_ 👍


## Project setup

### 1. Fork the Wisemen NestJS Template from Github

You can kickstart your new project without starting from square one by using the [Wisemen NestJS Template Project](https://github.com/wisemen-digital/nestjs-template). This repository already includes authentication, a user entity & much more, providing a solid foundation for your project. If at any point you are stuck, take a peek into the contact module, you might find great examples there!
[Fork](https://github.com/wisemen-digital/nestjs-onboarding-codelab/fork) this project into your own repository on Github.

### 2. Environment Variables

Copy .env.test to .env:

```bash
cp .env.test .env
```

### 3. Start local development environment

To run the services required for the project, we will use Docker. Start the services by running the following command:

```bash
docker compose up
```

> You can also use our VSCode tasks that are part of our template project to improve your speed while developing. One good example is the `Stop all docker containers and start containers of current project` task.

#### Services
- **PostgreSQL**: The database for the project.
- **NATS**: The message broker for the project.
- **Redis**: The caching for the project.
- **TypeSense**: The search engine for the project.
- **typesense_dashboard**: Let's you debug typesense locally.
- **zitadel**: A OIDC authentication service.
- **s3service**: A S3 compatible local object store called minio
- **go-feature-flag**: A feature flag service.

> As a sidenote, you might want to disable zitadel and go-feature-flag locally unless you really want to test those services specifically.

### 4. Running the project 🚀

Verify your setup by running the project. You can start the project in development mode by running the following command:

```bash
cd apps/api && pnpm start:dev
```
> This command already gives it away slightly, but in Wisemen we are moving towards monorepo projects.


## Tableplus Setup
### Connecting with PostgreSQL

Open TablePlus, click on 'create new connection' and select PostgreSQL. <br />
Name: `Todo App` <br />
Host/Socket : `localhost` <br />
Port: `5432` <br />
User: `postgres` <br />
Password: `password` <br />
Database: `test_db`<br />

## Project Structure

Backend projects in Nest.js have come a long way in Wisemen and have had multiple architectural changes. If at any point you are interested in which architectural choices we made and why, be sure to ask your buddy. (This might be on the test later 🥸).

Briefly summarized, we apply a layered architecture which can be simplified to the following layers:
- **controller, job handler, event listener**: responsible for in and outgoing communication
- **application layer**: orchestrates the business logic, typically use cases
- **storage layer**: typically database interaction code

We apply a vertical slice architecture to split code into isolated business use cases. That's why you'll find that every use case has their own layered set of classes.


### Folder structure

```
- src
   |__ 📁 modules
       |__ 📁 ...
       |__ 📁 contact
       |   |__ 📁 entities
       |   |   |__ 📄 contact.entity.ts
       |   |
       |   |__ 📁 use-cases
       |   |   |__ 📁 ...
       |   |   |__ 📁 create-contact
                   |__ 📁 tests
       |   |   |   |__ 📄 create-contact.command.ts
       |   |   |   |__ 📄 create-contact.controller.ts
       |   |   |   |__ 📄 create-contact.module.ts
       |   |   |   |__ 📄 create-contact.response.ts
       |   |   |   |__ 📄 create-contact.use-case.ts
       |   |   |   |__ 📄 create-contact.repository.ts
       |   |   |
       |   |   |__ 📁 update-contact
       |   |   |__ 📁 ...
       |   |
       |   |__ 📄 contact.module.ts
       |
       |__ 📁 ...
```

### Project structure
<img width="600" src="img/projectStructure/project-structure.svg">

### File naming conventions
As a general rule, we use kebab-case for filenames and folders. We name files based on their purpose and type. For example, a command file for creating a contact would be named `create-contact.command.ts`.

## PART 2: Todo App Backend
The goal is to create a robust backend system that allows users to perform CRUD operations on todo items.

### Project Description
The app should support the following use cases:

- **Create a Todo**: Users can create a new todo item with a title, description, and deadline.
- **View all Todos**: Users can retrieve a list of all todo items of the authenticated user.
- **View the detail of a Todo**: Users can retrieve a specific todo item by its unique identifier.
- **Update a Todo**: Users can update the title, description, and deadline of a todo item.
- **Delete a Todo**: Users can delete a todo item by its unique identifier.
- **Complete a Todo**: Users can mark a todo item as completed.
- **Uncomplete a Todo**: Users can mark a completed todo item as uncompleted.
- **Search todos**: Users can search their todos on both title and description.
- **Update external systems**: Users can subscribe to events so they can attach their own systems.


### Project Structure

We use following naming conventions:

1. **Entity**: Defines the structure of a database table, like a Todo item.

2. **Command, Queries and Response**: Commands and Queries are used to define the data structure of the input. Responses are used to define the data structure of the output. In case of a HTTP API, a command is the body of the request. A query is query of the HTTP request and a response is the body of the response.

3. **Controller**: A controller to handles HTTP incoming requests.

4. **Module**: Organize the components into a module to encapsulate the related functionality. A module is a Dependency injection concept from Nest.js, it defines imports, providers and exports of the module.

5. **Use case**: Develop the application layer to orchestrate business logic. For simple use cases the business logic is entirely contained within the use case itself.

6. **Repository**: The repository abstracts database interactions.

7. **Domain Event**: An internal transaction scoped event that communicates changes between different modules that live inside the same application.

8. **Integration Event**: An event that is emitted externally to communicate with other systems.

Now, let's dive into building the Todo App Backend!

## Todo Entity

Entities are used to define the data structure for a todo item. In this project, you will define a Todo entity.

### Entity Definition

The Todo entity is a simple data structure that represents a todo item. It should include the following fields:

- **uuid**: A unique identifier for the todo item.
- **createdAt**: An auto generated timestamp used for debugging.
- **updatedAt**: An auto generated timestamp used for debugging.
- **title**: The title of the todo item.
- **description**: An optional description for the todo item.
- **deadline**: An optional deadline for the todo item.
- **completed**: A boolean value indicating whether the todo item is completed.

To view all possible column types using Typeorm with Postgresql, see [docs](https://orkhan.gitbook.io/typeorm/docs/entities#column-types)

### Entity Setup
To define the Todo entity, you will create a new file called `todo.entity.ts` in the `apps/api/src/app/todo/entities` folder and define the Todo class.

```typescript
@Entity()
export class Todo {
  @PrimaryGeneratedColumn('uuid')
  uuid: TodoUuid

  @CreateDateColumn({ precision: 3 })
  createdAt: Date

  ...
}
```

> 💡 For the sake of exercise, typing the code yourself throughout this onboarding will help with remembering it better than copying the code.

### Entity Relations
Until now the Todo entity had no relation with any other entities. We want to add a relation on todo to track the owner of the todo (a user).To create a relation between the Todo and User entities, you can use the `@ManyToOne` decorator to define a many-to-one relationship between the two entities.

Here the Todo is the owner of the relationship. There can be many Todo's per User but each Todo only has a single User.

```typescript
// src/modules/todo/entities/todo.entity.ts

import { Column, CreateDateColumn, DeleteDateColumn, Entity, Index, ManyToOne, PrimaryGeneratedColumn, UpdateDateColumn } from 'typeorm'
import { User } from '../../../app/users/entities/user.entity.js'

@Entity()
export class Todo {
  // ... other fields

  @Index()
  @Column({ type: 'uuid' })
  userUuid: UserUuid

  @ManyToOne(() => User)
  @JoinColumn({ name: 'user_uuid' })
  user?: Relation<User>
}
```

This code already contains some of our conventions that we choose to uphold but are not required by TypeORM itself. 
- We always brand uuids into a separate type like `UserUuid` so that you cannot accidentally pass the wrong type of uuid.
- `@JoinColumn({ name: 'user_uuid' })` contains the name of the column TypeORM will use for joins, we default to snake_case.
- `user?: Relation<User>` we define relations as optional (`?:`) because they have to be joined explicitly. Meaning that they will not allways be present on an object with the Todo type.
- `@Index()` we put an index on the `userUuid` column. It is generally good practice to index the foreign key column to improve lookups ans joins. If you want to learn more about indexes check out this awesome [site](https://use-the-index-luke.com/).


### Create migration

After defining the Todo entity, we need to create a migration to apply the changes to the database schema.
Run the following command in your terminal:

```bash
# in apps/api

pnpm typeorm migration:generate src/sql/migrations/create-todo-table
```

Alternatively you can use the task `API: Generate typeorm migration`.

**Be sure to always check the generated migration and see if there are no unexpected changes.**

### Apply migration

After generating the migration file, you need to apply the migration to update the database schema.

```bash
#in app/api

pnpm typeorm migration:run
```

> 💡 This a great point to create your first pull request so your buddy can review your code and keep track of your progress. Keeping your PR's small and frequent is a good practice.

## Create Todo Use Case: Command and Reponse

Now we'll start to create the first use case. Add a `use-cases/create-todo` next to the `entities` folder from earlier.

### Command
Commands are used to defines how the input of a use case is structured. We define which fields are required and basic input validation for each field. First we will create a command for creating a todo item. Add the command in the `create-todo` use-case folder.

```typescript
// create-todo.command.ts

import { IsDateString, IsNotEmpty, IsString } from 'class-validator'
import { IsNullable } from '@wisemen/validators'

export class CreateTodoCommand {
  @IsString()
  @IsNotEmpty()
  title: string

  ...
  description: string | null

  @IsDateString({ strict: true })
  @IsNullable()
  deadline: Date | null
}
```

To view all possible decorators using class-validator, see [docs](https://github.com/typestack/class-validator). Next to the validators from class-validator, we have also implemented custom validators like `@IsPlainTime()`. 

### Response
Responses are used to define the data structure for the response of the use cases. The responses will transform the data to the correct format before sending it to the frontend.

Add the response in the `create-todo` use-case folder.

Create a new file called `create-todo.response.ts` in the `create-todo` use case folder and define the CreateTodoResponse class with the specified fields.

```typescript
// create-todo.response.ts
export class CreateTodoResponse {
  uuid: TodoUuid

  constructor (todo: Todo) {
    this.uuid = todo.uuid
  }
}
```

We only return the necessary data in the response. In this case, we only need the uuid.

On updates and deletes, we generally return no data, only a status code 204.

### Documentation
We have created both the input and output of our use case and added validation on the input. In order to document the input and output for the frontend we need to generate some form of documentation. In Nest.js this can be achieved by using the `ApiProperty` decorator for fields. It will attach metadata to the command and response so we can generate an OpenApi spec later.

We will edit the `create-todo.command.ts` file and add the `@ApiProperty` decorator to all the properties to define the request schema for the create todo endpoint.

```typescript
// create-todo.command.ts

export class CreateTodoCommand {
  @ApiProperty({type: String})
  @IsNotEmpty()
  title: string

  ...
  description: string | null

  @ApiProperty({ type: String, format: 'date-time', nullable: true })
  @IsDateString({ strict: true })
  @IsNullable()
  deadline: string | null
}
```

Don't forget to add the `@ApiProperty` decorators to the response as well.

> 💡 If at any point you feel stuck or are unsure about how something works, be sure to ask your buddy.

## Create Todo Use Case: Testing
### Testing

At Wisemen we require automated tests for every feature and reusable component. For use cases we typically define end-to-end tests, integration tests and unit tests. We decide which types of tests we need based on the complexity of the feature and code. In general the following rules apply:

- We create and end-to-end test for every use case with a controller (i.e. it's a HTTP endpoint).
- We create a unit test for every use case that has some meaningful side effect (e.g. creating, updating an entity).
- We create integration tests for all generally more difficult behavior so we can isolate it. Some examples could be integration testing difficult queries in repositories or testing that an async job works as expected.

In general we have no hard requirements on whether you should write tests before or after you write your code. But for this onboarding we will define the tests first.

### E2E Testing
End-to-end (E2E) testing is a software testing method that tests the entire software application from start to finish. The purpose of E2E testing is to simulate real user scenarios and validate the system's integration with external interfaces.

First we will create a new file called `create-todo.e2e.test.ts` in the `tests` folder of the use case.

```typescript
// create-todo.e2e.test.ts

import { before, describe, after, it } from 'node:test'
import request from 'supertest'
import { expect } from 'expect'
import { NestExpressApplication } from '@nestjs/platform-express'
import { TestAuthContext } from '../../../../../../test/utils/test-auth-context.js'
import type { TestUser } from '../../../../../app/users/tests/setup-user.type.js'
import { TestBench } from '../../../../../../test/setup/test-bench.js'
import { EndToEndTestSetup } from '../../../../../../test/setup/end-to-end-test-setup.js'
import { CreateTodoCommandBuilder } from './create-todo-command.builder.js'

describe('Create todo', () => {
   let setup: TestSetup

  before(async () => {
    setup = await TestBench.setupEndToEndTest()
  })

  after(async () => {
    await setup.teardown()
  })
```

In the above code, you defined the create todo test with the `before` and `after` hooks to set up and tear down the application for the tests. 
Every end-to-end test file runs in it's own transaction in order to prevent other tests from influencing it's setup.

Because we will be creating a todo as a user let's add a test user:

```typescript
describe('Create todo', () => {
  let setup: TestSetup
  let user: TestUser
  let unauthorizedUser: TestUser

  before(async () => {
    setup = await TestBench.setupEndToEndTest()
    user = await setup.authContext.getUser([Permission.TODO_CREATE]) // You can add this permission to the Permission enum
    unauthorizedUser = await setup.authContext.getUser([]) // This user has no permissions
  })

  after(async () => {
    await setup.teardown()
  })
```

Now you need to add the tests for the create operations for the todo items. In our tests we will check the following cases:

- **Unauthenticated**: Test the API endpoints without authentication.
- **Unauthorized**: Test the API endpoints with an unauthorized user.
- **Invalid Input**: Test the API endpoints with invalid input data. 
- **Valid Input**: Test the API endpoints with valid input data.


```typescript
// create-todo.e2e.test.ts
describe('Create todo', () => {
  // ... setup

  it('blocks calls without authentication', async () => {
    const response = await request(app.getHttpServer())
      .post('/api/v1/todos')

    expect(response).toHaveStatus(401)
  })

  it('blocks unauthorized users', async () => {
    const response = await request(app.getHttpServer())
      .post('/api/v1/todos')
      .set('Authorization', `Bearer ${unauthorizedUser.token}`)
      .send({})

    expect(response).toHaveStatus(403)
  })

  it('validates the command', async () => {
    const response = await request(app.getHttpServer())
      .post('/api/v1/todos')
      .set('Authorization', `Bearer ${user.token}`)
      .send({})

    expect(response).toHaveStatus(400)
  })

  it('creates a todo', async () => {
    const command = new CreateTodoCommandBuilder()
      .withTitle('Test Todo')
      .withDescription('Test Description')
      .withDeadline(new Date())
      .build()

    const response = await request(app.getHttpServer())
      .post('/api/v1/todos')
      .set('Authorization', `Bearer ${user.token}`)
      .send(command)

    expect(response).toHaveStatus(201)
    expect(response.body).toStrictEqual(expect.objectContaining({
      uuid: expect.uuid()
    }))
  })
})
```

In the above code, you can see we use a builder to create the command. The `CreateTodoCommandBuilder` is used to create command with specified data for the tests.

### Builders
Builders are used to create the data objects for the tests. In this project, you will define a CreateTodoCommandBuilder to create the command for the tests.

First we will create a new file called `create-todo.command.builder.ts` in the tests folder of the use case and define the CreateTodoCommandBuilder class with the specified methods.

```typescript
// create-todo-command.builder.ts
export class CreateTodoCommandBuilder {
  private command: CreateTodoCommand

  constructor () {
    // We define "sane" defaults
    this.command = new CreateTodoCommand()
    this.command.title = generateUuid()
    this.description = null
    this.deadline = null
  }

  withTitle (title: string): this {
    this.command.title = title
    return this
  }

  withDescription (description: string | null): this {
    this.command.description = description
    return this
  }

  withDeadline (deadline: Date | null): this {
    this.command.deadline = deadline
    return this
  }

  build (): CreateTodoCommand {
    return this.command
  }
}
```

Builders are also used to create entities for the tests. For the update and delete tests you will need to create a Todo entity builder to insert the data into the database. So we can perform the update and delete operations on existing data.

### Running tests

Have a look into the `.env.test` file, this environment file is used when running the tests. Make sure you docker containers are running.

Now run the tests with `pnpm test:all`. You will see the tests fail because we haven't implemented anything yet.

> 💡 We will come back to unit testing later when we have implemented the use case.

## Create Todo Use Case: Use Case and Repository
### Use Case

Use case are used to orchestrate the business logic for the application. In this example we will create a use case for the creation of a todo item. The creation of a todo, admittedly, does not have a lot of business logic. 

First we will create a new file called `create-todo.use-case.ts` in the use case folder and define the CreateTodoUseCase class.

```typescript
import { Injectable } from '@nestjs/common'
import { InjectRepository } from '@wisemen/nestjs-typeorm'
import { Todo } from '../../entities/todo.entity.js'
import { AuthContext } from '../../../auth/auth.context.js'
import { CreateTodoResponse } from './create-todo.response.js'
import { CreateTodoCommand } from './create-todo.command.js'

@Injectable()
export class CreateTodoUseCase {
  constructor (
    private datasource: Datasource,
    private repository: CreateTodoRepository,
    private emitter: DomainEventEmitter
  ) {}

  async execute (command: CreateTodoCommand, userUuid: UserUuid): Promise<CreateTodoResponse> {

    // If you haven't created a TodoBuilder yet, now is a good time to do it
    const todo = new TodoBuilder()
      .withUserUuid(userUuid)
      .withTitle(command.title)
      .withDescription(command.description)
      .withDeadline(command.deadline)
      .build()

    const event = new TodoCreatedEvent(todo)

    await transaction(this.datasource, async () => {
      await this.repository.insert(todo)
      await this.emitter.emit([event]) 
    })

    return new CreateTodoResponse(todo)
  }
}
```

That's probably a lot to unpack in a small piece of code. We also need to define some other building blocks as well that the use case uses. These are left out intentionally, try to implement these building blocks by looking at the example `contact` module. You should add: 
- A repository `CreateTodoRepository`
- A DomainEvent base type: `TodoEvent`
- A Specific event: `TodoCreatedEvent`

Let's go through some of the code:
1. The use case is decorated with `@Injectable()`, this means that any constructor arguments will be injected by Nest.js during bootstrap.
2. The constructor defines 3 dependencies:
   * `datasource` represents the connection to the database and is used to start a transaction
   * `repository` abstracts the database code so we can simplify unit testing the use case
   * `emitter` emits events to interested listeners within the application
3. We insert the todo and emit the event in the same transaction. Listeners of the event could perform their own database operations and we want to make sure that we apply an all-or-nothing policy when creating a todo.

> 💡 Do you understand everything here? If not first try to find out by yourself what is going on. But don't be shy to ask your buddy if you feel like you're stuck.

## Create Todo Use Case: Controller
### Controller

Controllers are used to handle incoming HTTP calls. We create a separate controller for every use case.

### Controller Definition
The `CreateTodoController` is a class that defines the API endpoints for the creation of todo items.

Create a new file called `create-todo.controller.ts` in the `create-todo` use case folder and define the `CreateTodoController` class:

```typescript
// create-todo.controller.ts

import { ApiTags, ApiCreatedResponse } from '@nestjs/swagger'
import { Body, Controller, Post } from '@nestjs/common'
import { Permission } from '#src/modules/permission/permission.enum.js'
import { Permissions } from '#src/modules/permission/permission.decorator.js'
import { AuthContext } from '#src/modules/auth/auth.context.js'
import { CreateTodoUseCase } from './create-todo.use-case.js'
import { CreateTodoCommand } from './create-todo.command.js'
import { CreateTodoResponse } from './create-todo.response.js'

@ApiTags('Todo')
@ApiOAuth2([])
@Controller()
export class CreateTodoController {
  constructor (
    private useCase: CreateTodoUseCase
    private authContext: AuthContext
  ) {}

  @Post('/todos')
  @Version('1')
  @ApiCreatedResponse({ type: CreateTodoResponse })
  @Permissions([Permission.TODO_CREATE])
  async createTodo (
    @Body() createTodoCommand: CreateTodoCommand,
  ): Promise<CreateTodoResponse> {
    const userUuid = this.authContext.getUserUuidOrFail()
    return this.useCase.execute(createTodoCommand)
  }
}
```

In the code above, you implement the controller class with the `createTodo` method to handle the create operation for the todo items. We injected our use case into the controller and used the `execute` method to create a new todo item with the specified data.

- The `@Controller()` decorator tells Nest.js that this class contains a HTTP endpoint.
- The `@Post(...)` decorator is used to define a HTTP post endpoint for the create operation.
- The `@Version('1')` decorator defines this endpoint as `v1`.
- The `@ApiCreatedResponse(...)` decorator is used to define the response schema. This is used to generate documentation.
- The `@Body()` decorator is used to validate the request body for the incoming request. It will validate it against the `CreateTodoCommand` class.
- The `@Permissions(...)` decorator validates that only users with the specified permission can call this endpoint.
- The `AuthContext` is a class that's aware of the user who is performing the API call. We use this to get the `UserUuid`.

Also see the [NestJs documentation](https://docs.nestjs.com/controllers) for more information about controllers.

### Identity Access Management and Access Control

We prevents unauthenticated users from accessing certain endpoints of our API. In our project template, we already implemented the middleware that will help guard us our endpoints. Have a look into `api.ts` & `auth.module.ts`, you'll see that we defined a middleware and some guards that will protect all our endpoints by default in our application.

Furthermore, have a look into the auth and user module, where all the authentication and user management logic is implemented.

For most projects, we use Zitadel as our default identity provider (i.e. the issuer of access tokens). Our middleware only checks if the user has a valid token and if the user is allowed to access the endpoint.


## Create Todo Use Case: Tying it all together with Modules
### Module

Modules are used to organize the dependency injection and bootstrapping system of Nest.js. We create a module for every use case. We will create a module that encapsulates all HTTP modules related to the todo items called `TodoModule`. This module will be imported into the api module to make it available as HTTP endpoints.

### Module Definition

The `CreateTodoModule` is a class that defines the components of the application related to the creation of todo items. It includes the following components:

First we will create a new file called `create-todo.module.ts` in the `create-todo` use case folder and define the CreateTodoModule class.

```typescript
// create-todo.module.ts

@Module({
  imports: [TypeOrmModule.forFeature([Todo])],
  controllers: [CreateTodoController],
  providers: [
    CreateTodoUseCase,
    CreateTodoRepository
  ],
  exports: []
})
export class CreateTodoModule {}
```

In the code above, you defined the TodoModule class with the `imports`, `controllers`, `providers`, and `exports` properties. 
- The `imports` property is used to define the dependencies of this module. 
- The `controllers` property is used to define the `CreateTodoController` as a controller for the CreateTodoModule. 
- The `providers` define injectable components that are scoped to this module.
- The `exports` define injectable components that can be used by other modules.

Also see the [NestJs documentation](https://docs.nestjs.com/modules) for more information about modules.

After defining the `CreateTodoModule`, you need to created a `todo.module.ts` file in the todo folder that imports the CreateTodoModule. This TodoModule needs to be imported into the root application module (`src/entrypoints/api.ts`) to make it available in the application. You can reference the `ContactModule` and where it's used.

When you run the application (`pnpm start:dev`), the TodoModule will be loaded and the `CreateTodoController` will be available to handle the API requests for the todo items. We can find the generated documentation in the [Swagger UI](http://localhost:3000/api/docs).

### Testing
At this point you can run the tests again with `pnpm test:all` to see if everything is working as expected. If the tests are passing, you can continue to the next step.

💡Don't forget to make a pull request of your work so your buddy can review your code and keep track of your progress. Keeping your PR's small and frequent is a good practice.

## Create Todo Use Case: Unit Tests

Let's create some unit tests for the use case. Start by creating a new test file `create-todo.use-case.unit.test.ts`

```typescript
describe('CreateContactUseCase Unit test', () => {
  before(() => {
    TestBench.setupUnitTest()
  })
})
```

You should note that there is no `after` hook in this setup. That's because for unit tests we should not rely on any database or other systems so real teardown is needed. I invite you to look at what other setup is performed for unit tests.

In unit tests we typically test all expected behavior of a use case. The create Todo use case is limited but we can test that at the end of the use case, it should have inserted a todo and it should have emitted an event:

```typescript
 it('inserts the created todo', async () => {
    const eventEmitter = createStubInstance(DomainEventEmitter)
    const repository = createStubInstance(CreateTodoRepository)

    const useCase = new CreateContactUseCase(stubDataSource(), repository, eventEmitter,)

    const command = new CreateTodoCommandBuilder().build()
    const userUuid = generateUuid<UserUuid>()

    await useCase.execute(command)

    assert.calledOnce(repository.insert)

    // as an exercise you can check whether the argument of the insert call is what you expected
  })

  it('emit a todo created event', async () => {
    const eventEmitter = createStubInstance(DomainEventEmitter)
    const repository = createStubInstance(CreateTodoRepository)

    const useCase = new CreateContactUseCase(stubDataSource(), repository, eventEmitter,)

    const command = new CreateTodoCommandBuilder().build()
    const userUuid = generateUuid<UserUuid>()

    const { uuid } = await useCase.execute(command)

    const expectedTodo = new TodoBuilder()
      .withUuid(uuid)
      .withTitle(command.title)
      .withDescription(command.description)
      .withDeadline(command.deadline)
      .build()

    const expectedEvent = new TodoCreatedEvent(expectedContact)
    expect(eventEmitter).toHaveEmitted(expectedEvent)
  })
```

Be sure to check if your tests pass! 

> 💡 When creating the remaining use cases like update and delete Todo you can add unit tests that verify that the use case throws a specific error.

## Create Todo Use Case: IntegrationEvent

This part of the onboarding will focus on using domain events in order to trigger other actions in the application. As an exercise we will emit an integration event whenever a new Todo is created. 

Start by creating a new use case: `emit-todo-created`. This use case will not have a controller or use case file itself because it will be rather limited. Instead it will only have a subscriber:

```typescript
import { Injectable } from '@nestjs/common'
import { ConfigService } from '@nestjs/config'
import { ContactDeletedIntegrationEvent, ContactDeletedNatsSubject } from './contact-deleted.integration.event.js'
import { Subscribe } from '#src/modules/domain-events/subscribe.decorator.js'
import { natsSubject } from '#src/modules/nats/nats-application/nats-subject.js'
import { NatsPublisher, IntegrationEventWithSubject } from '#src/modules/nats/outbox/nats-publisher/nats-publisher.js'
import { ContactDeletedEvent } from '#src/app/contact/use-cases/delete-contact/contact-deleted.event.js'

@Injectable()
export class EmitTodoCreatedSubscriber {
  constructor (
    private publisher: NatsPublisher,
    private config: ConfigService
  ) {}

  @Subscribe(TodoCreated)
  async on (events: TodoCreated[]): Promise<void> { // You will always receive an array of events
    const integrationEvents: IntegrationEventWithSubject[] = []

    for (const event of events) {
      const todoUuid = event.content.uuid
      const integrationEvent = new TodoCreatedIntegrationEvent(todoUuid)
      const onSubject = natsSubject(TodoCreatedNatsSubject, {
        env: this.config.getOrThrow('NODE_ENV'),
        uuid: todoUuid
      })
      integrationEvents.push({ event: integrationEvent, onSubject })
    }

    await this.publisher.publish(integrationEvents)
  }
}
```
 
- The `@Subscribe(TodoCreated)` decorator makes sure that whenever a `TodoCreated` event gets emitted, this handler will be called.
- The `NatsPublisher` will insert outbox jobs as part of the same transaction when we created a todo in the use case. These jobs will publish the integration event to NATS in an async worker.

To create the `TodoCreatedIntegrationEvent`, I suggest you to take a look at other integration events in the contact module.

This subscriber needs to be registered to Nest.js we do this with the following module:

```typescript
// emit-todo-created.module.ts
@Module({
  imports: [NatsPublisherModule],
  providers: [EmitTodoCreatedSubscriber]
})
export class EmitTodoCreatedModule {}
```

This module needs to added to the imports of `domain-event-subscribers.module.ts`.

> 💡 If you want to learn more about how we work with jobs and NATS be sure to ask your buddy.

> 💡 We also use domain event subscribers to trigger other business logic. For example when a new user is created we assign a default role to that user. This cleanly separated both business cases which allows us to develop, modify and test them separately.

## Other Use Cases
Now that you have completed the Create Todo use case, you can move on to the next use cases:

- **View Todos**: Users can retrieve and search list of all todo items of the user. Try to implement this with Typesense, our search engine.
- **View Todo Detail**: Users can retrieve a specific todo item by its unique identifier.
- **Update Todo**: Users can update the title, description, and deadline of a todo item.
- **Delete Todo**: Users can delete a todo item by its unique identifier.
- **Complete Todo**: Users can mark a todo item as completed.
- **Uncomplete Todo**: Users can mark a completed todo item as uncompleted.


If you are getting stuck, have a look at the other modules in the project template. You can find examples in the user, role, contact... modules. And don't hesitate to ask your buddy for help. They are there to help you and guide you through the process.

Once you have implemented all the use cases, and every test is passing, you can move on to the next step.

## Finishing up
Congratulations! You have successfully completed our Wisemen Nest.js workshop. Make sure that your project has been pushed to your repository and that you have created a pull request. Fix any remarks that you have received from your buddy and wait for the final feedback.
