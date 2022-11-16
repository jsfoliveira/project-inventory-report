# 	:woman_technologist: Project Inventory Reports

Esse projeto contém uma série de informações sobre o que eu aprendi aqui na Trybe ao longo  do curso de desenvolvimento web da Trybe. <br>
Neste projeto foi possível utilizar a Programação Orientada a Objetos! Foi implementado um **gerador de relatórios** que recebe como entrada arquivos com dados de um estoque e gera, como saída, um relatório acerca destes dados.

  Esses dados de estoque poderão ser obtidos de diversas fontes:

  - Através da importação de um arquivo `CSV`;

  - Através da importação de um arquivo `JSON`;

  - Através da importação de um arquivo `XML`.

  Além disso, o relatório final possuirá duas versões: **simples** e **completa**.

## :rocket:Começando
Esse projeto foi proposto pelo curso de desenvolvimento web da Trybe.
### Desenvolvimento
Esse projeto foi desenvolvido no bloco de ciências da computação e foi possível treinar a linguagem Python, os padrões: Iterator, Adapter, Strategy, Decorator, Observer, Factory.
### Commits
Os commits foram feitos de acordo com os requisitos finalizados.
### Branch
Todo o projeto foi feita na branch juliana-oliveira-inventory-report.
### Instalação
Antes de rodar a aplicação, é preciso criar e instalar o ambiente virtual, através dos comandos:<br>
- `python3 -m venv .venv && source .venv/bin/activate` <br>
- `python3 -m pip install -r dev-requirements.txt`
### Testes
```bash
  $ python3 -m pytest
  ```

  O arquivo `pyproject.toml` já configura corretamente o pytest. Entretanto, caso você tenha problemas com isso e queira explicitamente uma saída completa, o comando é:

  ```bash
  python3 -m pytest -s -vv
  ```

  Caso precise executar apenas um arquivo de testes basta executar o comando:

  ```bash
  python3 -m pytest tests/nomedoarquivo.py
  ```

  Caso precise executar apenas uma função de testes basta executar o comando:

  ```bash
  python3 -m pytest -k nome_da_func_de_tests
  ```

  Se desejar que os testes parem de ser executados quando acontecer o primeiro erro, use o parâmetro `-x`

  ```bash
  python3 -m pytest -x tests/test_simple_report.py
  ```

  Caso queria executar um teste especifico de um arquivo basta executar o comando:

  ```bash
  python3 -m pytest -x tests/nomedoarquivo.py::test_nome_do_teste
  ```
### Autores
Esse foi um projeto individual.
### Ferramentas usadas
Foi usado Visual Studio Code, além do Trello que auxiliou na organização das tarefas.
### Estrutura do projeto
<details>
  <summary><strong>🧱 Estrutura do Projeto</strong></summary><br />
  Este repositório já contém um template com a estrutura de diretórios e arquivos, tanto de código quanto de teste criados. Veja abaixo:

  ```
  Legenda:
  🔸Arquivos que não podem ser alterados
  🔹Arquivos a serem alterados para realizar os requisitos.
  .
  ├── inventory_report
  │   ├── data
  │   │   ├── 🔸inventory.csv
  │   │   ├── 🔸inventory.json
  │   │   └── 🔸inventory.xml
  │   ├── importer
  │   │   ├── 🔹csv_importer.py
  │   │   ├── 🔹importer.py
  │   │   ├── 🔹json_importer.py
  │   │   └── 🔹xml_importer.py
  │   ├── inventory
  │   │   ├── 🔹inventory_iterator.py
  │   │   ├── 🔹inventory_refactor.py
  │   │   └── 🔹inventory.py
  │   │   └── 🔸product.py
  │   ├── reports
  │   │   ├── 🔸colored_report.py
  │   │   ├── 🔹complete_report.py
  │   │   └── 🔹simple_report.py
  │   └── 🔹main.py
  └── tests
  │   ├── factories
  │   │   ├── 🔸__init__.py
  │   │   └── 🔸product_factory.py
  │   ├── product
  │   │   ├── 🔸__init__.py
  │   │   ├── 🔸conftest.py
  │   │   ├── 🔸mocks.py
  │   │   └── 🔹test_product.py
  │   ├── product_report
  │   │   ├── 🔸__init__.py
  │   │   ├── 🔸conftest.py
  │   │   ├── 🔸mocks.py
  │   │   └── 🔹test_product_report.py
  │   ├── report_decorator
  │   │   ├── 🔸__init__.py
  │   │   ├── 🔸conftest.py
  │   │   ├── 🔸mocks.py
  │   │   └── 🔹test_report_decorator.py
  │   ├── 🔸__init__.py
  │   ├── 🔸marker.py
  │   ├── 🔸test_complete_report.py
  │   ├── 🔸test_importer.py
  │   ├── 🔸test_inventory_refactor.py
  │   ├── 🔸test_inventory.py
  │   ├── 🔸test_main.py
  │   └── 🔸test_simple_report.py
  ├── 🔹dev-requirements.txt
  ├── 🔸docker-compose.yml
  ├── 🔸Dockerfile
  ├── 🔸pyproject.toml
  ├── 🔸README.md
  ├── 🔸requirements.txt
  ├── 🔸setup.cfg
  ├── 🔸setup.py
  └── 🔸trybe.yml
  ```

  Apesar do projeto já possuir uma **estrutura base**, você perceberá que possui arquivos vazios, ou seja, neles você quem deve implementar as classes. Novos arquivos e funções podem ser criados conforme a necessidade da sua implementação, porém não remova arquivos já existentes.

