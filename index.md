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
 - [Node.js](https://nodejs.org/en/learn/getting-started/introduction-to-nodejs): The cornerstone of our backend applications
 - [NestJS](https://docs.nestjs.com/): A backend framework on top of Node.js with a lot of cats? 🐈‍⬛
 - [TablePlus](https://docs.tableplus.com/): The database management tool with the best mascot 🐘 (we like elephant themed software)
 - [Figma](https://www.figma.com/): The tool our designers at Wisemen use to take our breath away 🎨
 - [Github](https://github.com/): Where we store our precious code 🤩
 <!-- - [Linear](https://linear.app/wisemen): Did you get any tickets yet? 🤨 -->
 - And much more...


#### This onboarding is designed to be completed in roughly 2 to 3 days
This does not mean you have to complete it in 3-4 days.
People with more experience will be able to complete it faster than people with less experience.
Go at your own pace and be sure to ask for help when needed from your buddy or a member of our circle 🤝.

#### You will be working on a small to-do app 📋
This app wil teach you our core conventions and ways of working in Node.js backends.
We expect you to make **pull request** of your work so your buddy can review your code and keep track of your progress 🫣.
Don't know how to make pull requests yet? No worries more wil be explained in the next step.

Good luck!!!


## What you'll need ️🛠️

Being a part of our Node team requires you to have ... well, Node.js 😅.
But to get Node.js we'll start by setting up your terminal and installing Homebrew 🍺, a popular package manager for MacOS.

Check our [backend Guidelines](https://wisemen-digital.github.io/nestjs-bible/development-environment) for the tools you need to install before starting the onboarding.

- [Terminal Setup](https://wisemen-digital.github.io/nestjs-bible/development-environment/terminal)
- [Package Manager](https://wisemen-digital.github.io/nestjs-bible/development-environment/package-manager)
- [Node.js & TypeScript](https://wisemen-digital.github.io/nestjs-bible/development-environment/nodejs)
- [Docker](https://wisemen-digital.github.io/nestjs-bible/development-environment/docker)
- [Git](https://wisemen-digital.github.io/nestjs-bible/development-environment/git)
- [IDE](https://wisemen-digital.github.io/nestjs-bible/development-environment/ide)
- [Figma](https://wisemen-digital.github.io/nestjs-bible/development-environment/figma)

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

You can kickstart your new project without starting from square one by using the [Wisemen NestJS Template Project](https://github.com/wisemen-digital/nestjs-template). This repository already includes authentication, a user entity & much more, providing a solid foundation for your project. If at any point you are stuck, take a peek into the auth of user module, you might find great examples there!
[Fork](https://github.com/wisemen-digital/nestjs-onboarding-codelab/fork) this project into your own repository on Github.

<!-- ### 2. Package.json

The package.json file is used manage the project's dependencies and predefined run commands.

```json
{
  "packageManager": "pnpm@9.15.0",
  "name": "nestjs-example",
  "version": "0.1.0",
  "description": "",
  "author": "",
  "private": true,
  "license": "UNLICENSED",
  "type": "module",
  "scripts": {
    "clean": "rm -rf ./dist",
    "build": "nest build",
    "start": "node dist/src/entrypoints/api.js",
    "start:dev": "nest start --exec \"node --env-file=.env\" --watch",
    "lint": "eslint",
    ...
  },
  "dependencies": {
    "@aws-sdk/client-s3": "^3.712.0",
    "@aws-sdk/lib-storage": "^3.712.0",
    "@aws-sdk/s3-request-presigner": "^3.712.0",
    "@nestjs/common": "^10.4.15",
    ...
  },
  "devDependencies": {
    "@nestjs/cli": "^10.1.17",
    "@nestjs/schematics": "^10.0.2",
    "@nestjs/testing": "^10.2.4",
    "@sentry/types": "^7.37.1",
    ...
  }
}

```

#### 2.1 Scripts

The scripts property is used to specify a list of scripts that can be run using `pnpm script-name`.
It's written as a JSON object where each key is the name of a script and the value is the command to execute.
Most common scripts are `start` and `build`.

#### 2.2 Dependencies

Install the dependencies specified in package.json file by running:
```bash
pnpm install
```

**Dev dependencies** are dependencies that are only used during development and are not required for production.
**Dependencies** are required for production.
 -->

### 2. Environment Variables

Copy .env.test to .env:

```bash
cp .env.test .env
```

### 3. Run Services

To run the services required for the project, we will use Docker. Start the services by running the following command:

```bash
docker compose up
```

#### Services
- **PostgreSQL**: The database service for the project.
- **NATS**: The message broker service for the project.
- **Redis**: The caching service for the project. (Will soon be replaced by NATS KV)
- **TypeSense**: The search engine service for the project.

### 4. Running the project 🚀

Verify your setup by running the project. You can start the project in development mode by running the following command:

```bash
pnpm start:dev
```

```
if (errors.length() === 0) {
   proceedToNextChapter()
} else {
   askBuddyForHelp()
}
```

## Debug Setup
### Connecting with PostgreSQL

Open TablePlus, click on 'create new connection' and select PostgreSQL. <br />
Name: `any` <br />
Host/Socket : `localhost` <br />
Port: `5432` <br />
User: `postgres` <br />
Password: `password` <br />
Database: `test_db`<br />

### Debugging in VSCode

TODO: Add debugging setup

## Project Structure

### Folder structure

For this project we will be using a ‘vertical slices' folder structure.

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
Welcome to the Todo App Backend Codelab! In this codelab, you will be building a backend for a todo app. The goal is to create a robust backend system that allows users to perform CRUD operations on todo items. The development process is divided into several steps to guide you through building the essential components of the application.

### Project Description
The Todo App Backend is a simple backend system that provides a RESTful API for managing todo items. The backend includes the following features:

- **Create a Todo**: Users can create a new todo item with a title, description, and deadline.
- **Get All Todos**: Users can retrieve a list of all todo items of the authenticated user.
- **Get a Todo**: Users can retrieve a specific todo item by its unique identifier.
- **Update a Todo**: Users can update the title, description, and deadline of a todo item.
- **Delete a Todo**: Users can delete a todo item by its unique identifier.
- **Complete a Todo**: Users can mark a todo item as completed.
- **Uncomplete a Todo**: Users can mark a completed todo item as uncompleted.


### Project Structure

The project is organized into the following components:

1. **Entity**: Defines the database structure for a todo item.

2. **Command and response**: Commands are used to define the data structure of the input. Responses are used to define the data structure of the output. In case of a Rest API, the command is the body of the request and the response is the body of the response.

3. **Controller**: Implement the API controllers to handle incoming requests and interact with the service layer.

4. **Module**: Organize the components into a module to encapsulate the related functionality.

5. **Tests**: Write comprehensive tests to ensure the reliability and correctness of your code.

6. **Use case and Repository**: Develop the service layer to handle business logic and the repository layer to interact with the database.

7. **Documentation**: We generate API documentation using Swagger. This will help frontend developers to understand the API endpoints and their request/response schemas.

Before you begin, make sure you have the necessary tools and dependencies installed. check [PART 1](#part-1-getting-started) on setting up your development environment.

Now, let's dive into building the Todo App Backend!

Happy coding!

## PROJECT: Entity

Entities are used to define the data structure for a todo item. In this project, you will define a Todo entity that represents the structure of a todo item.

### Entity Definition
The Todo entity is a simple data structure that represents a todo item. It includes the following fields:

- **uuid**: A unique identifier for the todo item.
- **title**: The title of the todo item.
- **description**: A nullable description for the todo item.
- **deadline**: A nullable deadline for the todo item.
- **completed**: A boolean value indicating whether the todo item is completed (default: false).

To view all possible column types using Typeorm with Postgresql, see [docs](https://orkhan.gitbook.io/typeorm/docs/entities#column-types)

### Entity Setup
To define the Todo entity, you will create a new file called `todo.entity.ts` in the `src/modules/todo/entities` folder and define the Todo class with the specified fields.

```typescript
// src/modules/todo/entities/todo.entity.ts

import { Column, CreateDateColumn, DeleteDateColumn, Entity, Index, ManyToOne, PrimaryGeneratedColumn, UpdateDateColumn } from 'typeorm'

@Entity()
export class Todo {
  @PrimaryGeneratedColumn('uuid')
  uuid: string

  @CreateDateColumn({ precision: 3 })
  createdAt: Date

  @UpdateDateColumn({ precision: 3 })
  updatedAt: Date

  @DeleteDateColumn({ precision: 3 })
  deletedAt: Date

  @Column({ type: 'varchar' })
  title: string

  @Column({ type: 'varchar', nullable: true })
  description: string | null

  @Column({ type: 'timestamp', precision: 3, nullable: true })
  deadline: Date | null

  @Column({ type: 'boolean', default: false })
  completed: boolean
}
```

In the code above, you defined the Todo entity using the `@Entity` decorator from TypeORM. The Todo class includes the `uuid`, `createdAt`, `updatedAt`, `deletedAt`, `title`, `description`, `deadline` , and `completed` fields, which map to the corresponding columns in the database table.

### Entity Relations
The Todo entity has no relation with any other entities, but we want to create a relation between the todo's and a user.

To create a relation between the Todo and User entities, you can use the `@ManyToOne` decorator to define a many-to-one relationship between the two entities.

```typescript
// src/modules/todo/entities/todo.entity.ts

import { Column, CreateDateColumn, DeleteDateColumn, Entity, Index, ManyToOne, PrimaryGeneratedColumn, UpdateDateColumn } from 'typeorm'
import { User } from '../../user/entities/user.entity'

@Entity()
export class Todo {
  // ... other fields

  @Column({ type: 'uuid' })
  @Index()
  userUuid: string

  @ManyToOne(() => User, user => user.todos)
  @JoinColumn({ name: 'userUuid' })
  user?: Relation<User>
}
```

In the code above, you defined a many-to-one relationship between the Todo and User entities using the `@ManyToOne` decorator. The `@ManyToOne` decorator takes two arguments:

- The first argument is a function that returns the entity class of the related entity (User).
- The second argument (optional) is a function that returns the property of the related entity that represents the inverse side of the relationship (todos).

Now you need to add a one-to-many relationship on the User entity to complete the bidirectional relationship.

```typescript
// src/modules/user/entities/user.entity.ts

import { Column, CreateDateColumn, DeleteDateColumn, Entity, Index, OneToMany, PrimaryGeneratedColumn, UpdateDateColumn } from 'typeorm'
import { Todo } from '../../todo/entities/todo.entity'

@Entity()
export class User {
  // ... other fields

  @OneToMany(() => Todo, todo => todo.user)
  todos?: Array<Relation<Todo>>
}
```

In the code above, you defined a one-to-many relationship between the User and Todo entities using the `@OneToMany` decorator. The `@OneToMany` decorator takes two arguments:

- The first argument is a function that returns the entity class of the related entity (Todo).
- The second argument (optional) is a function that returns the property of the related entity that represents the inverse side of the relationship (user).

Now the Todo entity has a many-to-one relationship with the User entity, and the User entity has a one-to-many relationship with the Todo entity, completing the bidirectional relationship.

### Create migration

After defining the Todo entity and its relation with the User entity, you need to create a migration to apply the changes to the database schema.

Run the following command in your terminal:

```bash
pnpm typeorm migration:generate src/sql/migrations/CreateTodoEntity
```

This command creates a new migration file with the name `CreateTodoEntity.ts` in the migrations folder.

### Apply migration

After generating the migration file, you need to apply the migration to update the database schema.

```bash
pnpm typeorm migration:run
```

💡Don't forget to make a pull request of your work so your buddy can review your code and keep track of your progress. Keeping your PR's small and frequent is a good practice.

## USE CASE: Create Todo (Command & Response)
### Command
Commands are used to defines how the input of a use case is structured. In a Controller, NestJS will validate the data and transform it to the correct format.

First we will create a command for creating a todo item. Add the command in the `src/modules/todo/use-cases/create-todo` use-case folder.

```typescript
// create-todo.command.ts
import { IsDateString, IsNotEmpty, IsString } from 'class-validator'
import { IsNullable } from '../../../util/validators/is-nullable.validator.js'

export class CreateTodoCommand {
  @IsNotEmpty()
  title: string

  @IsString()
  @IsNullable()
  description: string | null

  @IsDateString({ strict: true })
  @IsNullable()
  deadline: Date | null
}
```

In the code above, you defined the CreateTodoCommand class with the `title`, `description`, and `deadline` fields. The `@IsNotEmpty` decorator is used to validate that the `title` field is not empty, and the `@IsString` decorator is used to validate that the `description` field is a string. The `@IsDateString` decorator is used to validate that the `deadline` field is a valid date string. The `@IsNullable` decorator is used to allow the `description` and `deadline` fields to be nullable.

To view all possible decorators using class-validator, see [docs](https://github.com/typestack/class-validator)

### Response
Responses are used to define the data structure for the response of the use cases. The responses will transform the data to the correct format before sending it to the frontend.

Add the response in the `create-todo` use-case folder.

Create a new file called `create-todo.response.ts` in the `create-todo` use case folder and define the CreateTodoResponse class with the specified fields.

```typescript
// create-todo.response.ts
export class CreateTodoResponse {
  uuid: string
  createdAt: string,
  updatedAt: string,
  title: string,
  description: string,
  deadline: string | null,
  completed: boolean

  constructor (todo: Todo) {
    this.uuid = todo.uuid
    this.createdAt = todo.createdAt
    this.updatedAt = todo.updatedAt
    this.title = todo.title
    this.description = todo.description
    this.deadline = todo.deadline?.toISOString() ?? null
    this.completed = todo.completed
  }
}
```

We only return the necessary data in the response. In this case, we need all fields and explicitly return them.

On updates and deletes, we will return no data, only a status code.

### Documentation
To document the API endpoints, you will use the `@ApiProperty` decorator from the `@nestjs/swagger` package to define the request and response schemas for the API endpoints.

We will edit the `create-todo.command.ts` file and add the `@ApiProperty` decorator to all the properties to define the request schema for the create todo endpoint.

```typescript
// create-todo.command.ts
import { ApiProperty } from '@nestjs/swagger'
import { IsDateString, IsNotEmpty, IsString } from 'class-validator'
import { IsNullable } from '../../../util/validators/is-nullable.validator'

export class CreateTodoCommand {
  @ApiProperty()
  @IsNotEmpty()
  title: string

  @ApiProperty({ type: String, nullable: true })
  @IsString()
  @IsNullable()
  description: string | null

  @ApiProperty({ type: String, format: 'date-time', nullable: true })
  @IsDateString({ strict: true })
  @IsNullable()
  deadline: string | null
}
```

Don't forget to add the `@ApiProperty` decorators to the `CreateTodoResponse` class in the `create-todo.response.ts` file to define the response schema for the create todo endpoint.

💡Don't forget to make a pull request of your work so your buddy can review your code and keep track of your progress. Keeping your PR's small and frequent is a good practice.

## USE CASE: Create Todo (Test)
### Testing

At Wisemen we do [test driven development](https://martinfowler.com/bliki/TestDrivenDevelopment.html). This means that we write tests before we write the actual code. This way we can make sure that the code we write is working as expected.

### E2E Testing
End-to-end (E2E) testing is a software testing method that tests the entire software application from start to finish. The purpose of E2E testing is to simulate real user scenarios and validate the system's integration with external interfaces.

First we will create a new file called `create-todo.e2e.test.ts` in the `tests` folder of the use case.

```typescript
// create-todo.e2e.test.ts
import { before, describe, after, it} from 'node:test'
import request from 'supertest'
import { expect } from 'expect'
import type { DataSource } from 'typeorm'
import { NestExpressApplication } from '@nestjs/platform-express'
import { setupTest } from '../../../../../test/setup/test-setup.js'
import { TestContext } from '../../../../../test/utils/test-context.js'
import type { TestUser } from '../../tests/setup-user.type.js'
import { RoleSeeder } from '../../tests/seeders/role.seeder.js'
import { Role } from '../../entities/role.entity.js'
import { CreateTodoModule } from '../create-todo.module.js'

describe('Create todo', () => {
  let app: NestExpressApplication
  let dataSource: DataSource

  let context: TestContext

  let adminUser: TestUser
  let readonlyUser: TestUser

  before(async () => {
    ({ app, dataSource, context } = await setupTest([CreateTodoModule]))

    adminUser = await context.getAdminUser()
    readonlyUser = await context.getReadonlyUser()
  })

  after(async () => {
    await app.close()
  })
})
```

In the above code, you defined the create todo test with the `before` and `after` hooks to set up and tear down the application for the tests. The `before` hook is used to create the application instance and set up the global pipes and filters, and the `after` hook is used to close the application instance after the tests are completed.

Now you need to add the tests for the create operations for the todo items. In our tests we will check the following cases:

- **Unauthenticated**: Test the API endpoints without authentication.
- **Unauthorized**: Test the API endpoints with an unauthorized user.
- **Invalid Input**: Test the API endpoints with invalid input data.
- **Valid Input**: Test the API endpoints with valid input data.

```typescript
// create-todo.e2e.test.ts
describe('Create todo', () => {
  // ... setup

  it('should return 401 when not authenticated', async () => {
    const response = await request(app.getHttpServer())
      .post('/todos')

    expect(response.status).toBe(401)
  })

  it('should return 401 when not authorized', async () => {
    const response = await request(app.getHttpServer())
      .post('/todos')
      .set('Authorization', `Bearer ${readonlyUser.token}`)
      .send({})

    expect(response.status).toBe(400)
  })

  it('should return 400 when the body is invalid', async () => {
    const { token } = await userSeeder.setupUser()

    const response = await request(app.getHttpServer())
      .post('/todos')
      .set('Authorization', `Bearer ${adminUser.token}`)
      .send({})

    expect(response.status).toBe(400)
  })

  it('should return 201', async () => {
    const dto = new CreateTodoCommandBuilder()
      .withTitle('Test Todo')
      .withDescription('Test Description')
      .withDeadline(new Date())
      .build()

    const response = await request(app.getHttpServer())
      .post('/todos')
      .set('Authorization', `Bearer ${adminUser.token}`)
      .send(dto)

    expect(response.status).toBe(201)
  })

  // ... other tests
})
```

In the above code, you can see we use a builder to create the createTodoCommand. The `CreateTodoCommandBuilder` is used to create command with specified data for the tests.

### Builders
Builders are used to create the data objects for the tests. In this project, you will define a CreateTodoCommandBuilder to create the command for the tests.

First we will create a new file called `create-todo-command.builder.ts` in the tests folder of the use case and define the CreateTodoCommandBuilder class with the specified methods.

```typescript
// create-todo-command.builder.ts
export class CreateTodoCommandBuilder {
  private command: CreateTodoCommand

  constructor () {
    this.reset()
  }

  reset () {
    this.command = new CreateTodoCommand()
    this.command.title = 'Test Todo'

    return this
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
    const result = command.user

    this.reset()

    return result
  }
}
```

In the code above, you defined the CreateTodoCommand class. Here you can see that all the necessary fields are set to a default value in the constructor. You can use the `withTitle`, `withDescription`, and `withDeadline` methods to set the specified data for the tests. The `build` method is used to return the created command with the specified data.

Builders are used to create entities for the tests. For the update and delete tests you will need to create a Todo entity builder to insert the data into the database. So we can perform the update and delete operations on existing data.

### Running tests

Have a look into the `.env.test` file, this environment file is used when running the tests. Make sure you docker containers are running.

Now run the tests with `pnpm test`, normally you will see the tests fail because we haven't implemented the methods yet. Now we can start implementing the use case and see the tests pass!

💡Don't forget to make a pull request of your work so your buddy can review your code and keep track of your progress. Keeping your PR's small and frequent is a good practice.

## USE CASE: Create Todo (Use Case & Repository)
### Use Case

Use case are used to handle the business logic for the application. In this example we will create a use case for the creation of a todo item. The use case will use a repository to interact with the database for the todo items.

### Use Case Definition

The CreateTodoUseCase is a class that defines the methods to handle the business logic for the todo items.

First we will create a new file called `create-todo.use-case.ts` in the use case folder and define the CreateTodoUseCase class.

```typescript
// create-todo.use-case.ts
@Injectable()
export class CreateTodoUseCase {
  constructor (
    @InjectRepository(Todo)
    private todoRepository: Repository<Todo>,
  ) {}

  async execute (
    command: CreateTodoCommand
  ): Promise<CreateTodoResponse> {
    const todo = this.todoRepository.create(command)

    await this.todoRepository.insert(todo)

    return new CreateTodoResponse(todo)
  }
}
```

In the use case, we defined the CreateTodoUseCase class with the `execute` method to handle the create operation for the todo items. The `execute` method is used to create a new todo item with the specified data. We used a command for the input and a response for the output.


## USE CASE: Create Todo (Controller & Auth)
### Controller

Controllers are used to handle incoming API calls and interact with the service layer to process the data. We create a seperate controller for every use case.

### Controller Definition
The CreateTodoController is a class that defines the API endpoints for the creation of todo items.

Create a new file called `create-todo.controller.ts` in the `create-todo` use case folder and define the `CreateTodoController` class with the specified methods.

```typescript
// create-todo.controller.ts
@ApiTags('Todo')
@Controller('todos')
export class CreateTodoController {
  constructor (
    private createTodoUseCase: CreateTodoUseCase
  ) {}

  @Post()
  @ApiCreatedResponse({ type: CreateTodoResponse })
  @Permission([Permissions.TODO_CREATE])
  async createTodo (
    @Body() createTodoCommand: CreateTodoCommand,
  ): Promise<CreateTodoResponse> {
    return this.createTodoUseCase.execute(createTodoCommand)
  }
}
```

In the code above, you implement the controller class with the `createTodo` method to handle the create operation for the todo items. We injected our use case into the controller and used the `execute` method to create a new todo item with the specified data.

- The `@Controller` decorator is used to define the base path for the API endpoints,
- The `@Post` decorator is used to define it's a post endpoint for the create operation,
- The `@ApiCreatedResponse` decorator is used to define the response schema for the API endpoints,
- The `@Body` decorator is used to validate the request body for the incoming request. It will validate it against the `CreateTodoCommand` class.

Also see the [NestJs documentation](https://docs.nestjs.com/controllers) for more information about controllers.

### Authentication & IDP

We should prevent unauthenticated users from accessing certain endpoints of our API. In our project template, we already implemented the middleware that will help guard us our endpoints. Have a look into `api.ts` & `auth.module.ts`, you'll see that we defined a middleware and some guards that will protect all our endpoints by default in our application.

Furthermore, have a look into the auth and user module, where all the authentication and user management logic is implemented.

We use Zitadel as our default identity provider. Our middleware only checks if the user has a valid token and if the user is allowed to access the endpoint.

💡Don't forget to make a pull request of your work so your buddy can review your code and keep track of your progress. Keeping your PR's small and frequent is a good practice.

## USE CASE: Create Todo (Module)
### Module

Modules are used to organize the components of the application into cohesive units. We will create a module for every use case. We will create also a module that encapsulates all modules related to the todo items called `TodoModule`. This module will be imported into the api module to make it available for our frontend.

### Module Definition

The CreateTodoModule is a class that defines the components of the application related to the creation of todo items. It includes the following components:

- **Entity**: Define the data structure for a todo item.
- **Controller**: Define the controller for handling the operations for the todo items.
- **Use case**: Define the service for handling the business logic for the todo items.

First we will create a new file called `create-todo.module.ts` in the `create-todo` use case folder and define the CreateTodoModule class.

```typescript
// create-todo.module.ts
@Module({
  imports: [TypeOrmModule.forFeature([Todo])],
  controllers: [CreateTodoController],
  providers: [CreateTodoUseCase],
  exports: []
})
export class CreateTodoModule {}
```

In the code above, you defined the TodoModule class with the `imports`, `controllers`, `providers`, and `exports` properties. The `imports` property is used to import the TypeOrmModule to provide the Todo entity to the application. The `controllers` property is used to define the CreateTodoController as a controller for the CreateTodoModule. The `providers` and `exports` properties are used to define the service and repository components for the CreateTodoModule.

Also see the [NestJs documentation](https://docs.nestjs.com/modules) for more information about modules.

After defining the CreateTodoModule, you need to created a `todo.module.ts` file in the todo folder that imports the CreateTodoModule. This TodoModule needs to be imported into the root application module (`src/entrypoints/api.ts`) to make it available in the application. When you run the application (`pnpm start:dev`), the TodoModule will be loaded and the CreateTodoController will be available to handle the API requests for the todo items. We can find the generated documentation in the [Swagger UI](http://localhost:3000/api/docs).

### Testing
On this point you can run the tests again with `pnpm test` to see if everything is working as expected. If the tests are passing, you can continue to the next step.

💡Don't forget to make a pull request of your work so your buddy can review your code and keep track of your progress. Keeping your PR's small and frequent is a good practice.

## Other Use Cases
Now that you have completed the Create Todo use case, you can move on to the next use cases:

- **Get All Todos**: Users can retrieve a list of all todo items of the authenticated user.
- **Get a Todo**: Users can retrieve a specific todo item by its unique identifier.
- **Update a Todo**: Users can update the title, description, and deadline of a todo item.
- **Delete a Todo**: Users can delete a todo item by its unique identifier.
- **Complete a Todo**: Users can mark a todo item as completed.
- **Uncomplete a Todo**: Users can mark a completed todo item as uncompleted.


If you are getting stuck, have a look at the other modules in the project template. You can find examples in the user, role, contact... modules. And don't hesitate to ask your buddy for help. They are there to help you and guide you through the process.

Once you have implemented all the use cases, and every test is passing, you can move on to the next step.

## Finishing up
Congratulations! You have successfully completed our Wisemen NestJS workshop. Make sure that your project has been pushed to your repository and that you have created a pull request. Fix any remarks that you have received from your buddy and wait for the final feedback.
