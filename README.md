# Tipagens do TypeScript: `any`, `unknown`, `string`, e `number`

O TypeScript adiciona tipagem estática ao JavaScript, ajudando a prevenir erros e melhorar a qualidade do código. Neste guia, exploraremos os tipos fundamentais `any`, `unknown`, `string` e `number`, suas diferenças, vantagens e exemplos de uso.

---

## **`any`: Flexibilidade sem Restrições**

### **O que é?**
O tipo `any` permite que uma variável receba qualquer valor, desativando as verificações de tipo.

### **Vantagens**
- Útil em códigos legados ou durante a migração de JavaScript para TypeScript.
- Oferece flexibilidade total.

### **Desvantagens**
- Remove a segurança de tipo.
- Pode causar erros em tempo de execução, já que o TypeScript não faz validações.

### **Exemplo**
```tsx
let value: any;

value = "Texto";
console.log(value.toUpperCase()); // Funciona.

value = 42;
console.log(value.toFixed(2)); // Funciona, mas sem garantias de tipo.
```

## **`unknown`: Flexibilidade com Segurança**

### **O que é?**
O tipo `unknown` aceita qualquer valor, mas exige validação antes do uso. É mais seguro que `any`.

### **Vantagens**
- Força o desenvolvedor a validar o tipo dos dados.
- Previne erros em tempo de execução.

### **Desvantagens**
- Pode ser mais verboso, exigindo validações explícitas.

### **Exemplo**
```tsx
let value: unknown;

value = "Texto";
if (typeof value === "string") {
  console.log(value.toUpperCase()); // É seguro.
}

value = 42;
if (typeof value === "number") {
  console.log(value.toFixed(2)); // É seguro.
}
```

## **`string`: Manipulação de Texto**

### **O que é?**
O tipo `string` é usado para representar valores textuais, como nomes, mensagens e URLs.

### **Vantagens**
- Disponível para métodos de manipulação de texto.
- Melhora a legibilidade do código.

### **Exemplo**
```tsx
const greet = (name: string): string => {
  return `Olá, ${name}!`;
};

console.log(greet("Danilo")); // Olá, Danilo!
```

## **`number`: Representação Numérica**

### **O que é?**
O tipo `number` é usado para valores numéricos, sejam inteiros ou de ponto flutuante.

### **Vantagens**
- Permite operações matemáticas.
- Compatível com valores financeiros, contadores e mais.

### **Exemplo**
```tsx
const calculateArea = (radius: number): number => {
  return Math.PI * radius ** 2;
};

console.log(calculateArea(5)); // 78.53981633974483


