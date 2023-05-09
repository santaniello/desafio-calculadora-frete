# Desafio Calculadora Frete 

## FASE 1

***Objetivo:*** Criar uma aplicação que baseada em um produto e no endereço do cliente, seja calculado o valor do frete e impresso no console.

Exemplo do que deve ser impresso no Console :

```
Produto: Geladeira
UF: SP
Valor do Frete: 15,00
```

### Regras 

- As classes devem estar dentro de um pacote cujo nome é a junção do groupid e do artifactid do maven (br.com.happycode.desafiofrete);
  - Olhe o arquivo pom.xml que você irá ver o groupid e o artifactid (só por curiosidade);
  - Dica: De uma olhada no seguinte video para entender mais sobre a estrutura de um projeto Maven: https://www.youtube.com/watch?v=ZQICkNszEuI
- O cliente deverá conter as seguintes informações: 
  - nome;
  - data de aniversario;
    - A data de aniversario do cliente deverá utilizar a nova api de datas do Java 8 (Pesquise na internet);
    - Link que pode ajudar: https://www.alura.com.br/artigos/conheca-a-nova-api-de-datas-do-java-8
  - cep;
    - O cep deve estar dentro das seguintes regras:
      - O cep deve aceitar zeros a esquerda. Exemplo: 02123040;
      - O cep deve conter exatamente 8 dígitos numéricos;
      - Não pode ter letras ou caracteres especiais;
      - Caso o Cep seja invalido, você deve lançar a exceção IllegalArgumentException do Java, trata-la e exibir a seguinte mensagem no console: "Cep invalido ! o formato correto deveria ser XXXXXXXX"
        - Dica: Se precisar, revise o capitulo 12 da apostila;
      - Se o usuário mandar um cep com mascara (hifen) exemplo: 021023-040, você deve remover esse hifen exemplo: 02123040;
      - Dicas:
          - Estude sobre o pacote java.lang.String (Cap: 13 da apostila);
          - Link util: https://www.devmedia.com.br/java-string-manipulando-metodos-da-classe-string/29862

  - logradouro;
  - cidade;
  - uf;
    - A uf deve ser um estado do Brasil valido. Exemplo: SP, MG, RJ e etc ...
    - Dicas:
      - Você pode utilizar uma enum para representar a uf ao invés de String;
      - Link util: https://www.devmedia.com.br/enums-no-java/38764
- O produto deverá conter as seguintes informações:
  - descrição;
  - valor;
    - Pode utilizar Double como tipo;
    - O valor do produto não pode ser nulo ou zero, caso seja, a exceção PrecoInvalidoException (Você deverá criar essa exceção) deverá ser lançada e tratada e a unica mensagem que deverá ser exibida no console é: "O valor do produto [Aqui vc coloca o nome do produto] está inválido pois deve ser maior que zero !" ;
      - - Dica: Se precisar, revise o capitulo 12 da apostila;
- O retorno do calculo de frete deverá conter as seguintes informações:
  - produto;
  - uf;   
  - valor;

#### Como funcionará o calculo de frete ?

- Deve existir 2 tipos de calculo de frete, um baseado na uf do cliente e outro baseado no valor do produto.
- Ambos irão receber como parâmetro o produto e o cliente e devem retornar o Frete.

##### Calculo de Frete por uf
A regra para o calculo de frete por uf deverá ser a seguinte: Se a uf do cliente for SP, MG ou RJ, o valor do frete deverá ser 30% do valor do produto, caso contrário o valor do frete será 15% do valor do produto;

##### Calculo de Frete por valor do produto

A regra para o calculo de frete por valor do produto deverá ser a seguinte: Se o preco do produto for menor que 20,00 o valor do frete será de 2,00. Se o valor do produto for entre 20,00 e 100,00 o Frete deverá ser 8,00 e acima de R$ 100,00 o frete é gratis (0,00);


***Dica: Faça uso do Polimorfismo ! lembre-se que podemos alcança-lo com o uso de interfaces. Revise o capitulo 11 se vc precisar ...***


### O que será avaliado ?

Basicamente tudo que foi visto na apostila.

- Uso correto de variaveis;
- Uso correto de modificadores de acesso;
- Uso correto de metodos de instância e estáticos;
  - Dica se precisar: https://www.devmedia.com.br/trabalhando-com-metodos-em-java/25917
- Encapsulamento das classes;
  - Dica: https://www.youtube.com/watch?v=OTO1MBMmH9g;
- Coesão e Acoplamento;
  - Dica: https://www.devmedia.com.br/entendendo-coesao-e-acoplamento/18538
- Uso da orientação a objeto (Classe, Método, Herança, Polimorfismo, Encapsulamento e etc...);
- Se todas as regras e funcionalidades descritas nesse arquivo estão de acordo;

### Plus

Precisamos testar a nossa aplicação e para isso, a ideia é utilizar o conceito de testes automatizados !

Não sabe o que é isso ?

Dê uma pesquisada na Internet !

Pesquise sobre os tipos de teste e principalmente sobre o conceito de testes unitários utilizando Junit5 e Mockito, ambos são libs de teste do Java que são muito utilizadas no mercado. 

Objetivos:

- Implementar as dependências do Junit5 e do Mockito e criar testes unitários para os 2 tipos de calculo de frete e todas as validações que temos na aplicação (cep, valor do produto e etc...).
  - Como configurar o Junit5 em um projeto Maven: https://www.devmedia.com.br/teste-unitario-com-junit/41235
  - Não esqueça de usar a versão mais recente do Junit5 ! 
  - Pesquise sobre testes unitários e Mocks;
  - Configure a dependência do Mockito;

