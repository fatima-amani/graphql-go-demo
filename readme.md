# GraphQL Demo with Go

## Table of Contents
- [Introduction](#introduction)
- [Features](#features)
- [Prerequisites](#prerequisites)
- [Installation](#installation)
- [Usage](#usage)
- [Project Structure](#project-structure)
- [Technologies Used](#technologies-used)
- [References](#references)

## Introduction
GraphQL is a query language for APIs that provides a more efficient and flexible alternative to REST. This project showcases how to implement a GraphQL server in Go, enabling developers to query and mutate data with ease.

## Features
- GraphQL API implementation in Go.
- Query and mutation support.
- Example schema and resolver setup.
- Lightweight and easy to extend.

## Prerequisites
Before running this project, ensure you have the following installed:
- Go (1.18 or later)
- Git

## Installation
1. Clone the repository:
    ```bash
    git clone https://github.com/fatima-amani/graphql-go-demo.git
    cd graphql-go-demo
    ```

2. Install dependencies:
    ```bash
    go mod tidy
    ```

3. Run the server:
    ```bash
    go run main.go
    ```

## Usage
Once the server is running, you can access the GraphQL playground at `http://localhost:8080`. Use the playground to test queries and mutations.

### Example Query
```graphql
query characters($cliqueType: CliqueType!) {
	characters(cliqueType: $cliqueType) {
		id
		name
	cliqueType
	}
}
```

```variables
{
  "cliqueType": "KOOKS"
}
```

### Example Mutation
```graphql
mutation upsertCharacter($input: CharacterInput!) {
  upsertCharacter(input: $input) {
    name
    id
    cliqueType
    isHero
  }
}
```

```variables
{
  "input":{
    "name":"Fatima",
    "cliqueType":"KOOKS",
    "isHero":true
  }
}
```


## Project Structure
```
graphql-demo/
├── main.go          # Entry point of the application
├── graph/
│   ├── schema.graphql # GraphQL schema definition
│   ├── resolver.go    # Resolver functions
│   └── models.go      # Data models
├── go.mod           # Go module file
└── go.sum           # Dependency lock file
```

## Technologies Used
- [Go](https://golang.org): Programming language.
- [gqlgen](https://github.com/99designs/gqlgen): GraphQL server library for Go.

## References
- [Using GraphQL with Golang](https://www.apollographql.com/blog/using-graphql-with-golang)
- [gqlgen Documentation](https://gqlgen.com/)
