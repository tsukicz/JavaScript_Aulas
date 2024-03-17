# Variáveis

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
# Tipos de Dados

### **Tipos primitivos**

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