</details>

### Informações de arquivos
<details>
  <summary><strong>🗃️ Arquivos com os dados de entrada</strong></summary><br />
  Três formatos de importação estão disponíveis no diretório <code>data</code> dentro do diretório <code>inventory_report</code>. Confira o exemplo de formato eles:
  
  <strong>Arquivos CSV</strong>
  Os arquivos **CSV** são separados por vírgula, como no exemplo abaixo:

```CSV
id,nome_do_produto,nome_da_empresa,data_de_fabricacao,data_de_validade,numero_de_serie,instrucoes_de_armazenamento
1,cadeira,Target Corporation,2021-02-18,2025-09-17,CR25,empilhadas
2,mesa,"Galena Madeira, Inc.",2022-12-06,2026-12-25,FR29,desmontadas
3,abajur,Keen Iluminação,2019-12-22,2025-11-07,CZ09,em caixas
```

<strong>Arquivos JSON</strong>
Os arquivos JSON seguem o seguinte modelo:

```json
[
  {
    "id":1,
    "nome_do_produto":"Borracha",
    "nome_da_empresa":"Papelaria Solar",
    "data_de_fabricacao":"2021-07-04",
    "data_de_validade":"2029-02-09",
    "numero_de_serie":"FR48",
    "instrucoes_de_armazenamento":"Ao abrigo de luz solar"
  }
]
```

<strong>Arquivos XML</strong>
Os arquivos **XML** seguem o seguinte modelo:

```xml
<?xml version='1.0' encoding='UTF-8'?>
<dataset>
  <record>
    <id>1</id>
    <nome_do_produto>Microfone</nome_do_produto>
    <nome_da_empresa>Tecno Uau LTDA</nome_da_empresa>
    <data_de_fabricacao>2021-10-27</data_de_fabricacao>
    <data_de_validade>2032-08-31</data_de_validade>
    <numero_de_serie>MT08</numero_de_serie>
    <instrucoes_de_armazenamento>Longe de fonte de calor</instrucoes_de_armazenamento>
  </record>
</dataset>
```
</details>

