# Instruções
- Faça uma cópia deste arquivo .md para um repositório próprio
- Resolva as 8 questões objetivas assinalando a alternativa correta e **justificando sua resposta.**
- Resolva as 2 questões dissertativas escrevendo no próprio arquivo .md
- Lembre-se de utilizar as estruturas de código como ``esta aqui com ` `` ou
```javascript
//esta aqui com ```
let a = "olá"
let b = 10
print(a)
```
- Resolva as questões com uso do Visual Studio Code ou ambiente similar.
- Teste seus códigos antes de trazer a resposta para cá.
- Cuidado com o uso de ChatGPT (e similares), pois entregar algo só para ganhar nota não fará você aprender. Não seja dependente da máquina!
- Ao final, publique seu arquivo lista_01.md com as respostas em seu repositório, e envie o link pela Adalove. 

# Questões objetivas
**1) Considerando a execução do código abaixo, indique a alternativa correta e justifique sua resposta.**
```javascript
console.log(x);
var x = 5;
console.log(y);
let y = 10;
```
a) A saída será undefined seguido de erro 

b) A saída será 5 seguido de 10

**✅ c) A saída será undefined seguido de undefined**

d) A saída será erro em ambas as linhas que utilizam console.log

**R: A letra c está correta pois a varivel foi definida depois do comando ser executado, entao a variavel (x) e a variavel (y) ainda nao foram definidas por isso undefined.**


**2) O seguinte código JavaScript tem um erro que impede sua execução correta. Analise e indique a opção que melhor corrige o problema. Justifique sua resposta.**

```javascript
function soma(a, b) {
    if (a || b === 0) {
        return "Erro: número inválido";
    }
    return a + b;
}
console.log(soma(2, 0));
```

**a) ✅Substituir if (a || b === 0) por if (a === 0 || b === 0)**

b) Substituir if (a || b === 0) por if (a === 0 && b === 0)

c) Substituir if (a || b === 0) por if (a && b === 0)

d) Remover completamente a verificação if (a || b === 0)

**R: A alternativa (a) está correta porque atribuir a igualdade somente a b faz com que a igualdade === seja verificada primeiramente, fazendo com que qualquer valor aplicado a b seja atribuido como falso.**

______
**3) Ao executar esse código, qual será a saída no console? Indique a alternativa correta e justifique sua resposta.**
```javascript
function calcularPreco(tipo) {
    let preco;

    switch(tipo) {
        case "eletrônico":
            preco = 1000;
        case "vestuário":
            preco = 200;
            break;
        case "alimento":
            preco = 50;
            break;
        default:
            preco = 0;
    }

    return preco;
}

console.log(calcularPreco("eletrônico"));
```

a) O código imprime 1000.

**b)✅ O código imprime 200.**

c) O código imprime 50.

d) O código gera um erro.

**R: O código imprime 200 pois não tem um "break;" depois do case eletrônico.**
______
**4) Ao executar esse código, qual será a saída no console? Indique a alternativa correta e justifique sua resposta.**
```javascript
let numeros = [1, 2, 3, 4, 5];

let resultado = numeros.map(x => x * 2).filter(x => x > 5).reduce((a, b) => a + b, 0);

console.log(resultado);
```
a) 0

b) 6

c) 18

**d)✅24**

**R:Primeiro o código multiplica por 2 cada número da array, após isso o .filter filtra os números maiores que 5, depois disso o código soma os números filtrados.**
______
**5) Qual será o conteúdo do array lista após a execução do código? Indique a alternativa correta e justifique sua resposta.**

```javascript
let lista = ["banana", "maçã", "uva", "laranja"];
lista.splice(1, 2, "abacaxi", "manga"); // splice = emendar, entao o .splice diz para emendar "abacaxi" e "manga" no lugar da "maçã" e da "uva"(posição 1 e emende no lugar dos 2, onde esse 2 representa a maçã e a "uva") na lista
console.log(lista);
```

a) ["banana", "maçã", "uva", "abacaxi", "manga", "laranja"]

b) ["banana", "abacaxi", "manga"]

c) ["banana", "abacaxi", "manga", "laranja"]

**d) ✅["banana", "maçã", "uva", "abacaxi", "manga"]**

**R: splice = emendar, entao o .splice diz para emendar "abacaxi" e "manga" no lugar da "maçã" e da "uva"(posição 1 e emende no lugar dos 2, onde esse 2 representa a maçã e a "uva") na lista**
______
**6) Abaixo há duas afirmações sobre herança em JavaScript. Indique a alternativa correta e justifique sua resposta**

I. A herança é utilizada para compartilhar métodos e propriedades entre classes em JavaScript, permitindo que uma classe herde os métodos de outra sem a necessidade de repetir código.  
II. Em JavaScript, a herança é implementada através da palavra-chave `extends`.


a) As duas afirmações são verdadeiras, e a segunda justifica a primeira.

**b)✅As duas afirmações são verdadeiras, mas a segunda não justifica a primeira.**

c) A primeira afirmação é verdadeira, e a segunda é falsa.

d) A primeira afirmação é falsa, e a segunda é verdadeira.

**R: Não entendi muito bem, pois a afirmativa 2 está parcialmente certa, uma vez que para realmente herdar uma característica de uma outra classe precisa usar o "super()" e selecionar as características que deseja. Então a afirmativa 1 está correta, e a b está parcialmente correta.**
______
**7) Dado o seguinte código. Indique a alternativa correta e justifique sua resposta.**

```javascript
class Pessoa {
  constructor(nome, idade) {
    this.nome = nome;
    this.idade = idade;
  }

