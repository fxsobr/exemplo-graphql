# Exemplo Graphql

## Implementação Graphql utilizando GO

### Rodando o Projeto
> go run .\server.go

# Queries

## Categorias
### Criando uma nova Categoria
```GraphQL
mutation createCategory {
  createCategory(input: {name: "Python", description: "Python is Awesome!"}) {
    id
    name
    description
  }
}
```
### Listando Categorias
```GraphQL
query findCategories {
  categories {
    id
    name
    description
    courses {
      name
    }
  }
}
```
### Resultado
```GraphQL
{
  "data": {
    "categories": [
      {
        "id": "T5577006791947779410",
        "name": "Python",
        "description": "Python is Awesome!",
      }
    ]
  }
}
```

## Cursos
### Criando um novo Curso
```GraphQL
mutation createCourse {
  createCourse(
    input: {
      name: "Flask for Dummies"
      description: "Flask Course"
      categoryId: "T5577006791947779410"
    }
  ) {
    id
    name
    description
    category {
      id
      name
    }
  }
}
```
### Listando Cursos
```GraphQL
query findCourses {
  courses {
    id
    name
    description
    category {
      id
      description
    }
  }
}
```
### Resultado
```GraphQL
{
  "data": {
    "courses": [
      {
        "id": "T8674665223082153551",
        "name": "Flask for Dummies",
        "description": "Flask Course",
        "category": {
          "id": "T5577006791947779410",
          "description": "Python is Awesome!"
        }
      }
    ]
  }
}
```
## Capitulos
### Criando um novo capitulo
```GraphQL
mutation createChapter {
  createChapter(
    input: {
      name: "Introduction to Flask"
      courseId: "T8674665223082153551"
    }
  ) {
    id
    name
    course {
      name
    }
  }
}
```
### Listando Capitulos
```GraphQL
query findChapters {
  chapters {
    id
    name
    course {
      name
    }
  }
}
```
### Resultado
```GraphQL
{
  "data": {
    "chapters": [
      {
        "id": "T6129484611666145821",
        "name": "Introduction to Flask",
        "course": {
          "name": "Flask for Dummies"
        }
      }
    ]
  }
}
```