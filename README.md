# ArrayListJs
Tutorial de como manipular coleções com de Listas em Javascript utilizando: map, filter e reducer


## 🔄 `map()`

### O que faz?

Cria um novo array com os resultados da função aplicada a cada item do array original.

### Exemplo:

```javascript
const numeros = [1, 2, 3, 4, 5];
const dobrados = numeros.map(num => num * 2);

console.log(dobrados); // [2, 4, 6, 8, 10]