<details>
  <summary><strong>🤝 Depois de terminar o desenvolvimento (opcional)</strong></summary><br />

  Para sinalizar que o seu projeto está pronto para o _"Code Review"_, faça o seguinte:

  - Vá até a página **DO SEU** _Pull Request_, adicione a label de _"code-review"_ e marque seus colegas:

    - No menu à direita, clique no _link_ **"Labels"** e escolha a _label_ **code-review**;

    - No menu à direita, clique no _link_ **"Assignees"** e escolha **o seu usuário**;

    - No menu à direita, clique no _link_ **"Reviewers"** e digite `students`, selecione o time `tryber/students-sd-019-a`.

  Caso tenha alguma dúvida, [aqui tem um video explicativo](https://vimeo.com/362189205).

</details>

<details>
  <summary><strong>🕵🏿 Revisando um pull request</strong></summary><br />

  Use o conteúdo sobre [Code Review](https://course.betrybe.com/real-life-engineer/code-review/) para te ajudar a revisar os _Pull Requests_.

</details>

## :footprints:Requisitos
### Metodologia usada
No trabalho do desenvolvimento de software a gente sempre tem prazos, muitas vezes os prazos são apertados.<br>
Por outro lado, eu não quero criar algo que não entendo perfeitamente, como também fazer códigos rápidos pode levar a erros que podem demorar muito pra corrigir.<br>
Por isso, usei e sempre uso o método Baby Steps, que é uma estratégia de abordar o desafio passo à passo, defensivamente.<br>
Baby steps é um termo em inglês que quer dizer passos de bebê. Refere-se a fazer as coisas, quaisquer que sejam, devagar, com calma, passo a passo.

#### :footprints:Requisito 1 - Testar o construtor/inicializador do objeto Produto
> **Crie o teste em:** tests/product/test_product.py

  <p align="center">
    <img src="/.images/construtor.png " alt="Imagem de construtor em Python"  width="600"/>
  </p>

Ao analisar o código do projeto, você encontrará a classe do objeto produto já implementada neste arquivo: `inventory_report/inventory/product.py`, a classe **Product**.

Para termos confiança em continuar as implementações, precisamos que você implemente o teste, que certifique que o método `__init__` da classe Product esta funcionando corretamente.

O nome deste teste deve ser `test_cria_produto`, ele deve verificar o correto preenchimento dos seguintes atributos:
  - id (int)
  - nome_da_empresa (string)
  - nome_do_produto (string)
  - data_de_fabricacao (string)
  - data_de_validade (string)
  - numero_de_serie (string)
  - instrucoes_de_armazenamento (string)

<details>
  <summary>
    <b>🤖 O que será verificado pelo avaliador</b>
  </summary>

  - **1** - Deve criar um novo produto com todos os atributos corretamente preenchidos.

</details>

<details>
  <summary>
    <b>📌Como seu teste é avaliado</b>
  </summary>
  O <strong>teste da Trybe</strong> irá avaliar se o <strong>seu teste</strong> está passando conforme seu objetivo, e confirmará se ele está falhando em alguns casos que deve falhar.
  Para estes testes que esperemos que falhe, o requisito será considerado atendindo quando a resposta do Pytest for <code>XFAIL(Expected Fail)</code>, ao invés de <code>PASS</code> ou <code>FAIL</code>.
</details>


#### :footprints:Requisito 2 - Testar o relatório individual do produto
> **Crie o teste em:** tests/product_report/test_product_report.py

Boa novidade, o primeiro relatório já implementamos neste arquivo `inventory_report/inventory/product.py`. Formulamos uma frase construída com as informações do produto, que será muito útil para etiquetarmos o estoque.

Para desenvolver este relatório, utilizamos o recurso `__repr__` do Python, que permite alterar a representatividade do objeto, para que sempre que usarmos um print nele, no lugar de endereço de memória, teremos uma String personalizada. 

**Dica:** A reimplementação do `__repr__` não faz o objeto retornar exatamente uma `string`, fazer um `cast` para `string`, pode te ajudar.

Exemplo da frase:
> O produto `farinha` fabricado em `01-05-2021` por `Farinini` com validade até `02-06-2023` precisa ser armazenado `ao abrigo de luz`.

Agora para mantermos uma boa cobertura de testes, precisamos que você implemente o teste.

O nome deste teste deve ser `test_relatorio_produto`, ele deve instanciar um objeto `Product` e verificar se acessá-lo a frase de retorno esta correta.

<details>
  <summary>
    <b>🤖 O que será verificado pelo avaliador</b>
  </summary>


  - **1** - Se seu código testa que o retorno padrão (`__repr__`) de um objeto `Product` deve ser um relatório sobre ele 
</details>
    
<details>
  <summary>
    <b>📌Como seu teste é avaliado</b>
  </summary>
  O <strong>teste da Trybe</strong> irá avaliar se o <strong>seu teste</strong> está passando conforme seu objetivo, e confirmará se ele está falhando em alguns casos que deve falhar.
  Para estes testes que esperemos que falhe, o requisito será considerado atendindo quando a resposta do Pytest for <code>XFAIL(Expected Fail)</code>, ao invés de <code>PASS</code> ou <code>FAIL</code>.
</details>


#### :footprints:Requisito 3 - Gerar a versão simplificada do relatório

> **Crie a classe em:** inventory_report/reports/simple_report.py

O relatório deve ser gerado através de um método estático ou de classe chamado `generate` escrito dentro da classe `SimpleReport`.

- Ao rodar os testes localmente, você terá um teste para cada validação de cada informação
- Deve ser possível executar o método `generate` sem instanciar um objeto de `SimpleReport`
- O método deve receber um parâmetro que representa uma `list` (estrutura de dados), onde cada posição contém um `dict`(estrutura de dados).

Exemplo de formato de entrada

```json
   [
     {
       "id": 1,
       "nome_do_produto": "CADEIRA",
       "nome_da_empresa": "Forces of Nature",
       "data_de_fabricacao": "2022-04-04",
       "data_de_validade": "2023-02-09",
       "numero_de_serie": "FR48",
       "instrucoes_de_armazenamento": "Conservar em local fresco"
     }
   ]
```

- O método deverá retornar uma `string` de saída com o seguinte formato:
   ```bash
   Data de fabricação mais antiga: YYYY-MM-DD
   Data de validade mais próxima: YYYY-MM-DD
   Empresa com mais produtos: NOME DA EMPRESA
   ```
- A data de validade mais próxima, somente considera itens que ainda não venceram.

**Dica:** O módulo [datetime](https://docs.python.org/3/library/datetime.html) pode te ajudar.

<details>
  <summary>
    <b>🤖 O que será verificado pelo avaliador</b>
  </summary>


  - **3.1** - O método generate da classe SimpleReport deve retornar todas informações do relatório simples. Informações necessárias:
    - a data de fabricação mais antiga
    - a validade mais próxima
    - a empresa com maior número de produtos

  - **3.2** - O método generate da classe SimpleReport deve retornar o formato correto do relatório simples

    📌 Atente-se a espaçamentos e quebras de linhas

</details>

#### :footprints:Requisito 4 - Gerar a versão completa do relatório

> **Crie em:** inventory_report/reports/complete_report.py

O relatório deve ser gerado através de um método `generate` para a classe `CompleteReport`.
Ele deverá receber dados numa lista contendo estruturas do tipo `dict` e deverá retornar uma string formatada como um relatório.

- A classe `CompleteReport` deve herdar da classe `SimpleReport` e sobrescrever o método `generate`, de modo a especializar seu comportamento.

- Deve ser possível executar o método `generate` sem instanciar um objeto de `CompleteReport`
  
- O método deve receber de parâmetro uma lista de dicionários no seguinte **formato**:

   ```json
   [
     {
       "id": 1,
       "nome_do_produto": "MESA",
       "nome_da_empresa": "Forces of Nature",
       "data_de_fabricacao": "2022-05-04",
       "data_de_validade": "2023-02-09",
       "numero_de_serie": "FR48",
       "instrucoes_de_armazenamento": "Conservar ao abrigo de luz"
     }
   ]
   ```

- O método deverá retornar uma saída com o seguinte formato:

```bash
Data de fabricação mais antiga: YYYY-MM-DD
Data de validade mais próxima: YYYY-MM-DD
Empresa com mais produtos: NOME DA EMPRESA
Produtos estocados por empresa:
- Physicians Total Care, Inc.: QUANTIDADE
- Newton Laboratories, Inc.: QUANTIDADE
- Forces of Nature: QUANTIDADE
```

<details>
  <summary>
    <b>🤖 O que será verificado pelo avaliador</b>
  </summary>


  - **2.1** - O método generate da classe CompleteReport deve retornar todas informações do relatório completo no formato correto. Informações necessárias:
    - a data de fabricação mais antiga
    - a validade mais próxima
    - a empresa com maior estoque
    - a quantidade de produtos por empresa, ordenado pela mesma ordem que as empresas aparecem na lista de entrada

</details>

#### :footprints:Requisito 5 - Gere os relatórios através de um arquivo CSV
> **Crie em:** inventory_report/inventory/inventory.py

A importação do arquivo CSV deve ser realizada através do método `import_data` que você deve criar em uma classe chamada `Inventory`.
    
O método deve ser estático ou de classe, ou seja, deve ser possível chamá-lo sem instanciar um objeto da classe.

O método receberá como primeiro parâmetro uma string como caminho para o arquivo `CSV` e como segundo parâmetro uma string que representa o tipo de relatório a ser gerado. Tipos:
 - `"simples"`
 - `"completo"`

De acordo com os parâmetros recebidos, deve recuperar os dados do arquivo e chamar o método de gerar relatório correspondente à entrada passada. Ou seja, o método da classe `Inventory` deve chamar o método `generate` da classe que vai gerar o relatório (`SimpleReport`, `CompleteReport`).

<details>
  <summary>
    <b>🤖 O que será verificado pelo avaliador</b>
  </summary>

  - **3** - Ao importar um arquivo CSV, deve retornar o relatórios simples ou o completo conforme solicitado.

</details>

#### :footprints:Requisito 6 - Gere os relatórios através de um arquivo JSON
> **Incremente em:** `inventory_report/inventory/inventory.py`. 

> 📌 Utilize o mesmo método do requisito anterior.

Altere o método `import_data` para que ele também seja capaz de carregar arquivos `JSON`.
    
Como no requisito anterior, o método ainda receberá como primeiro parâmetro uma string como caminho para o arquivo, e como segundo parâmetro uma string que representa o tipo de relatório a ser gerado. Tipos:
 - `"simples"`
 - `"completo"`

De acordo com os parâmetros recebidos, deve recuperar os dados do arquivo e chamar o método de gerar relatório correspondente à entrada passada. Ou seja, o método da classe `Inventory` deve chamar o método `generate` da classe que vai gerar o relatório (`SimpleReport`, `CompleteReport`).


<details>
  <summary>
    <b>🤖 O que será verificado pelo avaliador</b>
  </summary>


- **4** - Ao importar um arquivo JSON, deve retornar o relatórios simples ou o completo conforme solicitado.

</details>

#### :footprints:Requisito 7 - Gere os relatórios através de um arquivo XML
> **Incremente em:** `inventory_report/inventory/inventory.py`. 

> 📌 Utilize o mesmo método do requisito anterior.
    
Altere o método `import_data` para que ele também seja capaz de carregar arquivos `XML`.
    
Como no requisito anterior, o método ainda receberá como primeiro parâmetro uma string como caminho para o arquivo, e como segundo parâmetro uma string que representa o tipo de relatório a ser gerado. Tipos:
 - `"simples"`
 - `"completo"`

De acordo com os parâmetros recebidos, deve recuperar os dados do arquivo e chamar o método de gerar relatório correspondente à entrada passada. Ou seja, o método da classe `Inventory` deve chamar o método `generate` da classe que vai gerar o relatório (`SimpleReport`, `CompleteReport`).

*Dica: 👀 Dê uma olhada na biblioteca externa `xmltodict`*
<details>
  <summary>
    <b>🤖 O que será verificado pelo avaliador</b>
  </summary>
  
  - **5** - Ao importar um arquivo XML, deve retornar o relatórios simples ou o completo conforme solicitado.

</details>

#### :footprints:Requisito 8 - Organizar o código de importação com o padrão Strategy
> **Crie em:** inventory_report/importer/importer.py

Como pôde observar até aqui, o método `import_data` está com muitas responsabilidades, e, com o intuito de resolver isso, podemos dividir a sua complexidade para cada formato de arquivo.

O padrão de projeto `Strategy` nos ajuda a isolar cada estratégia em um objeto, e por meio de uma Interface podemos padronizar a assinatura dos métodos, garantindo que todas elas possuam o comportamento similar.

- Ao rodar os testes localmente, você terá um teste para cada validação de cada informação
- Crie uma classe abstrata `Importer` para ser a interface da estratégia
- A Interface será uma classe abstrata `Importer` terá três classes de estratégias herdeiras: `CsvImporter`, `JsonImporter` e `XmlImporter`.
- Crie as classes nos respectivos arquivos:
  > inventory_report/importer/csv_importer.py
  > inventory_report/importer/json_importer.py
  > inventory_report/importer/xml_importer.py

- A classe abstrata deve definir a assinatura do método `import_data` a ser implementado por cada classe herdeira. Esse método deve ser estático ou de classe, e deve receber como parâmetro o nome do arquivo a ser importado.

- O método `import_data` definido por cada classe herdeira deve lançar uma exceção do tipo `ValueError` caso a extensão do arquivo passado por parâmetro seja inválida. Por exemplo, quando se passa um caminho de um arquivo com extensão `.csv` para o `JsonImporter`. A mensagem de erro da exceção deve ser _"Arquivo inválido"_.

- O método deverá ler os dados do arquivo passado e retorná-los estruturados em uma lista de dicionários conforme exemplo abaixo:

   ```json
   [
     {
       "id": 1,
       "nome_do_produto": "Cafe",
       "nome_da_empresa": "Cafes Nature",
       "data_de_fabricacao": "2020-07-04",
       "data_de_validade": "2023-02-09",
       "numero_de_serie": "FR48",
       "instrucoes_de_armazenamento": "instrucao"
     }
   ]
   ```

<details>
  <summary>
    <b>🤖 O que será verificado pelo avaliador</b>
  </summary>

  - **8** - As classes estratégicas `CsvImporter`, `JsonImporter` e `CsvImporter` devem cada uma:
      - herdar a classe `importer`
      - importar e retornar os dados para uma lista (`list`) de dicionários (`dict`)
      - validar se ao enviar um arquivo com extensão incorreta deve gerar um erro

</details>

#### :footprints:Requisito 9 - Testar a geração de uma versão do relatório em cores
> **Crie o teste em:** tests/report_decorator/test_report_decorator.py

Uma versão deste relatório será exibida em letreiros em Led, estes letreiros são coloridos, para isso, já implementamos o método responsável por retornar este relatório em cores.

> Implementamos em : inventory_report/reports/colored_report.py

Em vez de criarmos uma classe que herda os relatórios originais, utilizamos o padrão `Decorator` para receber o tipo do relatório por composição (`SimpleReport` ou `CompleteReport`) e, assim, colorir o retorno do método `generate`, que recebe uma lista de produtos e retorna o relatório já colorido.

Para termos confiança que as cores sairão corretamente, precisamos que você implemente o teste, que certifique que o método **generate**  de **ColoredReport** funciona corretamente.

Para que o Python consiga colorir as strings, é preciso que a string contenha o início do código da cor, e o reset da cor.

📌 Execute este print teste em um terminal interativo `python3 -i`. O resultado das cores podem não ser exatos, por isso, atente-se aos códigos deste exemplo:

```python
print("\033[36mAzul\033[0m \033[32mVerde\033[0m \033[31mVermelho\033[0m")
```

  <p align="center">
    <img src="/.images/print_colorido.png" alt="Logo Flask"/>
  </p>

O nome deste teste deve ser `test_decorar_relatorio`, ele deve verificar se o relatório está devidamente colorido. Representamos abaixo como deve ser a disposição das cores:

<span style="color: green;">🟩Data de fabricação mais antiga:🟩</span> <span style="color: blue;">🟦10-05-2022🟦</span>

<span style="color: green;">🟩Data de validade mais próxima:🟩</span> <span style="color: blue;">🟦14-06-2021🟦</span>

<span style="color: green;">🟩Empresa com mais produtos:🟩</span> <span style="color: red;">🟥Farinini🟥</span>

  
<details>
  <summary>
    <b>🤖 O que será verificado pelo avaliador</b>
  </summary>

  - **9** - Deve retornar o relatório devidamente colorido.
    - **verde:**
        - "Data de fabricação mais antiga:"
        - "Data de validade mais próxima:"
        - "Empresa com mais produtos:"
    -  **azul:** As datas
    - **vermelho:** Nome da empresa com mais produtos
</details>

<details>
  <summary>
    <b>📌Como seu teste é avaliado</b>
  </summary>
  O <strong>teste da Trybe</strong> irá avaliar se o <strong>seu teste</strong> está passando conforme seu objetivo, e confirmará se ele está falhando em alguns casos que deve falhar.
  Para estes testes que esperemos que falhe, o requisito será considerado atendindo quando a resposta do Pytest for <code>XFAIL(Expected Fail)</code>, ao invés de <code>PASS</code> ou <code>FAIL</code>.
</details>
