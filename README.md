# DIO - Trilha .NET - Testes Unitários com C#
www.dio.me

## Desafio de projeto
Para este desafio, você precisará usar seus conhecimentos adquiridos no módulo de Testes Unitários com C#, da trilha .NET da DIO.

<div align="center">
  
  ![.Net](https://img.shields.io/badge/.NET-5C2D91?style=for-the-badge&logo=.net&logoColor=white)  ![C#](https://img.shields.io/badge/c%23-%23239120.svg?style=for-the-badge&logo=c-sharp&logoColor=white)
  
</div>

## Índice
1. [Titúlo](#dio---trilha-net---testes-unitários-com-c)
2. [Índice](#índice)
3. [Contexto](#contexto) 
4. [Premissas](#premissas)
5. [Projeto Console, suas classes e métodos](#projeto-console-suas-classes-e-métodos)
6. [Projeto do tipo teste, suas classes e métodos](#projeto-do-tipo-teste-suas-classes-e-métodos)
7. [Estrutura do projeto](#estrutura-do-projeto)
8. [Solução](#solução)
9. [Resultado Final](#resultado-final)
10. [Autor](#autor)


## Contexto
Você está trabalhando em um sistema, e seus gestores relataram que frequentemente há problemas no software: bugs, funcionalidades que estavam funcionando de repente não funcionam mais, problemas de validações, entre outros. Os clientes já começam a duvidar da qualidade do código.

Feito isso, você sugeriu a implementação de testes unitários: escrever testes cobrindo as partes mais críticas do sistema, com cenários positivos e negativos, a fim de ter uma rastreabilidade e controle do código, melhorando assim a qualidade desse sistema.

Os gestores aceitaram a sua ideia, e com isso, você precisa implementar testes unitários no sistema.

## Premissas
O sistema hoje possui dois projetos: um do tipo console, e um do tipo testes com **xUnit**. O projeto do tipo console possui duas classes em que são realizadas as lógicas principais: **ValidacoesLista** e **ValidacoesString**. Essas classes contém métodos em comum que são usados para realizar diversas validações em determinados cenários.

O projeto de testes possui as classes de teste **ValidacoesListaTests** e **ValidacoesStringTests**, assim como seus métodos para validar o projeto do tipo console, porém estão incompletos. 

O seu objetivo é implementar os métodos de testes contidos no projeto.

## Projeto Console, suas classes e métodos

Essas são as classes do projeto console, onde fica a principal lógica do sistema.

**Classe ValidaçõesLista**

Classe responsável por realizar diversas validações envolvendo listas.

| Classe          | Método                       | Objetivo                                                                                                                |
|---------------- |------------------------------|-------------------------------------------------------------------------------------------------------------------------|
| ValidacoesLista | RemoverNumerosNegativos      | Recebe uma lista de números inteiros e retorna uma nova lista, apenas com os números positivos                          |
| ValidacoesLista | ListaContemDeterminadoNumero | Recebe uma lista de números inteiros e verifica se um determinado número está presente dentro dessa lista               |
| ValidacoesLista | MultiplicarNumerosLista      | Recebe uma lista de números inteiros e retorna uma nova lista, com seus valores múltiplicados por um determinado número |
| ValidacoesLista | RetornarMaiorNumeroLista     | Recebe uma lista de números inteiros e retorna o maior número entre eles                                                |
| ValidacoesLista | RetornarMenorNumeroLista     | Recebe uma lista de números inteiros e retorna o menor número entre eles                                                |

**Classe ValidacoesString**

Classe responsável por realizar diversas validações envolvendo strings.

| Classe           | Método                       | Objetivo                                                                                                                
|------------------|------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ValidacoesString | RetornarQuantidadeCaracteres | Recebe um texto qualquer e retorna a quantidade de caracteres presentes no texto                                                                           |
| ValidacoesString | ContemCaractere              | Recebe um texto qualquer e um texto a ser procurado, retorna verdadeiro ou falso se um determinado trecho procurado está presente no texto                 |
| ValidacoesString | TextoTerminaCom              | Recebe um texto qualquer e um trecho a ser procurado, retorna verdadeiro ou falso se um determinado trecho procurado está presente no final do texto apenas |

## Projeto do tipo teste, suas classes e métodos

**Classe ValidacoesListaTests**

Classe responsável por realizar os testes da classe ValidacoesLista.

| Classe               | Método de teste                               | Resultado esperado do teste
|----------------------|-----------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------|
| ValidacoesListaTests | DeveRemoverNumerosNegativosDeUmaLista         | Ao passar uma lista com diversos números, incluindo positivos e negativos, deve ser retornado uma nova lista apenas com números positivos  |
| ValidacoesListaTests | DeveConterONumero9NaLista                     | Ao passar uma lista com diversos números, incluindo o número 9, deve retornar verdadeiro, pois encontrou o 9 na lista                      |
| ValidacoesListaTests | NaoDeveConterONumero10NaLista                 | Ao passar uma lista com diversos números, mas sem o número 10, deve retornar falso, pois não encontrou o 10 na lista                       |
| ValidacoesListaTests | DeveMultiplicarOsElementosDaListaPor2         | Ao passar uma lista de inteiros, deve retornar uma nova lista, com todos os elementos da lista multiplicados por 2                         |
| ValidacoesListaTests | DeveRetornar9ComoMaiorNumeroDaLista           | Ao passar uma lista de números inteiros, sendo o maior deles 9, deve retornar o 9 como maior elemento dentro dessa lista                   |
| ValidacoesListaTests | DeveRetornarOitoNegativoComoMenorNumeroDaList | Ao passar uma lista de números inteiros, sendo o menor deles -8, deve retornar o -8 como menor elemento dentro dessa lista                 |

**Classe ValidacoesStringTests**

Classe responsável por realizar os testes da classe ValidacoesString.

| Classe                | Método de teste                                  | Resultado esperado do teste
|---------------------- |--------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ValidacoesStringTests | DeveRetornar6QuantidadeCaracteresDaPalavraMatrix | Ao passar um texto escrito a palavra "Matrix", deve retornar o número 6, representando 6 caracteres presentes na palavra                                                                         |
| ValidacoesStringTests | DeveContemAPalavraQualquerNoTexto                | Ao passar um texto escrito "Esse é um texto qualquer" e procurar pela palavra "qualquer", deve retornar verdadeiro pois a palavra existe no texto                                                |
| ValidacoesStringTests | NaoDeveConterAPalavraTesteNoTexto                | Ao passar um texto escrito "Esse é um texto qualquer" e procurar pela palavra "teste", deve retornar falso pois a palavra não existe no texto                                                    |
| ValidacoesStringTests | TextoDeveTerminarComAPalavraProcurado            | Ao passar um texto escrito "Começo, meio e fim do texto procurado" e procurar pela palavra "procurado", deve retornar verdadeiro pois a palavra existe no texto e está inclusa no final do texto |

## Estrutura do projeto

O projeto está estruturado da seguinte maneira:

![Métodos Swagger](Imagens/projeto.png)


## Solução
O código de testes está pela metade, e você deverá dar continuidade implementando os testes descritos acima, para que no final, tenhamos um programa de testes funcional. Procure pela palavra comentada "TODO" no código, em seguida, implemente conforme as regras acima.

## Resultado Final
<div align="center">
  
**Status do desafio:**
<br>✅**Finalizado**✅<br>
A tabela abaixo mostra quais foram as alterações feitas em cada classe, caso queira ver o código, basta clicar no nome da classe que deseja ver.
<br><br>


| Classe | Mudanças |
| ------ | -------- |
| [ValidacoesListaTests](https://github.com/thiagosilvaantenor/Desafio-DIO-dot-net-testes-unitarios/blob/main/TestesUnitarios.Desafio.Tests/ValidacoesListaTests.cs)  |No teste: `NaoDeveConterONumero10NaLista`, adicionado o "Act": uma variavel que recebe o retorno do método que será testado, usando a lista e o número que será procurado como parametros `(linha 47)` e no "Assert" utilizei um `Assert.False()` para verificar se o resultado será "False" `(linha 50)`;<br>Adicionado o `[Fact]` antes do teste: `DeveMultiplicarOsElementosDaListaPor2` , para indicar que ele é um teste `(linha 54)`, e novamente uma variavel que recebe o retorno do método testado, usando da lista criada no "Arrange" e outra variavel com resultado esperado `(linha 60 e 61)` , as duas vão ser comparadas com `Assert.Equal` verificando se seus valores são iguais `(linha 67)`; Utilizei a mesma estratégia para o teste: `DeveRetornar9ComoMaiorNumeroDaLista` `(linhas 79, 80 e 84)`;<br>No teste `DeveRetornarOitoNegativoComoMenorNumeroDaLista` utilizei uma variavel com o resultado esperado para realizar a comparação no `Assert.Equal` `(linhas 97 e 101)`| 
|[ValidacoesStringTests](https://github.com/thiagosilvaantenor/Desafio-DIO-dot-net-testes-unitarios/blob/main/TestesUnitarios.Desafio.Tests/ValidacoesStringTests.cs) |No teste: `DeveRetornar6QuantidadeCaracteresDaPalavraMatrix` corrigi a variavel texto `(linha 15)` para estar de acordo com o nome do teste;<br> Já no teste: `DeveContemAPalavraQualquerNoTexto` coloquei a chamada do método correto, `ContemCaractere()` `(linha 34)`, e utilizei da variavel resultado como parametro para o assert, `Assert.Equal(resultado)` `(linha 54)`;<br>Adicionado a notação `[Fact]` para sinalizar que abaixo vem um teste `(linha 58)`, alterado o valor da variavel textoProcurado `var textoProcurado = "procurado"` `(linha 65)`.|
 
</div>

## Autor
<div align="center">
<a href="https://www.linkedin.com/in/thiago-antenor/">
<img style="border-radius: 50%;" src="https://avatars.githubusercontent.com/u/99970279?v=4" width="100px;" alt="foto do autor"/>
 <br />
 <sub><b>Thiago Silva Antenor</b></sub></a> <a href="https://www.linkedin.com/in/thiago-antenor/" title="Linkedin"> 🧑🏾‍💻</a>


Feito por Thiago Silva Antenor 👨🏾‍💻 Entre em contato!

[![Linkedin Badge](https://img.shields.io/badge/-Thiago-blue?style=flat-square&logo=Linkedin&logoColor=white&link=https://www.linkedin.com/in/thiago-antenor/)](https://www.linkedin.com/in/thiago-antenor/) 
[![Gmail Badge](https://img.shields.io/badge/-thiagoantenor31@gmail.com-c14438?style=flat-square&logo=Gmail&logoColor=white&link=mailto:thiagoantenor31.com)](mailto:thiagoantenor31.com)
</div>
