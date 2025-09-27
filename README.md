
POST: http://localhost:8080/pacientes
{
	"nome": "Arlan Henrique Pires de Oliveira",
    "email":"arlan@gmail.com",
    "cpf": "0000000000",
    "telefone": "11111111111",
    "endereco":{
        "logradouro":"Rua 7",
        "bairro":"Vila St Antonio",
        "cep": "12345688",
        "cidade": "Maringa",
        "uf": "PR",
        "numero":"7777",
        "complemento":"complemento"
    }
}

GET: http://localhost:8080/pacientes

PUT: http://localhost:8080/pacientes
{
    "id":1,
  "nome": "Arlan Henrique Oliveira",
  "telefone": "1559999",
  "endereco": {
    "logradouro": "Rua Nova",
    "bairro": "Vila St Antonio",
    "cep": "1654",
    "cidade": "Maringá",
    "uf": "PR",
    "numero": "7777",
    "complemento": "ap 107"
  }
}
DELETE: http://localhost:8080/pacientes/9 <- passar ID 
