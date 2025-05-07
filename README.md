# ArrayListJs
Como manipular coleções com de Listas em Javascript utilizando: map, filter e reducer.

## `map()`

O `.map()` é usado para transformar os elementos de um array, criando um novo array com os resultados da transformação aplicada a cada elemento do array original.  
Ele não modifica o array original, mas retorna um novo array com os valores transformados.

### Sintaxe:

```javascript
const novoArray = arrayOriginal.map(callback(elemento, indice, array) {
  // Retorna o valor transformado
});
```

callback: Uma função que é chamada para cada elemento no array.
elemento: O elemento atual sendo processado.
indice (opcional): O índice do elemento atual.
array (opcional): O array original que está sendo iterado.
novoArray: O array resultante após a transformação.

### Exemplo 1:

Dobrar os números de um array:

```javascript
const numeros = [1, 2, 3, 4, 5];
const dobro = numeros.map(numero => numero * 2);

console.log(dobro); // [2, 4, 6, 8, 10]
```
Cada número foi multiplicado por 2. O array original permanece inalterado.

### Exemplo 2:

Criar um novo array com apenas uma propriedade de cada objeto:

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
___  
## `filter()`
