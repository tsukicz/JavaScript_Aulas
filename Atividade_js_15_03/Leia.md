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
### **2.** **Bloco:**
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