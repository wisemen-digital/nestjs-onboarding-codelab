author: Jonas Vannieuwenhuijsen
summary: Onboarding Code Lab
id: index
tags:
categories:
environments:
status: Draft

# Wisemen Onboarding Backend

## What you'll learn: overview

#### First of all, welcome to **Wisemen!** We are happy to have you here and we hope you will have a great time working with us.


  <img width="200" src="img/projectSetup/Wisemen_Logo_Acid.png">

Welcome to the backend onboarding! In this onboarding you will learn how development happens at Wisemen.
You will learn how to work with NodeJs, TablePlus, Figma, Github and Jira.

This onboarding is designed to be completed in roughly 3-4 days. 
This does not mean you have to complete it in 3-4 days. People with more experience will be able to complete it faster than people with less experience.

You will be working on a small to-do app.
This app will be used to learn the same way we, as backend developers work at Wisemen. You will be working with the exact tools and workflow we use in our projects.

We also expect you to make pull request of your work so your buddy can review your code and keep track of your progress.
The way we do this will be explained in this onboarding.

Good luck!!!


## What you need: Prerequisites

### Development Environment

A well-configured development environment is crucial for efficient and productive backend development. We use the following tools and services for version control, code editing, and enhancing our coding experience.

#### Setup

Our backend stack is built using Node.js and TypeScript using the NestJs framework, which provide a powerful and flexible foundation for server-side development. In this section, we'll explain how to set up Node.js using Homebrew, a popular package manager for macOS.

#### Setting up Homebrew

1. **Install Homebrew** (if not already installed): Open Terminal and run the following command:

   ```bash
   /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
   ```

   This command will download and install Homebrew on your system.

2. **Update Homebrew**: Before installing any packages, it's a good idea to update Homebrew to the latest version. Run the following command to do so:

   ```bash
   brew update
   ```

#### Installing iTerm2 & Oh My Zsh & Powerlevel10k

