># Variáveis

Temos 3 variáveis que podemos usar em JavaScript, sendo elas:

- `let`
- `var`
- `const`

### **1**. `let`:
**let**: Similar ao `var`, mas tem escopo de bloco. Isso significa que a variável só é válida dentro do bloco onde é declarada.

```javascript
let num = 20;
console.log(num);
```

### **2.** `var`:
**var**: Usado para declarar uma variável. Anteriormente era a única maneira de declarar variáveis em JavaScript, mas agora é menos usada devido a escopo confuso.

```javascript
var palavra = "Denise";
console.log(palavra);
```

### **3.** `const`:
**const**: Cria uma variável cujo valor é fixo e não pode ser reatribuído após a sua inicialização.

```javascript
const num = 25;
console.log(num);
```
# Escopo

Em JavaScript, existem três tipos principais de escopo:

- `Global`
- `Bloco`
- `Função`

### **1.** **GLOBAL:**
- Variáveis declaradas fora de qualquer função têm escopo global.
- Elas podem ser acessadas de qualquer lugar do código.
- São úteis para valores que precisam ser compartilhados em todo o programa.

```javascript
var variavelGlobal = 10;

function exemplo() {
    console.log(variavelGlobal);
}

exemplo();
```
### **2.** **BLOCO:**
- Variáveis declaradas com let e const têm escopo de bloco.
- Elas só podem ser acessadas dentro do bloco onde são declaradas.
- São úteis para evitar vazamento de variáveis e manter o código mais organizado.

```javascript
let variavel = "global";

if (true) {
    let bloco = "bloco";
    console.log("Dentro do bloco:", bloco); 
    variavel = "global no bloco"; 
}

console.log("Fora do bloco:", variavel);
```
### **3.** **FUNÇÃO:**
- Variáveis declaradas dentro de uma função têm escopo local.
- São acessíveis apenas dentro da função onde são definidas.
- Não são visíveis ou acessíveis fora da função.

```javascript
function funcao() {
    var local = "Esta é uma variável local";
    console.log(local); 
}
 funcao();
```
># Tipos de Dados
---
## **Tipos primitivos**

Os tipos primitivos em JavaScript são os tipos de dados fundamentais que não são objetos e não têm métodos próprios, possui cinco tipos principais de dados primitivos, esses que podem ser representados:

- `Boolean`
- `Number`
- `String`
- `Undefined`
- `Null` 

### **1. Boolean:**
- Representa um valor lógico que pode ser true (verdadeiro) ou false (falso).
- É frequentemente usado em expressões condicionais e operações lógicas.

```javascript
let chovendo = true;
let ensolarado = false;

if (chovendo) {
    console.log("Leve um guarda-chuva!");
} else {
    console.log("Vamos dar um passeio!");
}
```
### **2. Number:**
- Representa números, tanto inteiros quanto de ponto flutuante.
- Pode ser usado para operações matemáticas e cálculos.

