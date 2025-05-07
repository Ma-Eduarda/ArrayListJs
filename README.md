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

O `.filter()` é um método que filtra os elementos de um array com base em uma condição e retorna um novo array com os itens que passam nesse teste.
Ele não modifica o array original.

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
