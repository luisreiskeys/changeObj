# changeObj
function to change easly a multi level object item

Essa função criei para me facilitar em alguns formluários. Estava desenvolvendo um app para consumo de uma api já em produção.

Em alguns formulários a api me retornava todas as informações em um único objeto ex:

retorno:
{
    "mensagem": "string",  - caso tenha erro de validação

    "codigo": "int",
    "finalidade": "string",
    "situacao": "string",
    "leadqualificado": "bool",
    "lead": {
        "tipo": "int",
        "codigo": "int",
        "nome": "string",
        "cpfcnpj": "string",
        "telefone1": "string",
        "endereco": {
           "logradouro": "string",
           "numero": "int",
           "CEP": : "int",
           "bairro": "string",
           "cidade": "string",
           "estado": "string",
           "complemento":"string"
        }
    }
}

e com esse retono eu montava um formaulário de edi
