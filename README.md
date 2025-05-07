# ArrayListJs
Tutorial de como manipular coleções com de Listas em Javascript utilizando: map, filter e reducer

## `map()`

O `.map()` é um método que **executa uma função em cada item** e **retorna um novo array** com os resultados dessa função.  
Ele **não altera o array original**, apenas cria uma nova versão dele.

### Sintaxe:

```javascript
const novoArray = arrayOriginal.map(function(elemento, indice, array) {
  // retorna novo valor para o elemento
});
```

### Exemplo 1:

Dobrar os números de um array

```javascript
const numeros = [1, 2, 3, 4, 5];
const dobrados = numeros.map(num => num * 2);

console.log(dobrados); // [2, 4, 6, 8, 10]
```
Cada número foi multiplicado por 2. O array original permanece inalterado.
