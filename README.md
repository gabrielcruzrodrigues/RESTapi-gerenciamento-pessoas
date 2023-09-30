# EndPoints

#### POST /person 
cria nova pessoa.
- por padrão, as pessoas não são cadastradas com logradouros;
* body:
```
{
    "name": "pedro",
    "dateOfBirth": "1998-09-27"
}
```

#### PUT /person/:id 
Atualiza registro da uma pessoa indicada pelo id.
* body:
```
{
    "name": "pedro",
    "dateOfBirth": "1998-09-27"
}
```
#### GET /person/:id 
Busca pessoa por id.
```
{
    "id": 2,
    "name": "samuca",
    "dateOfBirth": "2002-01-22",
    "publicPlaces": [
        {
            "id": 1,
            "publicPlace": "Rua z",
            "cep": "12347890",
            "number": "46",
            "city": "jequie",
            "main": true
        }
    ]
}
```

#### GET /person
Lista todas as pessoas.
```
[
    {
        "id": 1,
        "name": "ana",
        "dateOfBirth": "2022-01-22",
        "publicPlaces": []
    },
    {
        "id": 2,
        "name": "pedro",
        "dateOfBirth": "1998-09-27",
        "publicPlaces": []
    }
]
```

#### POST /publicPlace/:id
cria endereço (publicPlace) para pessoa indicada pelo id.
- por padrão, o primeiro endereço criado para uma pessoa, sera o seu endereço principal atual, você pode alterar isso usando o `PUT /publicPlace/main/:id`, listado logo abaixo.
* body:
```
{
    "publicPlace": "Rua z",
    "cep": "12347890",
    "number": "46",
    "city":"ilheus"
}
```
#### GET /person/publicPlaces/:id
Lista todos os endereços de uma pessoa.
```
[
    {
        "id": 1,
        "publicPlace": "Rua A",
        "cep": "12347890",
        "number": "19",
        "city": "Salvador",
        "main": true
    },
    {
        "id": 2,
        "publicPlace": "Rua z",
        "cep": "12347809",
        "number": "46",
        "city": "jequie",
        "main": false
    },
```

#### GET /publicPlace/main/:id
Lista o logradouro principal da pessoa.
```
{
    "id": 1,
    "publicPlace": "Rua z",
    "cep": "12347890",
    "number": "46",
    "city": "jequie",
    "main": true
}
```

#### PUT /publicPlace/main/:id
Atualiza o logradouro principal da pessoa.
* body:
```
{
    "id": 2
}
```
