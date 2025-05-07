# ArrayListJs  
Como manipular coleções com de Listas em Javascript utilizando: map, filter e reducer.

## `map()`

O `.map()` é usado para **transformar os elementos de um array**, criando um novo array com os resultados da transformação aplicada a cada elemento do array original.  
**Ele não modifica o array original**, mas **retorna um novo array com os valores transformados**.

### Sintaxe:

```javascript
const novoArray = arrayOriginal.map(callback(elemento, indice, array) {
  // Retorna o valor transformado
});
```

- Callback: Uma função que é chamada para cada elemento no array. É uma função que é **passada como argumento** para outra função.
  - Elemento: O elemento atual sendo processado.
  - Indice (opcional): O índice do elemento atual.
  - Array (opcional): O array original que está sendo iterado.
- NovoArray: O array após a transformação.

### Exemplo 1:

Dobrar os números de um array

```javascript
const numeros = [1, 2, 3, 4, 5];
const dobro = numeros.map(numero => numero * 2);

console.log(dobro); // [2, 4, 6, 8, 10]
```
Cada número foi multiplicado por 2. O array original permanece inalterado.

### Exemplo 2:

Extrair propriedades de objetos

```javascript
const usuarios = [
  { id: 1, nome: "Maria" },
  { id: 2, nome: "João" },
  { id: 3, nome: "Ana" }
];

const nomes = usuarios.map(usuario => usuario.nome);

console.log(nomes);
// Saída: ["Maria", "João", "Ana"]
```
Novo array com apenas a propriedade 'nome' do objeto.
___  

## `filter()`

O `.filter()` é um método que **filtra os elementos de um array com base em uma condição** e **retorna um novo array com os itens que passam nesse teste**.
Não modifica o array original.

Use o filter quando:
- Você precisa extrair apenas alguns itens de uma lista (array).
- O critério de escolha pode ser representado por um retorno true ou false.
- A estrutura da array não precisa ser modificada, apenas reduzida com base em condições.

### Sintaxe:

```javascript
const novoArray = arrayOriginal.filter(callback(elemento, indice, array) {
  // Retorna true para incluir o elemento no novo array
  // Retorna false para excluir o elemento
});
```
- Callback: Função que é chamada para cada elemento do array.
  - Elemento: O elemento atual sendo processado.
  - Indice (opcional): O índice do elemento atual.
  - Array (opcional): O array original.
- NovoArray: O array contendo os elementos que passaram no teste.

### Exemplo 1:

Filtrar números maiores que 10

```javascript
const numeros = [5, 12, 8, 130, 44];
const maioresQueDez = numeros.filter(num => num > 10);

console.log(maioresQueDez);
// Saída: [12, 130, 44]
```

Somente os números maiores que 10 foram mantidos no novo array.

### Exemplo 2:

Filtrar usuários ativos

```javascript
const usuarios = [
  { id: 1, nome: "Maria", ativo: true },
  { id: 2, nome: "João", ativo: false },
  { id: 3, nome: "Ana", ativo: true },
];

const usuariosAtivos = usuarios.filter(usuario => usuario.ativo);

console.log(usuariosAtivos);
// [
//   { id: 1, nome: "Maria", ativo: true },
//   { id: 3, nome: "Ana", ativo: true }
// ]

```

Apenas os objetos com ativo: true são incluídos no novo array.

___  

## `reduce()`

O `.reduce()` é um método que reduz um array a um único valor, aplicando uma função acumuladora em cada elemento, da esquerda para a direita. 
É útil para somar, multiplicar, agrupar ou transformar arrays em valores únicos ou objetos.

### Sintaxe

```javascript 
array.reduce(callback(acumulador, elementoAtual, indice, array), valorInicial);
```
- Callback: Função que será executada em cada elemento do array.
  - Acumulador: O valor acumulado da operação. Ele carrega o "resultado" até o momento.
  - ElementoAtual: O elemento atual do array sendo processado.
  - Indice (opcional): O índice do elemento atual.
  - Array (opcional): O array original.
- ValorInicial (opcional): Um valor inicial para o acumulador. Se não for fornecido, o primeiro elemento do array será usado como valor inicial e a iteração começa no segundo elemento.

### Exemplo 1:  

Somar todos os números do array  

```javascript

const numeros = [1, 2, 3, 4];
const soma = numeros.reduce((acumulador, numero) => acumulador + numero, 0);

console.log(soma);
// Saída: 10

```

### Exemplo 2:  

Contar quantas vezes cada item aparece

```javascript

const frutas = ['maçã', 'banana', 'maçã', 'laranja', 'banana', 'maçã'];

const contagem = frutas.reduce((acc, fruta) => {
  acc[fruta] = (acc[fruta] || 0) + 1;
  return acc;
}, {});

console.log(contagem);
// { maçã: 3, banana: 2, laranja: 1 }

```

___  

## Conclusão:

### `map()`: Transforma os dados  
O map percorre o array e aplica uma função em cada elemento, retornando um novo array com os valores transformados.  
É usado para modificar os elementos de um array, sem alterar o original.  


### `filter()`: Filtra os dados  
O filter também percorre o array, mas retorna somente os elementos que passam em uma condição, criando um novo array com eles.
É usado para remover itens indesejados de um array com base em alguma regra.  


### `reduce()`: Reduz os dados a um único valor  

O reduce percorre o array e acumula os valores em uma variável (o acumulador), até que reste um único resultado. É usado para somar, contar, juntar ou transformar um array em um valor só.
