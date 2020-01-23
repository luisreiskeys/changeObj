# changeObj
function to change easly a multi level object item

Essa função criei para me facilitar em alguns formluários. Estava desenvolvendo um app em React-Native para consumo de uma api já em produção.

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

e com esse retono eu montava um formaulário de edição. Esse exemplo está bem simplificado, normalmente a api retornava um objeto bem maior, em média com 5 níveis.

Enfim, para exibir os dados do objeto na input era bem simples. Guardava o objeto inteiro numa váriável de estado e chamava esse campo no value do componente Input.

ex: Input para o Logradouro

<TextInput 
    value={retorno.lead.endereco.logradouro} 
/>

Nesse caso quando abria a tela de edição do user a input de logradouro recebia o valor do campo logradouro que veio no objeto de retorno.

Agora para editar o usuário a api tbm pedia como post um objeto, no mesmo padrão que ela me enviava, então não tinha como eu postar apenas o logradouro por exemplo, caso tivesse sido esse o único campo alterado.

O que eu fiz foi criar uma função que alterava um campo específico dentro de um objeto, sendo assim eu editava apenas aquele campo e postava de volta o objeto para a api.

seguindo o exemplo acima a chamada da função ficaria assim:

<TextInput 
    value={retorno.lead.endereco.logradouro}
    onChangeText={(txt)=> changObjState(retorno,['lead','endereco','logradouro'],txt)} 
/>

o que essa função faz é desmembrar o objeto em um array até chegar ao nível que eu quero editar, depois de editar eu refaço e retorno o objeto.