```javascript
let idade = 30;
let pi = 3.14;

let total = idade * pi;
console.log(total); 
```
### **3. String**
- Representa texto.
- Deve ser colocado entre aspas simples (') ou duplas (").

```javascript
let mensagem = "Olá, mundo!";
let nome = 'João';

console.log(mensagem + " Meu nome é " + nome); 
```

### **4. Undefined**
- Representa uma variável que foi declarada, mas ainda não foi atribuída a um valor.
- É atribuído automaticamente a variáveis que foram declaradas, mas não inicializadas.

```javascript
let ind;
console.log(ind); 
```

### **5. Null**
- Representa a ausência intencional de qualquer valor ou objeto.
- Pode ser usado para indicar a ausência de um valor em situações específicas.

```javascript
let nome = null;
console.log(nome); 
```

>## Exercício:

Faça um site capaz de entregar as duas raízes através um da fórmula de bhaskara em JavaScript. Podendo ser uma interface simples:

```javascript
<!DOCTYPE html>
<html lang = "pt-br">
<head>
    <meta charset = "UTF-8">
    <meta http-equiv = "X-UA-Compatible" content = "IE=edge">
    <meta name = "viewport" content = "width=device-width, initial-scale=1.0">
    <title>Soft Bhaskara</title>

    <style>

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            width: 100vw;
            height:100vh;

            background-color: rgb(243, 205, 221);
            display: grid;
            place-items: center;
        }

        .container {
            width: 25%;
            height: 40%;
            background-color: rgb(253, 230, 237);

            border-radius: 10px;
            border: 1px solid rgb(243, 205, 221);

            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
        }

        #coeficiente-c {
            margin-bottom: 15px;
        }

        label {
            color: rgb(197, 92, 153);

            font-weight: bolder;
            font-size: large;
        }

        input {
            width: 46%;
            height: 8%;
        }

        button {
            cursor: pointer;
            font-weight: bolder;

            width: 35%;
            height: 10%;

            background-color: rgb(209, 158, 188);
            color: rgb(250, 225, 239);
        }

        button:hover {
            color: rgb(235, 214, 227);
            background-color: rgb(206, 108, 163);
        }

        label, input, button, p {
            padding: 5px;
            margin: 3px;
            box-sizing: border-box; 
            border: none;
            border-radius: 5px;
        }

        p {
            color: rgb(197, 92, 153);

            font-size: x-large;
            font-weight: bolder;
        }

    </style>

</head>
<body>

    <div class = "container">

        <label for = "coeficiente-a">Entre com o coeficiente: "a"</label>
        <input type = "number" id = "coeficiente-a">

        <label for = "coeficiente-b">Entre com o coeficiente: "b"</label>
        <input type = "number" id = "coeficiente-b">

        <label for = "coeficiente-c">Entre com o coeficiente: "c"</label>
        <input type = "number" id = "coeficiente-c">

        <button id = "button" onclick = "calcularBhaskara()">Calcular</button>

        <p id = "result"></p>

    </div>

    <script>
        function calcularBhaskara() {
            let a = parseFloat(document.getElementById("coeficiente-a").value);
            let b = parseFloat(document.getElementById("coeficiente-b").value);
            let c = parseFloat(document.getElementById("coeficiente-c").value);

            let delta = Math.pow(b, 2) - 4 * a * c;

            if (delta < 0) {
                document.getElementById("result").innerHTML = "Não possuí raíz real.";

            } else {
                let x1 = (-b + Math.sqrt(delta)) / (2 * a);
                let x2 = (-b - Math.sqrt(delta)) / (2 * a);

                document.getElementById("result").innerHTML = "X1 = " + x1 + "<br>X2 = " + x2;
            }
        }
    </script>
    
</body>
</html>
```

### Objetos:
utilizamos objetos para agrupar valores que possuem propriedades e funções.

- **O que são:** Coleções de informações organizadas em pares chave-valor **=>** { nome: 'João', idade: 30, cidade: 'São Paulo' }
- **são usados:** Representam entidades com propriedades específicas.

```javascript
let usuario = {
    nome: 'Denise',
    idade: 17,
    email: 'denise@example.com',
    estáAtivo: true
};
```
### Array:
O array é um objeto no JavaScript, nos auxilia pois podemos utilizar uma única variável para armazenar uma lista de diferentes elementos, os arrays são definidos usando colchetes `[]`

- **O que são:** Listas ordenadas de itens **=>** ['maçã', 'banana', 'laranja']
- **são usados:** Armazenam múltiplos valores em uma única variável e são acessados por índices.

```javascript
let frutas = ['maçã', 'banana', 'laranja'];
```
># Operadores Básico
 >**Operadores Aritméticos:** Os operadores aritméticos são usados para realizar operações matemáticas básicas, como adição, subtração, multiplicação e divisão. 
- Adição: `+` 
 ```javascript 
  let soma = 10 + 5; 
```
- Subtração: `-` 
```javascript 
  let diferenca = 10 - 5; 
```
- Multiplicação: `*` 
```javascript 
let produto = 10 * 5; 
``` 
- Divisão: `/` 
 ```javascript
   let quociente = 10 / 5; 
```
- Módulo: `%` : o operador % é um pouco diferente na programação ele retorna o resto da divisão
```javascript
   let resto = 10 % 5; 
 ```
- Incremento: `++` 
```javascript
let x = 5;
x++; // x é igual a 6, ele adiciona + 1 ao numero
```
- Decremento: `--`
```javascript
let y = 5;
y--; // y é igual a 4, ele diminui - 1 do número
```

>**Operadores de comparação:** são usados para comparar valores e retornar um resultado booleano (verdadeiro ou falso), sendo eles: `==`, `!=`, `===`, `!==`, `>`, `<`, `>=` e `<=`:
```javascript
console.log(5 == 5);    
console.log('5' == 5);   

console.log(5 != 10);    
console.log('5' != 5);

console.log(5 === 5);    
console.log('5' === 5);  

console.log(5 !== '5');  
console.log(5 !== 5);  

console.log(10 > 5);    
console.log(5 < 10);  

console.log(10 >= 10);  
console.log(5 <= 10);   
```

>**Operadores Lógicos:** Os operadores lógicos são usados para combinar ou inverter valores booleanos, sendo os operadores `"&&" (E lógico)`, `"||" (OU lógico)` e `"!" (NÃO lógico)` são usados para avaliar condições complexas e tomar decisões com base nos resultados:

```javascript
console.log(true && true);   // true
console.log(true && false);  // false
console.log(false && true);  // false
console.log(false && false); // false

console.log(true || true);   // true
console.log(true || false);  // true
console.log(false || true);  // true
console.log(false || false); // false

console.log(!true);  // false
console.log(!false); // true
```
>**Typeof:** `typeof` é um operador unário em JavaScript que é usado para determinar o tipo de dado de uma expressão, ele retorna uma string indicando o tipo de dado.
O operador `typeof` é uma ferramenta útil para lidar com diferentes tipos de dados em JavaScript, especialmente em situações em que é necessário garantir que um determinado tipo de dado seja manipulado corretamente.

```javascript
console.log(typeof 42);        // 'number'
console.log(typeof 'Hello');   // 'string'
console.log(typeof true);      // 'boolean'
console.log(typeof undefined); // 'undefined'
console.log(typeof null);      // 'object' - cuidado! typeof null retorna 'object', mas null é primitivo
console.log(typeof {});        // 'object'
console.log(typeof []);        // 'object' - cuidado! Array é considerado um objeto em JavaScript
console.log(typeof function(){}); // 'function'
```