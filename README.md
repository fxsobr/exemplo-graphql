# Exemplo Graphql

## Implementação Graphql utilizando GO

### Rodando o Projeto
> go run .\server.go

# Queries

## Categorias
### Criando uma nova Categoria
```GraphQL
mutation createCategory {
  createCategory(input: {name: "Graphql for Dummies", description: "Graphql and Go Example"}) {
    id
    name
    description
  }
}
```
### Listando Categorias


## Cursos
### Criando um novo Curso

### Listando Cursos

## Capitulos
### Criando um novo capitulo

### Listando Capitulos
