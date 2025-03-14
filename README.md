# ponderada-semana06

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

c) A saída será undefined seguido de undefined

d) A saída será erro em ambas as linhas que utilizam console.log

alternativa a, porque a variável x é preparada com var antes de ser definida, então aparece como undefined no primeiro console.log, enquanto a variável y é declarada com let, não podendo ser usada antes da declaração, causando um erro.  

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

a) Substituir if (a || b === 0) por if (a === 0 || b === 0)

b) Substituir if (a || b === 0) por if (a === 0 && b === 0)

c) Substituir if (a || b === 0) por if (a && b === 0)

d) Remover completamente a verificação if (a || b === 0)

Alternativa a é a correta, pois deixa claro que o valor de zero é tanto para a quanto para b. Da forma que foi escrita da a entender que a pode ser qualquer valor, o que poderia trazer problemas na hora do erro ser retornado. Com o ajuste, garante que o erro só será retornado se a ou b for igual a zero 

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

b) O código imprime 200.

c) O código imprime 50.

d) O código gera um erro.

A alternativa certa é a b, uma vez que executando (calcularPreco("eletrônico")), abre o case eletrônico, mas só é interrompida com o break após o case vestuário, atribuindo o valor de 200.

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

d) 24

A saída no console será 24, alternativa d,  porque o map multiplica todos os valores por 2, transformando então em [2, 4, 6, 8, 10]. Logo em seguida, o filtro faz com que selecione apenas numeros maiores do que cinco, reduzindo a seleção de números para [6, 8, 10]. Por fim, o reduce soma todos os valores do aray, dando o resultado 24. 
______
**5) Qual será o conteúdo do array lista após a execução do código? Indique a alternativa correta e justifique sua resposta.**

```javascript
let lista = ["banana", "maçã", "uva", "laranja"];
lista.splice(1, 2, "abacaxi", "manga");
console.log(lista);
```

a) ["banana", "maçã", "uva", "abacaxi", "manga", "laranja"]

b) ["banana", "abacaxi", "manga"]

c) ["banana", "abacaxi", "manga", "laranja"]

d) ["banana", "maçã", "uva", "abacaxi", "manga"]

entao leia a minha justificativa, a alternativa é a c pois, no js, a contagem dos elementos de uma array começa a partir de 0, sendo assim, os elementos 1 e 2, como indicados, se referem a maça e uva. Dessa forma, a splice 'corta' os dois elementos, ficando então ["banana", "abacaxi", "manga", "laranja"] 

**6) Abaixo há duas afirmações sobre herança em JavaScript. Indique a alternativa correta e justifique sua resposta**

I. A herança é utilizada para compartilhar métodos e propriedades entre classes em JavaScript, permitindo que uma classe herde os métodos de outra sem a necessidade de repetir código.  
II. Em JavaScript, a herança é implementada através da palavra-chave `extends`.


a) As duas afirmações são verdadeiras, e a segunda justifica a primeira.

b) As duas afirmações são verdadeiras, mas a segunda não justifica a primeira.

c) A primeira afirmação é verdadeira, e a segunda é falsa.

d) A primeira afirmação é falsa, e a segunda é verdadeira.

a alternativa correta é  a b, pois a palavr-chave´'extends' só define como a herança é implementada nas chaves do js. 
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
```


I) A classe Funcionario herda de Pessoa e pode acessar os atributos nome e idade diretamente.  
II) O método `apresentar()` da classe Funcionario sobrepõe o método `apresentar()` da classe Pessoa, mas chama o método da classe pai usando `super`.  
III) O código não funciona corretamente, pois Funcionario não pode herdar de Pessoa como uma classe, já que o JavaScript não suporta herança de classes.

Quais das seguintes afirmações são verdadeiras sobre o código acima?

a) I e II são verdadeiras.

b) I, II e III são verdadeiras.

c) Apenas II é verdadeira.

d) Apenas I é verdadeira.

A afirmação verdadeira é a letra a (I e II), pois Funcioário pode herdade de Pessoa como uma classe ao utilizar o 'extends'. 
______

**8) Analise as afirmações a seguir. Indique a alternativa correta e justifique sua resposta.**

**Asserção:** O conceito de polimorfismo em Programação Orientada a Objetos permite que objetos de diferentes tipos respondam à mesma mensagem de maneiras diferentes.  
**Razão:** Em JavaScript, o polimorfismo pode ser implementado utilizando o método de sobrecarga de métodos em uma classe.

a) A asserção é falsa e a razão é verdadeira.

b) A asserção é verdadeira e a razão é falsa.

c) A asserção é verdadeira e a razão é verdadeira, mas a razão não explica a asserção.

d) A asserção é verdadeira e a razão é verdadeira, e a razão explica a asserção.

 a alternativa correta é a b, pois a asserção é verdadeira, uma vez que o polimorfismo permite que objetos de diferentes classes respondam de formas diferentes a uma mesma mensagem, enquanto a razão é falsa pq js não tem suporte proprio para sobrecarga de métodos.

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

function somaArray(numeros) {
    // Começa a variável 'soma' com 0 para acumular a soma dos valores
    let soma = 0;
    // Usa 'numeros.length' para conseguir o tamanho do array ao invés de 'numeros.size'
    // Declara 'i' com let para limitar seu escopo ao bloco
    for (let i = 0; i < numeros.length; i++) {
        // Acumula o dobro de cada número e usa '+=' para somar ao invés de sobrescrever a variável
        soma += 2 * numeros[i];
    }
    // Retorna a soma acumulada
    return soma;
}

console.log(somaArray([1, 2, 3, 4])); // Saída esperada: 20

______
10) Crie um exemplo prático no qual você tenha duas classes:

- Uma classe `Produto` com atributos `nome` e `preco`, e um método `calcularDesconto()` que aplica um desconto fixo de 10% no preço do produto.
- Uma classe `Livro` que herda de `Produto` e modifica o método `calcularDesconto()`, aplicando um desconto de 20% no preço dos livros.

Explique como funciona a herança nesse contexto e como você implementaria a modificação do método na classe `Livro`.


class Produto {
  constructor(nome, preco) {
    this.nome = nome;
    this.preco = preco;
  }

  calcularDesconto() {
    return this.preco * 0.9;
  }
}

class Livro extends Produto {
  constructor(nome, preco, autor) {
    super(nome, preco);
    this.autor = autor;
  }

  calcularDesconto() {
    return this.preco * 0.8; 
  }
}

A herança nesse contwxto funciona pois a classe Livro utiliza a palavra 'extends' para herdar da classe Produto, o que significa que Livro passa a ter o s mesmos atributos e me´todos da classe Produto sem precisar definir-los de novo. No construtor de Livro, o uso de 'super' é necessário pra iniciar os atributos herdados. Além disso, a classe livro sobrescreve o método calcularDesconto para aplicar um desconto de 20% ao invés de 10%.