1. **Install iTerm2**: Download the latest version of iTerm2 from [https://iterm2.com](https://iterm2.com).

2. **Installing Oh My Zsh**: Open Iterm2 and run the following command:

    ```bash
    sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
    ```

  This command will download and install Oh My Zsh and set Zsh as your default shell.

3. **Install the recommend fonts**:

   - [MesloLGS NF Regular.ttf](
       https://github.com/romkatv/powerlevel10k-media/raw/master/MesloLGS%20NF%20Regular.ttf)
   - [MesloLGS NF Bold.ttf](
       https://github.com/romkatv/powerlevel10k-media/raw/master/MesloLGS%20NF%20Bold.ttf)
   - [MesloLGS NF Italic.ttf](
       https://github.com/romkatv/powerlevel10k-media/raw/master/MesloLGS%20NF%20Italic.ttf)
   - [MesloLGS NF Bold Italic.ttf](
       https://github.com/romkatv/powerlevel10k-media/raw/master/MesloLGS%20NF%20Bold%20Italic.ttf)

    Download each file and double-click on each file and click "Install". This will make `MesloLGS NF` font available to all applications on your system.

4. **Install Powerlevel10k**: Run the following command:

    ```bash
    git clone --depth=1 https://github.com/romkatv/powerlevel10k.git ${ZSH_CUSTOM:-$HOME/.oh-my-zsh/custom}/themes/powerlevel10k
    ```

  Set `ZSH_THEME="powerlevel10k/powerlevel10k"` in `~/.zshrc`

  Restart Zsh with `exec zsh`.

5. **Configure Powerlevel10k**: Run the following command:

    ```bash
    p10k configure
    ```

  This command will start the configuration wizard. Follow the instructions to customize your prompt.


#### Installing Node.js with Homebrew

To install Node.js using Homebrew, follow these steps:

1. **Install Node.js**: Now that Homebrew is installed and updated, you can install Node.js by running the following command:

   ```bash
   brew install node
   ```

   This command will install the latest stable version of Node.js on your system.

2. **Verify Node.js installation**: To verify that Node.js is installed correctly, run the following commands to check the version numbers for Node.js and npm (the Node.js package manager):

   ```bash
   node --version
   npm --version
   ```

   If both commands return version numbers, Node.js and npm are installed correctly.

3. **Install pnpm**: We use pnpm as our package manager. To install pnpm, run the following command:

   ```bash
   npm install -g pnpm
   ```

   This command will install the latest version of pnpm and make it available system-wide.

4. **Install TypeScript**: We use TypeScript as our programming language. To install TypeScript, run the following command:

   ```bash
   npm install -g typescript
   ```

   This command will install the latest version of TypeScript and make it available system-wide.

5. **Verify TypeScript installation**: To verify that TypeScript is installed correctly, run the following command to check the TypeScript version:

   ```bash
   tsc --version
   ```

   If the command returns a version number, TypeScript is installed correctly.

#### Version Control

- **Git**: Our preferred version control system for tracking code changes and collaborating with the team.
- [**Bitbucket**](https://bitbucket.org/appwise/workspace/overview) / Github: We use Bitbucket and Github as our Git repository hosting service for managing our codebase and collaborating on projects.


### IDE

There are 2 different IDE's used in this company. You can use either **Visual Studio Code** or **WebStorm**.

#### WebStorm
WebStorm is a JavaScript IDE with complete set of tools for client-side and server-side development and testing.
It provides code completion, on-the-fly error detection, powerful navigation and refactoring for JavaScript, TypeScript, CSS, HTML and more.

Webstorm is a paid IDE. You can get a license from Wisemen. Ask your buddy!

[Download WebStorm](https://www.jetbrains.com/webstorm/download)


#### Visual Studio Code
Visual Studio Code is a source-code editor developed by Microsoft for Windows, Linux and macOS. 
It includes support for debugging, syntax highlighting, intelligent code completion, snippets, and code refactoring.

Visual Studio Code is a free IDE. You can download it from the website.

[Download vscode](https://code.visualstudio.com/download)

Choose the IDE you want to work with and download it.


### Figma
Our designers work with **Figma**.
Figma is a vector graphics editor and prototyping tool which is browser-based or can be installed on macOS or Windows.
We recommend you to install the desktop app.

[Download Figma](https://www.figma.com/downloads/)

Take a look around in Figma and try to get familiar with the tool. You will be using it a lot in the future.
You can view all of our designs here:

[Wisemen Figma](https://www.figma.com/files/team/1070403287155222588/Wisemen?fuid=1070747045190465434)

To access the designs you need, you need to log in with your Wisemen account.
the designs you need for this onboarding are: [Todo-app designs](https://www.figma.com/file/hebgv4Qx8VanMAQkO1NFpa/Onboarding-to-do?node-id=407-4095&t=2qdyy89lKwN7dFw3-0)

### Github repository
Github is a web-based version control repository hosting service, for source code and development projects that use the Git revision control system.

All your future projects will be hosted on Github.

[Wisemen Github](https://github.com/wisemen-digital)

If you are not yet familiar with Bitbucket and/or Git, Here is great article to get you started:
[Github Git tutorial](https://docs.github.com/en/get-started/quickstart/hello-world)

We also expect you to make pull request of your work so your buddy can review your code and keep track of your progress.
In the article above you can find a section about pull requests to get you started!

<!-- ### Jira access

For this onboarding you will be working with Jira to track your progress. You can find the Jira board here:
[Jira Todo]()

Jira is used to track the progress of your project and manage the tasks that need to be done.
All the requirements for the to-do app are in the Jira. You will be creating tasks in the Jira to keep track of your progress. (weet niet of ze zelf ticketjes hiervoor moeten maken of we ze dat geven?)

The Jira contains all the requirements for creating the to-do app.

*ToDo: Add link to Jira* -->

## What you'll do


### Project explanation

You will be creating the backend for a simple to-do app. In the app they can  create, edit, delete, check and uncheck to-do's.

### Designs

[Todo-app designs](https://www.figma.com/file/hebgv4Qx8VanMAQkO1NFpa/Onboarding-to-do?node-id=407-4095&t=2qdyy89lKwN7dFw3-0)

## Project setup

### 1. Clone the Wisemen-Nest-Core from Github

You can kickstart your new project without starting from square one by utilizing the [Wisemen-Nest-Core repository](https://github.com/wisemen-digital/nestjs-template). This repository already includes authentication and a user entity, providing a solid foundation for your project.

### 2. Package.json

> The package.json file is used to give information to npm that allows it to identify the project as well as handle the
> project's dependencies. npm can install the packages you specify in your package.json file.
> The main use of the package.json file is to list the packages that your project depends on and to ensure that your 
> colleagues get the same packages when they do `npm install`.

#### 2.1 Scripts

> The scripts property is used to specify a list of scripts that can be run using `npm run <script-name>`.
> It's written as a JSON object where each key is the name of a script and the value is the command to run for.
> Most common scripts are `start` and `build`.

#### 2.2 Dependencies vs Dev Dependencies

> Dev dependencies are dependencies that are only used during development and are not required for production.
> Dependencies are required for production.

### 3. Environment variables

Create the .env file and setup the following 5 variables:
- PostgreSQL link (example)<br />
   `TYPEORM_URI = postgresql://postgres:password@127.0.0.1:5432/todo`
- Refresh token lifetime (5 minute example)<br />
   `REFRESH_TOKEN_LIFETIME = 300`
- To generate the crypto keys, following commands are required (best to execute this in CLI at project folder)<br />

   'Note: during private generation a passphrase is required, this is RSA_PASSPHRASE'
   ```bash
   openssl genrsa -des3 -out private.pem 2048
   openssl rsa -in private.pem -outform PEM -pubout -out public.pem
   cat private.pem | base64 '<-- Your RSA_PRIVATE'
   cat public.pem | base64 '<-- Your RSA_PUBLIC'
   ```
   RSA private key<br />
   `RSA_PRIVATE = "your private key"`<br />

   RSA public key<br />
   `RSA_PUBLIC = "your public key"`<br />

   RSA passphrase<br />
   `RSA_PASSPHRASE = "your password"`<br />

### 4. PostGis Database Setup

#### Requirements
1. Docker Desktop
2. TablePlus

#### Docker setup

Download and install the requirements above. Once these are installed we can pull the `postgis/postgis` image from the docker website. Open a command tool and execute `docker pull postgis/postgis`. This will download the image which we will use later.

Open the Docker Desktop application and confirm the image has been installed. After the image is installed, we can create a docker container using following command: `docker run --name [NAME] -e POSTGRES_PASSWORD=[PASSWORD] -p 5432:5432 -d postgis/postgis`. Confirm that in the Containers / Apps the postgis/postgis container with the name `[NAME]` is running. We can now setup different databases using following command which will open the psql CLI: `docker exec -ti [NAME] psql -U postgres`. After we are in the CLI, we can configure the databases: `CREATE DATABASE [database_name];` (notice the ; at the end) To check if the database has been created, execute the `\l` command in the CLI, this will list all the databases available. To exit the CLI, type `quit`.

#### Connecting with TablePlus
(TablePlus can be downloaded though SetApp)

Open TablePlus, click on 'create new connection' and select PostgreSQL. <br />
Name: `any` <br />
Host/Socket : `localhost` <br />
Port: `5432` <br />
User: `postgres` <br />
Password: `[PASSWORD]` <br />
Database: `[database_name]`<br />

### 5. First Start 🚀

Now try to run your first project with `pnpm start:dev`

```
if (errors.length() === 0) {
   proceedToNextChapter()
} else {
   askBuddyForHelp()
}
```

## Project Structure

### Folder structure
For this project we will be using a ‘split-by-type' folder structure. This is recommended for small applications.

```
- src
   - modules
      - ...
      - users
         - controllers
            - user.controller.ts
         - dtos
            - create-user.dto.ts
            - update-user.dto.ts
         - entities
         - guards
         - modules
         - repositories
         - services
         - tests
         - transformers
```

### File naming conventions
As seen above the filename template is the following: <br />
`name-of-the-file.type-of-thing.ts` 

### Project structure
<img width="600" src="img/projectStructure/project-structure.svg">

## PROJECT: Overview
Welcome to the Todo App Backend Codelab! In this codelab, you will be building a backend for a todo app. The goal is to create a robust backend system that allows users to perform CRUD operations on todo items. The development process is divided into several steps to guide you through building the essential components of the application.

### Project Description
The Todo App Backend is a simple backend system that provides a RESTful API for managing todo items. The backend system includes the following features:

- **Create a Todo**: Users can create a new todo item with a title, description, and deadline.
- **Get All Todos**: Users can retrieve a list of all todo items of the authenticated user.
- **Get a Todo**: Users can retrieve a specific todo item by its unique identifier.
- **Update a Todo**: Users can update the title, description, and deadline of a todo item.
- **Delete a Todo**: Users can delete a todo item by its unique identifier.
- **Complete a Todo**: Users can mark a todo item as completed.
- **Uncomplete a Todo**: Users can mark a completed todo item as uncompleted.


### Project Structure

The project is organized into the following components:

1. **Entity**: Define the data structure for a todo item.

2. **DTO (Data Transfer Object) and Transformer**: Create DTOs to transfer data between layers and transformers to convert to the correct response

3. **Controller**: Implement the API controllers to handle incoming requests and interact with the service layer.

4. **Module**: Organize the components into a module to encapsulate the related functionality.

5. **Tests**: Write comprehensive tests to ensure the reliability and correctness of your code.

6. **Service and Repository**: Develop the service layer to handle business logic and the repository layer to interact with the database.

7. **Documentation**: Document your API endpoints to make it easy for others to use your backend.

Before you begin, make sure you have the necessary tools and dependencies installed. Refer to step 4 in the guide for instructions on setting up your development environment.

Now, let's dive into building the Todo App Backend!

Happy coding!

## PROJECT: Entity

Entities are used to define the data structure for a todo item. In this project, you will define a Todo entity that represents the structure of a todo item.

### Entity Definition
The Todo entity is a simple data structure that represents a todo item. It includes the following fields:

- **uuid**: A unique identifier for the todo item.
- **title**: The title of the todo item.
- **description**: An nullable description for the todo item.
- **deadline**: An nullable deadline for the todo item.
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

In the code above, you define the Todo entity using the `@Entity` decorator from TypeORM. The Todo class includes the `uuid`, `createdAt`, `updatedAt`, `deletedAt`, `title`, `description`, `deadline` , and `completed` fields, which map to the corresponding columns in the database table.

### Entity Relations
Now the Todo entity has no relation with any other entity, but we want to "attach" the todo's to an user. This we can do with entity relations.

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

In the code above, you define a many-to-one relationship between the Todo and User entities using the `@ManyToOne` decorator. The `@ManyToOne` decorator takes two arguments:

- The first argument is a function that returns the entity class of the related entity (User).
- The second argument is a function that returns the property of the related entity that represents the inverse side of the relationship (todos).

Now you need to add a one-to-many relationship to the User entity to complete the bidirectional relationship.

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

In the code above, you define a one-to-many relationship between the User and Todo entities using the `@OneToMany` decorator. The `@OneToMany` decorator takes two arguments:

- The first argument is a function that returns the entity class of the related entity (Todo).
- The second argument is a function that returns the property of the related entity that represents the inverse side of the relationship (user).

Now the Todo entity has a many-to-one relationship with the User entity, and the User entity has a one-to-many relationship with the Todo entity, completing the bidirectional relationship.

### Create migration

After defining the Todo entity and its relation with the User entity, you need to create a migration to apply the changes to the database schema.

First add your entity to the `models.ts` file in the `src/config/sql/models` folder.

Next, run the following command in your terminal:

```bash
pnpm typeorm migration:create CreateTodoEntity
```

This command creates a new migration file with the name `CreateTodoEntity`. Add this file to the `src/config/sql/migrations` folder and add the generated migration class to the `mainMigrations` in the `index.ts` file.

💡Don't forget to make a pull request of your work so your buddy can review your code and keep track of your progress. Keeping your PR's small and frequent is a good practice.

## PROJECT: DTO & Transformer (and documentation)
### Data Transfer Object (DTO)
Data Transfer Objects (DTOs) are used to defines how the data will be sent over the network. The DTOs will validate the data and transform it to the correct format before sending it to the controller.

First we will create a DTO for creating a todo item. Create a new file called `create-todo.dto.ts` in the `src/modules/todo/dtos` folder and define the CreateTodoDto class with the specified fields.

```typescript
// src/modules/todo/dtos/create-todo.dto.ts

import { IsDateString, IsNotEmpty, IsString } from 'class-validator'
import { IsNullable } from '../../../util/validators/is-nullable.validator'

export class CreateTodoDto {
  @IsNotEmpty()
  title: string

  @IsString()
  @IsNullable()
  description: string | null

  @IsDateString({ strict: true })
  @IsNullable()
  deadline: string | null
}
```

In the code above, you define the CreateTodoDto class with the `title`, `description`, and `deadline` fields. The `@IsNotEmpty` decorator is used to validate that the `title` field is not empty, and the `@IsString` decorator is used to validate that the `description` field is a string. The `@IsDateString` decorator is used to validate that the `deadline` field is a valid date string. The `@IsNullable` decorator is used to allow the `description` and `deadline` fields to be nullable. 

To view all possible decorators using class-validator, see [docs](https://github.com/typestack/class-validator)

For the update call we will use the same DTO, because we only want to update the title, description and deadline.


💡Don't forget to make a pull request of your work so your buddy can review your code and keep track of your progress. Keeping your PR's small and frequent is a good practice.

### Transformer
Transformers are used to convert the data to the correct format before sending the response to the client. In this project, you will define a TodoTransformer to transform the todo item to the correct format before sending it to the client.

First we will create a transformer and transformer type for the todo item. Create a new file called `todo.transformer.ts` in the `src/modules/todo/transformers` folder and define the TodoTransformer class with the specified fields.

```typescript
// src/modules/todo/transformers/todo.transformer.ts

import { Todo } from '../entities/todo.entity'
import { Transformer } from '@appwise/express-dto-router'

export class TodoTransformerType {
   uuid: string
   createdAt: Date
   updatedAt: Date
   title: string
   description: string | null
   deadline: Date | null
   completed: boolean
}

export class TodoTransformer extends Transformer<Todo, TodoTransformerType> {
  transform (todo: Todo): TodoTransformerType {
    return {
      uuid: todo.uuid,
      createdAt: todo.createdAt,
      updatedAt: todo.updatedAt,
      title: todo.title,
      description: todo.description,
      deadline: todo.deadline?.toISOString() ?? null,
      completed: todo.completed
    }
  }
}
```

In the code above, you define the TodoTransformer class with the `transform` method that takes a todo item as an argument and returns a transformed todo item in the correct format.

### Documentation
To document the API endpoints, you will use the `@ApiProperty` decorator from the `@nestjs/swagger` package to define the request and response schemas for the API endpoints.

First we will edit the `create-todo.dto.ts` file in the `src/modules/todo/dtos` folder and add the `@ApiProperty` decorator to the `CreateTodoDto` class to define the request schema for the create todo endpoint.

```typescript
// src/modules/todo/dtos/create-todo.dto.ts

import { ApiProperty } from '@nestjs/swagger'
import { IsDateString, IsNotEmpty, IsString } from 'class-validator'
import { IsNullable } from '../../../util/validators/is-nullable.validator'

export class CreateTodoDto {
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

Second we will edit the `todo.transformer.ts` file in the `src/modules/todo/transformers` folder and add the `@ApiProperty` decorator to the `TodoTransformerType` class to define the response schema for the todo item.

```typescript
// src/modules/todo/transformers/todo.transformer.ts

import { ApiProperty } from '@nestjs/swagger'
import { Todo } from '../entities/todo.entity'
import { Transformer } from '@appwise/express-dto-router'

export class TodoTransformerType {
  @ApiProperty()
  uuid: string

  @ApiProperty()
  createdAt: Date

  @ApiProperty()
  updatedAt: Date

  @ApiProperty()
  title: string

  @ApiProperty({ type: String, nullable: true })
  description: string | null

  @ApiProperty({ type: String, format: 'date-time', nullable: true })
  deadline: Date | null

  @ApiProperty()
  completed: boolean
}

// ... other code
```

In the code above, you define the request and response schemas for the create todo endpoint using the `@ApiProperty` decorator. The `@ApiProperty` decorator takes an optional argument to define the type, format, and nullable properties of the schema.

💡Don't forget to make a pull request of your work so your buddy can review your code and keep track of your progress. Keeping your PR's small and frequent is a good practice.

## PROJECT: Controller

Controllers are used to handle incoming requests and interact with the service layer to process the data. In this project, you will define a TodoController to handle the CRUD operations for the todo items.

### Controller Definition
The TodoController is a class that defines the API endpoints for the todo items. It includes the following methods to handle the CRUD operations for the todo items:

- **createTodo**: Create a new todo item.
- **getTodos**: Retrieve a list of all todo items.
- **getTodo**: Retrieve a specific todo item by its unique identifier.
- **updateTodo**: Update the title, description, and deadline of a todo item.
- **deleteTodo**: Delete a todo item by its unique identifier.
- **completeTodo**: Mark a todo item as completed.
- **uncompleteTodo**: Mark a completed todo item as uncompleted.

First we will create a new file called `todo.controller.ts` in the `src/modules/todo/controllers` folder and define the TodoController class with the specified methods.

```typescript
// src/modules/todo/controllers/todo.controller.ts

import { Body, Controller, Get, Param, ParseUUIDPipe, Post } from '@nestjs/common'
import { ApiResponse, ApiTags } from '@nestjs/swagger'
import { CreateTodoDto } from '../dtos/create-todo.dto.js'
import { TodoTransformerType } from '../transformers/user.transformer.js'

@ApiTags('Todo')
@Controller('todos')
export class TodoController {

  @Post()
  @ApiResponse({
    status: 201,
    description: 'The todo has been successfully created.',
    type: TodoTransformerType
  })
  async createTodo (
    @Body() createTodoDto: CreateTodoDto,
  ): Promise<void> {
      // ... create todo
  }

  @Get(':todo')
  @ApiResponse({
    status: 200,
    description: 'The todo has been successfully received.',
    type: UserTransformerType
  })
  async getTodo (
    @Param('todo', ParseUUIDPipe) todoUuid: string
  ): Promise<void> {
      // ... get todo
  }

}

```

In the code above, you define the TodoController class with the `createTodo` and `getTodo` methods to handle the create and get operations for the todo items. 

The `@Post` and `@Get` decorators are used to define the API endpoints for the create and get operations, and the `@ApiResponse` decorator is used to define the response schema for the API endpoints. 

The `@Body` and `@Param` decorators are used to extract the request body and URL parameters from the incoming requests. 

The `ParseUUIDPipe` is used to validate and parse the UUID parameter from the URL, more info about pipes can be found [here](https://docs.nestjs.com/pipes).

For now we use `Promise&lt;void&gt;` as return type, but we will change this later to the correct return type once we have the service and repository setup.

Also see the [NestJs documentation](https://docs.nestjs.com/controllers) for more information about controllers.

Now create the other methods for the controller!

💡Don't forget to make a pull request of your work so your buddy can review your code and keep track of your progress. Keeping your PR's small and frequent is a good practice.

## PROJECT: Module

Modules are used to organize the components of the application into cohesive units. In this project, you will define a TodoModule to encapsulate the related functionality for the todo items.

### Module Definition

The TodoModule is a class that defines the components of the application related to the todo items. It includes the following components:

- **Entity**: Define the data structure for a todo item.
- **Controller**: Define the controller for handling the CRUD operations for the todo items.
- **Service**: Define the service for handling the business logic for the todo items.
- **Repository**: Define the repository for interacting with the database for the todo items.

First we will create a new file called `todo.module.ts` in the `src/modules/todo` folder and define the TodoModule class with the specified components.

```typescript
// src/modules/todo/todo.module.ts

import { Module } from '@nestjs/common'
import { TypeOrmModule } from '@nestjs/typeorm'
import { Todo } from './entities/todo.entity'
import { TodoController } from './controllers/todo.controller'

@Module({
  imports: [TypeOrmModule.forFeature([Todo])],
  controllers: [TodoController],
  providers: [],
  exports: []
})
export class TodoModule {}
```

In the code above, you define the TodoModule class with the `imports`, `controllers`, `providers`, and `exports` properties. The `imports` property is used to import the TypeOrmModule to provide the Todo entity to the application. The `controllers` property is used to define the TodoController as a controller for the TodoModule. The `providers` and `exports` properties are used to define the service and repository components for the TodoModule.

Also see the [NestJs documentation](https://docs.nestjs.com/modules) for more information about modules.

After defining the TodoModule, you need to import the TodoModule into the root application module (`src/app.module.ts`) to make it available to the application. Now when you run the application (`pnpm start:dev`), the TodoModule will be loaded and the TodoController will be available to handle the API requests for the todo items and the documentation will be available in the [Swagger UI](http://localhost:3000/api).

💡Don't forget to make a pull request of your work so your buddy can review your code and keep track of your progress. Keeping your PR's small and frequent is a good practice.

## PROJECT: Repository

Repositories are used to interact with the database for the application. In this project, you will define a TodoRepository to interact with the database for the todo items.

### Repository Definition

The TodoRepository is a class that defines the methods to interact with the database for the todo items. 

First we will create a new file called `todo.repository.ts` in the `src/modules/todo/repositories` folder and define the TodoRepository class with the specified methods.

```typescript
import { EntityManager, Repository } from 'typeorm'
import { Injectable } from '@nestjs/common'
import { InjectEntityManager } from '@nestjs/typeorm'
import { Todo } from '../entities/todo.entity.js'

@Injectable()
export class TodoRepository extends Repository<Todo> {
  constructor (@InjectEntityManager() entityManager: EntityManager) {
    super(Todo, entityManager)
  }
}
```

In the code above, you define the TodoRepository class that extends the Repository class from TypeORM. The TodoRepository class includes the `constructor` method to inject the EntityManager and call the super constructor with the Todo entity and the EntityManager. This allows you to use the methods provided by the Repository class to interact with the database for the todo items. You can add custom methods to the TodoRepository class to handle the specific database operations for the todo items, like find all todos of a user, find a todo by its uuid, etc.

💡Don't forget to make a pull request of your work so your buddy can review your code and keep track of your progress. Keeping your PR's small and frequent is a good practice.

## PROJECT: Testing

At Wisemen we work with [test driven development](https://martinfowler.com/bliki/TestDrivenDevelopment.html). This means that we write tests before we write the actual code. This way we can make sure that the code we write is working as expected.

### E2E Testing
End-to-end (E2E) testing is a software testing method that tests the entire software application from start to finish. The purpose of E2E testing is to simulate real user scenarios and validate the system's integration with external interfaces.

First we will create a new file called `todo.e2e.test.ts` in the `src/modules/todo/tests` folder and define the TodoE2eTest class with the specified tests.

```typescript
// src/modules/todo/tests/todo.e2e.test.ts
import { after, before, describe } from 'node:test'
import { ValidationPipe, type INestApplication } from '@nestjs/common'
import { Test } from '@nestjs/testing'
import request from 'supertest'
import { HttpAdapterHost } from '@nestjs/core'
import { HttpExceptionFilter } from '../../../utils/Exceptions/http-exception.filter.js'
import { AppModule } from '../../../app.module'
import { UserSeeder } from '../../user/tests/user.seeder.js'
import { UserSeederModule } from '../../user/tests/user.seeder.module.js'


describe('Todo tests', async () => {
  let app: INestApplication
  let userSeeder: UserSeeder

  before(async () => {
    const moduleRef = await Test.createTestingModule({
      imports: [
        AppModule,
        UserSeederModule
      ]
    }).compile()

    app = moduleRef.createNestApplication()
    app.useGlobalPipes(
      new ValidationPipe({
        whitelist: true,
        forbidNonWhitelisted: true,
        transform: true,
        transformOptions: {
          enableImplicitConversion: true
        }
      })
    )

    const httpAdapterHost = app.get(HttpAdapterHost)

    app.useGlobalFilters(new HttpExceptionFilter(httpAdapterHost))

    userSeeder = moduleRef.get(UserSeeder)

    await app.init()
  })

  after(async () => {
    await app.close()
  })

})
```

In the above code, you define the TodoE2eTest class with the `before` and `after` hooks to set up and tear down the application for the tests. The `before` hook is used to create the application instance and set up the global pipes and filters, and the `after` hook is used to close the application instance after the tests are completed.

Now you need to add the tests for the create, get, update, delete, complete, and uncomplete operations for the todo items. In our tests we will check the following cases:

- **Unauthenticated**: Test the API endpoints without authentication.
- **Unauthorized**: Test the API endpoints with an unauthorized user.
- **Invalid Input**: Test the API endpoints with invalid input data.
- **Valid Input**: Test the API endpoints with valid input data.

```typescript
// src/modules/todo/tests/todo.e2e.test.ts

// ... setup

describe('Create todo', () => {
    it('should return 401 when not authenticated', async () => {
      const response = await request(app.getHttpServer())
        .post('/todos')

      expect(response.status).toBe(401)
    })

    it('should return 401 when not authorized', async () => {
      const { token } = await userSeeder.unAuthorizedUser()

      const response = await request(app.getHttpServer())
        .post('/todos')
        .set('Authorization', `Bearer ${token}`)
        .send({})

      expect(response.status).toBe(400)
    })

    it('should return 400 when body is empty', async () => {
      const { token } = await userSeeder.setupUser()

      const response = await request(app.getHttpServer())
        .post('/todos')
        .set('Authorization', `Bearer ${token}`)
        .send({})

      expect(response.status).toBe(400)
    })

    it('should return 200', async () => {
      const dto = todoSeeder.generateCreateTodoDto()

      const { token } = await userSeeder.setupUser()

      const response = await request(app.getHttpServer())
        .post('/todos')
        .set('Authorization', `Bearer ${token}`)
        .send(dto)

      expect(response.status).toBe(200)
    })
  })

   // ... other tests

```

In the above code, you can see we use Seeders to create the user and todo items for the tests. The `userSeeder` and `todoSeeder` are used to create the user and todo items with the specified data for the tests. The `generateCreateTodoDto` method is used to generate the create todo DTO with the specified data for the tests. In the following chapters we will create the seeders and the DTO generator.

### Seeder
Seeders are used to create the data for the tests. In this project, you will define a TodoSeeder to create the todo items for the tests.

First we will create a new file called `todo.seeder.ts` in the `src/modules/todo/tests` folder and define the TodoSeeder class with the specified methods.

```typescript
// src/modules/todo/tests/todo.seeder.ts

import { Injectable } from '@nestjs/common'

@Injectable()
export class TodoSeeder {
  generateCreateTodoDto (): CreateTodoDto {
    return {
      title: 'Test todo',
      description: 'Test description',
      deadline: new Date().toISOString()
    }
  }

   // ... other methods
}
```

In the code above, you define the TodoSeeder class with the `generateCreateTodoDto` method to generate the create todo DTO with the specified data for the tests. In this seeder you will also add todo items to the database to use in the tests.

### Test Module

Now you need to create a test module to provide the TodoSeeder to the application for the tests. First we will create a new file called `todo.seeder.module.ts` in the `src/modules/todo/tests` folder and define the TodoSeederModule class with the specified components.

```typescript
// src/modules/todo/tests/todo.seeder.module.ts

import { Module } from '@nestjs/common'
import { TodoSeeder } from './todo.seeder.js'

@Module({
  providers: [TodoSeeder],
  exports: [TodoSeeder]
})
export class TodoSeederModule {}
```

In the code above, you define the TodoSeederModule class with the `providers` and `exports` properties to define the TodoSeeder as a provider and export it to make it available to the application for the tests. Now you need to import the TodoSeederModule into the test module (`src/modules/todo/tests/todo.e2e.test.ts`) to make it available to the application for the tests.

Now run the tests with `pnpm test`, normally you will see the tests fail because we haven't implemented the methods yet. Now you can start implementing the methods and see the tests pass!

💡Don't forget to make a pull request of your work so your buddy can review your code and keep track of your progress. Keeping your PR's small and frequent is a good practice.

## PROJECT: Service

Services are used to handle the business logic for the application. In this project, you will define a TodoService to handle the CRUD operations for the todo items.

### Service Definition

The TodoService is a class that defines the methods to handle the business logic for the todo items.

First we will create a new file called `todo.service.ts` in the `src/modules/todo/services` folder and define the TodoService class with the specified methods.

```typescript
// src/modules/todo/services/todo.service.ts

import { Injectable } from '@nestjs/common'
import { TodoRepository } from '../repositories/todo.repository.js'
import { CreateTodoDto } from '../dtos/create-todo.dto.js'
import { Todo } from '../entities/todo.entity.js'

@Injectable()
export class TodoService {
  constructor (private readonly todoRepository: TodoRepository) {}

  async createTodo (createTodoDto: CreateTodoDto): Promise<Todo> {
    const todo = this.todoRepository.create(createTodoDto)

    return this.todoRepository.save(todo)
  }

  async getTodo (todoUuid: string): Promise<Todo> {
    return this.todoRepository.findOneOrFail(todoUuid)
  }

  // ... other methods
}
```

In the code above, you define the TodoService class with the `createTodo` and `getTodo` methods to handle the create and get operations for the todo items. The `createTodo` method is used to create a new todo item with the specified data, and the `getTodo` method is used to retrieve a specific todo item by its unique identifier. You can add other methods to the TodoService class to handle the update, delete, complete, and uncomplete operations for the todo items.

Add the service and repository as providers to the TodoModule and inject the TodoService into the TodoController to use the methods in the controller. You also need to export the TodoService in the module to make it available to the application.

Now you need to add the methods for the update, delete, complete, and uncomplete operations for the todo items. In these methods you will use the TodoRepository to interact with the database for the todo items.

Regularly run the tests with `pnpm test` to make sure that the methods are working as expected.

Once all methods are implemented and the tests are passing, you can make your final pull request and wait for the final feedback.

## Finishing Up
Congratulations! You have successfully completed our Wisemen NestJs workshop. Make sure that your project has been pushed to your repository and that you have created a pull request. Fix any remarks that you have received from your mentor and wait for the final feedback.