  apresentar() {
    console.log(`Olá, meu nome é ${this.nome} e tenho ${this.idade} anos.`);
  }
}

class Funcionario extends Pessoa {
  constructor(nome, idade, salario) {
    super(nome, idade);
    this.salario = salario;
  }

  apresentar() {
    super.apresentar();
    console.log(`Meu salário é R$ ${this.salario}.`);
  }
}

let pessoa1 = new Funcionario("caio", 25, 6000);
pessoa1.apresentar();
 resultado:
'Olá, meu nome é caio e tenho 25 anos.'
'Meu salário é R$ 6000.'

```


I) A classe Funcionario herda de Pessoa e pode acessar os atributos nome e idade diretamente. ✅
II) O método `apresentar()` da classe Funcionario sobrepõe o método `apresentar()` da classe Pessoa, mas chama o método da classe pai usando `super`.✅
III) O código não funciona corretamente, pois Funcionario não pode herdar de Pessoa como uma classe, já que o JavaScript não suporta herança de classes.❌

Quais das seguintes afirmações são verdadeiras sobre o código acima?

**a) I e II são verdadeiras. ✅**

b) I, II e III são verdadeiras.

c) Apenas II é verdadeira.

d) Apenas I é verdadeira.

**R: let pessoa1 = new Funcionario("caio", 25, 6000);
pessoa1.apresentar();
 resultado:
'Olá, meu nome é caio e tenho 25 anos.'
'Meu salário é R$ 6000.'**
______

**8) Analise as afirmações a seguir. Indique a alternativa correta e justifique sua resposta.**

**Asserção:** O conceito de polimorfismo em Programação Orientada a Objetos permite que objetos de diferentes tipos respondam à mesma mensagem de maneiras diferentes.  
**Razão:** Em JavaScript, o polimorfismo pode ser implementado utilizando o método de sobrecarga de métodos em uma classe.

a) A asserção é falsa e a razão é verdadeira.

**b) ✅A asserção é verdadeira e a razão é falsa.**

c) A asserção é verdadeira e a razão é verdadeira, mas a razão não explica a asserção.

d) A asserção é verdadeira e a razão é verdadeira, e a razão explica a asserção.

**R: Sei que a **razão** está errada pois o método de sobrecarga não está correto, mas sim o de sobrescrita**
______

# Questões dissertativas
9) O seguinte código deve retornar a soma do dobro dos números de um array, mas contém erros. Identifique os problema e corrija o código para que funcione corretamente. Adicione comentários ao código explicado sua solução para cada problema.

```javascript
function somaArray(numeros) {

    for (i = 0; i < numeros.size; i++) {
        soma = 2*numeros[i];
    }
    return soma;
}
console.log(somaArray([1, 2, 3, 4]));
```
------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
**RESPOSTA:**

```javascript
function somaArray(numeros) {
  let somaTotal = 0; // Criando uma variável para armazenar o resultado

  for (let i = 0; i < numeros.length; i++) { // .size nao funciona e sim .length
    somaTotal += 2 * numeros[i]; // Acumulando a soma
  }

  return somaTotal; // Retornando a soma total
}

let numeros = [1, 2, 3, 4]; // criando a array números
console.log(somaArray(numeros)); 
```

______
10) Crie um exemplo prático no qual você tenha duas classes:

- Uma classe `Produto` com atributos `nome` e `preco`, e um método `calcularDesconto()` que aplica um desconto fixo de 10% no preço do produto.
- Uma classe `Livro` que herda de `Produto` e modifica o método `calcularDesconto()`, aplicando um desconto de 20% no preço dos livros.

Explique como funciona a herança nesse contexto e como você implementaria a modificação do método na classe `Livro`.


```javascript
class Produto {
  constructor(nome, preco){
    this.nome = nome;
    this.preco = preco;
  }
  
  calcularDesconto(){
    
    let desconto = this.preco * 0.1;
    let precoFinal = this.preco - desconto;
    console.log(`o produto ${this.nome} custa ${this.preco}, porem você possui um desconto de 10% saindo por ${precoFinal}`)
  }
}


class Livro extends Produto{
  constructor(nome,preco){
    super(nome,preco)
  }
  calcularDesconto(){
    let desconto = this.preco * 0.2;
    let precoFinal = this.preco - desconto;
    console.log(`o Livro ${this.nome} custa ${this.preco}, porem você possui um desconto de 20% saindo por ${precoFinal}`)
  }
}

item1 = new Livro("relativity", 99)
item1.calcularDesconto();
```


**R: Nesse exemplo a herença funciona ao importar da classe pai "Produto" as variaveis nome e preco, e no meu caso, copiei e colei o metódo calcularDesconto() e troquei as partes necessárias.**






