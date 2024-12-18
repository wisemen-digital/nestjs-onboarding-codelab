author: Jonas Vannieuwenhuijsen
summary: Onboarding Code Lab
id: index
tags:
categories:
environments:
status: Draft

# Wisemen Circle Node.js Onboarding 

## Welcome to Circle Node.js at **Wisemen!**

  <img width="200" src="img/projectSetup/Wisemen_Logo_Acid.png">

### Welcome to the Node.js onboarding 👋!  
Strap in and get ready to learn how we build killer apps at wisemen 🔥.


#### You will learn how to work with
 - [Typescript](https://www.typescriptlang.org/docs/handbook/intro.html): Because a world without types is no world to live in
 - [Node.js](https://nodejs.org/en/learn/getting-started/introduction-to-nodejs): The cornerstone of our backend applications
 - [NestJS](https://docs.nestjs.com/): A backend framework on top of Node.js with a lot of cats? 🐈‍⬛
 - [TablePlus](https://docs.tableplus.com/): The database management tool with the best mascot 🐘 (we like elephant themed software)
 - [Figma](https://www.figma.com/): The tool designers at Wisemen use to take our breath away 🎨
 - [Github](https://github.com/): Where we store our precious code 🤩
 - [Linear](https://linear.app/wisemen): Did you get any tickets yet? 🤨


#### This onboarding is designed to be completed in roughly 3 to 4 days
This does not mean you have to complete it in 3-4 days.  
People with more experience will be able to complete it faster than people with less experience.  
Go at your own pace and be sure to ask for help when needed from your buddy or a member of our circle 🤝.

#### You will be working on a small to-do app 📋
This app wil teach you our core conventions and ways of working in Node.js backends.  
We expect you to make **pull request** of your work so your buddy can review your code and keep track of your progress 🫣.  
Don't know how to make pull requests yet? No worries more wil be explained on the next page.

Good luck!!!


## What you'll need ️🛠️: iTerm2

### Node.js

Being a part of our Node.js circle requires you to have ... well, Node.js 😅.
But to get Node.js we'll start by setting up your terminal and installing Homebrew 🍺, a popular package manager for MacOS.

### Installing iTerm2

The unleash your full hacker-man potential 😎 we'll install [iTerm2](https://iterm2.com/) to replace the default MacOS terminal.

1. **Install iTerm2**:  
  Download the latest version of iTerm2 from [https://iterm2.com](https://iterm2.com).


2. **Install Oh My Zsh**:  
  [Oh My Zsh](https://ohmyz.sh/) brings a lot of new goodies and allows for better completion on commands through plugins.  
  Open Term2 and run the following command:
    ```bash
    sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
    ```
    This command will download and install Oh My Zsh and set Zsh as your default shell.


3. **Install the recommend fonts**:

    Download each file. Double-click on each file followed by clicking on "Install". This will make `MesloLGS NF` font available to all applications on your system.
   - [MesloLGS NF Regular.ttf](
     https://github.com/romkatv/powerlevel10k-media/raw/master/MesloLGS%20NF%20Regular.ttf)
   - [MesloLGS NF Bold.ttf](
     https://github.com/romkatv/powerlevel10k-media/raw/master/MesloLGS%20NF%20Bold.ttf)
   - [MesloLGS NF Italic.ttf](
     https://github.com/romkatv/powerlevel10k-media/raw/master/MesloLGS%20NF%20Italic.ttf)
   - [MesloLGS NF Bold Italic.ttf](
     https://github.com/romkatv/powerlevel10k-media/raw/master/MesloLGS%20NF%20Bold%20Italic.ttf)

   

4. **Install Powerlevel10k**:  
    Run the following command:  
    ```bash
    git clone --depth=1 https://github.com/romkatv/powerlevel10k.git ${ZSH_CUSTOM:-$HOME/.oh-my-zsh/custom}/themes/powerlevel10k
    ```

    Add or change the line `ZSH_THEME="powerlevel10k/powerlevel10k"` in `~/.zshrc`  
    Restart Zsh with `exec zsh`.


5. **Configure Powerlevel10k**:  
   Run the following command:
    ```bash
    p10k configure
    ```
    This command will start the configuration wizard. Follow the instructions to customize your prompt.

_To complete your hacker man arc try out some definitely useful tools like lolcat and cowsay.
Be sure to share any other essential tools for iTerm overlords you know of 👑_

## What you'll need ️🛠️: Homebrew 🍺
### Installing Homebrew 🍺

1. **Install Homebrew** (if not already installed)   
   Open a terminal and run the following command:

   ```bash
   /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
   ```

2. **Update Homebrew**: Before installing any packages, it's a good idea to update Homebrew to the latest version. Run the following command to do so:

   ```bash
   brew update
   ```

_Did you know that our circle lead also home brews his own beers?_ 😋🍺

## What you'll need ️🛠️: Node.js 
### Installing Node.js

1. **Install Node.js**:  
   Now that Homebrew is installed and updated, you can install Node.js by running the following command:

   ```bash
   brew install node
   ```

   This command will install the latest stable version of Node.js on your system.  
  Verify your installation with:
  
   ```bash
   node --version
   npm --version
   ```

   If both commands return version numbers, Node.js and npm are installed successfully.


2. **Install pnpm**:  
    We use [pnpm](https://pnpm.io/) as our package manager for Node.js. To install pnpm, run the following command:

   ```bash
   npm install -g pnpm
   ```

   This command will install the latest version of pnpm and make it available system-wide.


3. **Install TypeScript**:   
   We use [TypeScript](https://www.typescriptlang.org/docs/handbook/intro.html) as our programming language. To install TypeScript, run the following command:

   ```bash
   npm install -g typescript
   ```  
    This command will install the latest version of TypeScript and make it available system-wide.  
    Verify your typescript installation with:
    
     ```bash
     tsc --version
     ```
    
    If the command returns a version number, TypeScript is installed correctly.

## What you'll need ️🛠️: VCS
### Version Control

#### Git 
Our preferred version control system at Wisemen.  
It should come preinstalled on your mac. You can verify your installation with:
```bash
git -v
```
If you are not familiar with git, you can learn it here in an interactive way:
[Learn Git](https://learngitbranching.js.org/)

#### Github

We use Github (and previously [Bitbucket](https://bitbucket.org/appwise/workspace/overview)) as our repository hosting service.  
Your future projects will be hosted on Github. So be sure to link your Wisemen work email to your personal github account our make a new work account before continuing.  
If you have not received an invite for the Wisemen github organisation be sure to ask your budy about it.

[Wisemen Github](https://github.com/wisemen-digital)

Here is great article to get you started with github:
[Github Git tutorial](https://docs.github.com/en/get-started/quickstart/hello-world)   🤓  
It also teaches you how to create **pull requests**, so keep this tab open for when you make your first pull request 🤞. 

_I can't see the main for the branches anymore_ 😵‍💫

## What you'll need ️🛠️: IDE

There are 2 different IDEs in use at Wisemen. You can use either **Visual Studio Code** or **WebStorm**.

#### Visual Studio Code
Visual Studio Code is an editor developed by Microsoft for Windows, Linux and macOS.
It includes support for debugging, syntax highlighting, intelligent code completion, snippets, and code refactoring.

Visual Studio Code is a free IDE. You can download it from the [website](https://code.visualstudio.com/download).

#### WebStorm
WebStorm is a JavaScript and Typescript IDE with a complete set of tools for client-side and server-side development and testing.
It provides code completion, on-the-fly error detection, powerful navigation and refactoring for JavaScript, TypeScript, CSS, HTML and more.

Webstorm is a paid IDE. You can get a license from Wisemen. Ask your buddy!

[Download WebStorm](https://www.jetbrains.com/webstorm/download)

_Opinions differ on which IDE is best. In truth both IDEs are fine, choose the one which supports your way of working the best_ 🙌


## What you'll need ️🛠️: Figma

Our talented designers work with **Figma** 👩‍🎨🧑‍🎨.  
Figma is a browser-based vector graphics editor and prototyping tool.
We recommend you to install the desktop app.

[Download Figma](https://www.figma.com/downloads/)

Take a look around in Figma and try to get familiar with the tool. You will be using it a lot in the future.
You can view all of our designs here:

[Wisemen Figma](https://www.figma.com/files/team/1070403287155222588/Wisemen?fuid=1070747045190465434)

To access the designs you need, you need to log in with your Wisemen account.
The designs you need for this onboarding are: [Todo-app designs](https://www.figma.com/file/hebgv4Qx8VanMAQkO1NFpa/Onboarding-to-do?node-id=407-4095&t=2qdyy89lKwN7dFw3-0)

We commonly leave notes on designs as feedback to our designers, but be sure to have a talk face to face as well 😄 or else...

  <img width="200" src="img/afbeelding-voor-noodgevallen.png">

_Figma balls_ 🍒


<!-- ### Jira access

For this onboarding you will be working with Jira to track your progress. You can find the Jira board here:
[Jira Todo]()

Jira is used to track the progress of your project and manage the tasks that need to be done.
All the requirements for the to-do app are in the Jira. You will be creating tasks in the Jira to keep track of your progress. (weet niet of ze zelf ticketjes hiervoor moeten maken of we ze dat geven?)

The Jira contains all the requirements for creating the to-do app.

*ToDo: Add link to Jira* -->

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

You can kickstart your new project without starting from square one by using the [Wisemen NestJS Template Project](https://github.com/wisemen-digital/nestjs-template). This repository already includes authentication and a user entity, providing a solid foundation for your project. If at any point you are stuck, take a peek into the auth of user module, you might find great examples there!
Fork this project into your own repository on Github.

### 2. Package.json

The package.json file is used manage the project's dependencies and predefined run commands.

```json
{
  "name": "nestjs-example",
  "version": "0.0.1",
  "description": "",
  "author": "",
  "private": true,
  "license": "UNLICENSED",
  "type": "module",
  "scripts": {
    "clean": "rm -rf ./dist",
    "build": "nest build",
    "format": "prettier --write \"src/**/*.ts\" \"test/**/*.ts\"",
    "start": "node dist/src/main.js",
    ...
  },
  "dependencies": {
    "@appwise/express-dto-router": "^1.1.5",
    "@appwise/oauth2-server": "^0.0.10",
    "@appwise/transformer": "^0.0.2",
    "@nestjs/common": "^10.2.4",
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


### 3. Environment variables

#### Generating RSA keys

To generate the RSA keys execute the following in at your project folder:

   ```bash
   openssl genrsa -des3 -out private.pem 2048
   openssl rsa -in private.pem -outform PEM -pubout -out public.pem
   cat private.pem | base64 '<-- Your RSA_PRIVATE'
   cat public.pem | base64 '<-- Your RSA_PUBLIC'
   ```
_Note: during private generation a passphrase is required, this is RSA_PASSPHRASE_



Create an .env file and add the following:

```dotenv
TYPEORM_URI = postgresql://postgres:password@127.0.0.1:5432/todo # PSQL link
REFRESH_TOKEN_LIFETIME = 300 # 5 minutes
RSA_PRIVATE = "your private key"
RSA_PUBLIC = "your public key"
RSA_PASSPHRASE = "your password
```

### 4. PostGis Database Setup

#### Requirements
1. Docker Desktop
2. Install TablePlus through Setapp

#### Docker setup

Download and install the requirements above. Once these are installed we can execute the following command in the terminal: `docker compose up`. This will pull all the necessary images and start the database.

#### Connecting with TablePlus
(TablePlus can be downloaded though SetApp)

Open TablePlus, click on 'create new connection' and select PostgreSQL. <br />
Name: `any` <br />
Host/Socket : `localhost` <br />
Port: `5432` <br />
User: `postgres` <br />
Password: `password` <br />
Database: `test_db`<br />

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

2. **Command and response**: Create commands to transfer data between layers and responses to convert to the correct response.

3. **Controller**: Implement the API controllers to handle incoming requests and interact with the service layer.

4. **Module**: Organize the components into a module to encapsulate the related functionality.

5. **Tests**: Write comprehensive tests to ensure the reliability and correctness of your code.

6. **Use case and Repository**: Develop the service layer to handle business logic and the repository layer to interact with the database.

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

Run the following command in your terminal:

```bash
pnpm typeorm migration:generate src/config/sql/migrations/CreateTodoEntity
```

This command creates a new migration file with the name `CreateTodoEntity.ts`. Add the generated migration class to the `migrations` folder which can be found `src/config/sql/migrations`.

💡Don't forget to make a pull request of your work so your buddy can review your code and keep track of your progress. Keeping your PR's small and frequent is a good practice.

## USE CASE: Create Todo (1/5)
### Command
Commands are used to defines how the data will be sent over the network. The commands will validate the data and transform it to the correct format before sending it to the controller.

First we will create a command for creating a todo item. Create a new file called `create-todo.command.ts` in the `src/modules/todo/use-cases/create-todo` folder and define the CreateTodoCommand class with the specified fields.

```typescript
// src/modules/todo/use-cases/create-todo/create-todo.command.ts

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

In the code above, you define the CreateTodoCommand class with the `title`, `description`, and `deadline` fields. The `@IsNotEmpty` decorator is used to validate that the `title` field is not empty, and the `@IsString` decorator is used to validate that the `description` field is a string. The `@IsDateString` decorator is used to validate that the `deadline` field is a valid date string. The `@IsNullable` decorator is used to allow the `description` and `deadline` fields to be nullable.

To view all possible decorators using class-validator, see [docs](https://github.com/typestack/class-validator)

💡Don't forget to make a pull request of your work so your buddy can review your code and keep track of your progress. Keeping your PR's small and frequent is a good practice.

### Response
Responses are used to define the data structure for the response of the API endpoints. The responses will transform the data to the correct format before sending it to the frontend.

Create a new file called `create-todo.response.ts` in the `src/modules/todo/use-cases/create-todo` folder and define the CreateTodoResponse class with the specified fields.

```typescript
export class CreateTodoResponse {
  uuid: string

  constructor (todo: Todo) {
    this.uuid = todo.uuid
  }
}
```

We only return the necessary data in the response. In this case, we only return the `uuid` so that the frontend can use it to retrieve the todo item later with the detail call.

On updates and deletes, we will return no data, only a status code.

### Documentation
To document the API endpoints, you will use the `@ApiProperty` decorator from the `@nestjs/swagger` package to define the request and response schemas for the API endpoints.

First we will edit the `create-todo.command.ts` file in the `src/modules/todo/use-cases/create-todo` folder and add the `@ApiProperty` decorator to the `CreateTodoCommand` class to define the request schema for the create todo endpoint.

```typescript
// src/modules/todo/dtos/create-todo.dto.ts

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

Don't forget to add the `@ApiProperty` decorator to the `CreateTodoResponse` class in the `create-todo.response.ts` file to define the response schema for the create todo endpoint.

💡Don't forget to make a pull request of your work so your buddy can review your code and keep track of your progress. Keeping your PR's small and frequent is a good practice.

## USE CASE: Create Todo (2/5)
### Controller

Controllers are used to handle incoming requests and interact with the service layer to process the data. We will create a controller for every use case.

### Controller Definition
The CreateTodoController is a class that defines the API endpoints for the creation of todo items.

Create a new file called `create-todo.controller.ts` in the `src/modules/todo/use-cases/create-todo` folder and define the CreateTodoController class with the specified methods.

```typescript
// src/modules/todo/use-cases/create-todo/todo.controller.ts

@ApiTags('Todo')
@Controller('todos')
export class TodoController {

  @Post()
  @ApiCreatedResponse({ type: CreateTodoResponse })
  async createTodo (
    @Body() createTodoCommand: CreateTodoCommand,
  ): Promise<void> {
    // Not implemented
  }
}

```

In the code above, you define the TodoController class with the `createTodo` method to handle the create operations for the todo items.

The `@Post` decorators is used to define the API endpoints for the create operations, and the `@ApiResponse` decorator is used to define the response schema for the API endpoints.

The `@Body` decorators is used to extract the request body from the incoming requests.

For now we use `Promise&lt;void&gt;` as return type, but we will change this later to the correct return type once we have the use-case setup.

Also see the [NestJs documentation](https://docs.nestjs.com/controllers) for more information about controllers.

### Authentication

We should prevent unauthenticated users from accessing certain endpoints of our API. In our project template, we already built the logic that will help us protect our endpoints. Have a look into `app.module.ts`, you'll see that we defined some global guards that will protect all endpoints in our application.

Furthermore, have a look into the auth and user module, where all the authentication and user management logic is built.

Also see the [NestJs documentation](https://docs.nestjs.com/security/authentication) for more information about security and authentication.


💡Don't forget to make a pull request of your work so your buddy can review your code and keep track of your progress. Keeping your PR's small and frequent is a good practice.

## USE CASE: Create Todo (3/5)
### Module

Modules are used to organize the components of the application into cohesive units. We will create a module for every use case. We will create also a module that encapsulates all modules related to the todo items called `TodoModule`. This module will be imported into the root application module to make it available to the application.

### Module Definition

The CreateTodoModule is a class that defines the components of the application related to the creation of todo items. It includes the following components:

- **Entity**: Define the data structure for a todo item.
- **Controller**: Define the controller for handling the operations for the todo items.
- **Use case**: Define the service for handling the business logic for the todo items.

First we will create a new file called `create-todo.module.ts` in the `src/modules/todo/use-cases/create-todo` folder and define the CreateTodoModule class with the specified components.

```typescript
// src/modules/todo/use-cases/create-todo/create-todo.module.ts

@Module({
  imports: [TypeOrmModule.forFeature([Todo])],
  controllers: [TodoController],
  providers: [],
  exports: []
})
export class CreateTodoModule {}
```

In the code above, you define the TodoModule class with the `imports`, `controllers`, `providers`, and `exports` properties. The `imports` property is used to import the TypeOrmModule to provide the Todo entity to the application. The `controllers` property is used to define the TodoController as a controller for the TodoModule. The `providers` and `exports` properties are used to define the service and repository components for the TodoModule.

Also see the [NestJs documentation](https://docs.nestjs.com/modules) for more information about modules.

After defining the CreateTodoModule, you need to created a `todo.module.ts` file in the todo folder that imports the CreateTodoModule. This TodoModule needs to be imported into the root application module (`src/app.module.ts`) to make it available to the application. Now when you run the application (`pnpm start:dev`), the TodoModule will be loaded and the TodoController will be available to handle the API requests for the todo items and the documentation will be available in the [Swagger UI](http://localhost:3000/api/docs).

💡Don't forget to make a pull request of your work so your buddy can review your code and keep track of your progress. Keeping your PR's small and frequent is a good practice.

## Use Case: Create Todo (4/5)
### Testing

At Wisemen we work with [test driven development](https://martinfowler.com/bliki/TestDrivenDevelopment.html). This means that we write tests before we write the actual code. This way we can make sure that the code we write is working as expected.

### E2E Testing
End-to-end (E2E) testing is a software testing method that tests the entire software application from start to finish. The purpose of E2E testing is to simulate real user scenarios and validate the system's integration with external interfaces.

First we will create a new file called `todo.e2e.test.ts` in the `src/modules/todo/tests` folder and define the TodoE2eTest class with the specified tests.

```typescript
// src/modules/todo/use-cases/create-todo/create-todo.e2e.test.ts
import { before, describe, after } from 'node:test'
import type { DataSource } from 'typeorm'
import { NestExpressApplication } from '@nestjs/platform-express'
import { setupTest } from '../../../../../test/setup/test-setup.js'
import { TestContext } from '../../../../../test/utils/test-context.js'
import type { TestUser } from '../../../users/tests/setup-user.type.js'
import { RoleSeeder } from '../../tests/seeders/role.seeder.js'
import { Role } from '../../entities/role.entity.js'
import { RoleEntityBuilder } from '../../tests/builders/entities/role-entity.builder.js'

describe('Create todo', () => {
  let app: NestExpressApplication
  let dataSource: DataSource

  let context: TestContext

  let adminUser: TestUser
  let readonlyUser: TestUser

  before(async () => {
    ({ app, dataSource, context } = await setupTest())

    adminUser = await context.getAdminUser()
    readonlyUser = await context.getReadonlyUser()
    
  })

  after(async () => {
    await app.close()
  })
})
```

In the above code, you define the TodoE2eTest class with the `before` and `after` hooks to set up and tear down the application for the tests. The `before` hook is used to create the application instance and set up the global pipes and filters, and the `after` hook is used to close the application instance after the tests are completed.

Now you need to add the tests for the create operations for the todo items. In our tests we will check the following cases:

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
      const response = await request(app.getHttpServer())
        .post('/todos')
        .set('Authorization', `Bearer ${readonlyUser.token}`)
        .send({})

      expect(response.status).toBe(400)
    })

    it('should return 400 when body is empty', async () => {
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

      const { token } = await userSeeder.setupUser()

      const response = await request(app.getHttpServer())
        .post('/todos')
        .set('Authorization', `Bearer ${adminUser.token}`)
        .send(dto)

      expect(response.status).toBe(201)
    })
  })

   // ... other tests

```

In the above code, you can see we use a builder to create the createTodoCommand. The `CreateTodoCommandBuilder` is used to create command with specified data for the tests. 

### Builders
Builders are used to create the data for the tests. In this project, you will define a CreateTodoCommandBuilder to create the command for the tests.

First we will create a new file called `create-todo-command.builder.ts` in the test folder of the use case and define the CreateTodoCommandBuilder class with the specified methods.

```typescript
// src/modules/todo/use-cases/create-todo/tests/create-todo-command.builder.ts

export class CreateTodoCommandBuilder {
  private command: CreateTodoCommand

  constructor () {
    this.command = new CreateTodoCommand()
    this.command.title = 'Test Todo'
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

In the code above, you define the CreateTodoCommand class. Here you can see that all the necessary fields are set to a default value in the constructor. You can use the `withTitle`, `withDescription`, and `withDeadline` methods to set the specified data for the tests. The `build` method is used to return the created command with the specified data.

Builders are also used to create entities for the tests. For the update and delete tests you will need to create a Todo entity builder to insert the data into the database. So you can perform the update and delete operations on existing data.

### Running tests

Have a look into the `.env.test` file, this environment file is used when running the tests. Make sure you postgis docker container is running and matches your environment settings.

Now run the tests with `pnpm test`, normally you will see the tests fail because we haven't implemented the methods yet. Now you can start implementing the methods and see the tests pass!

💡Don't forget to make a pull request of your work so your buddy can review your code and keep track of your progress. Keeping your PR's small and frequent is a good practice.

## Use Case: Create Todo (5/5)
### Use Case

Use case are used to handle the business logic for the application. In this example we will create a use case for the creation of a todo item. The use case will use the TodoRepository to interact with the database for the todo items.

### Use Case Definition

The CreateTodoUseCase is a class that defines the methods to handle the business logic for the todo items.

First we will create a new file called `create-todo.use-case.ts` in the use case folder and define the CreateTodoUseCase class with the specified methods.

```typescript
// src/modules/todo/services/todo.service.ts

@Injectable()
export class CreateTodoUseCase {
  constructor (
    @InjectRepository(Todo)
    private todoRepository: Repository<Todo>,
  ) {}

  async execute (command: CreateTodoCommand): Promise<CreateTodoResponse> {
    const todo = this.todoRepository.create(command)
    await this.todoRepository.insert(todo)

    return new CreateTodoResponse(todo)
  }
}
```

In the code above, you define the CreateTodoUseCase class with the `execute` method to handle the create operation for the todo items. The `execute` method is used to create a new todo item with the specified data.

Add the use case as a provider to the CreateTodoModule and inject the CreateTodoUseCase into the CreateTodoController to use the methods in the controller. 

Regularly run the tests with `pnpm test` to make sure that the methods are working as expected.


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
Congratulations! You have successfully completed our Wisemen NestJs workshop. Make sure that your project has been pushed to your repository and that you have created a pull request. Fix any remarks that you have received from your mentor and wait for the final feedback.
