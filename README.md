# Exercício de Testes Unitários Vanilla - Account

---

## Descrição do Projeto
Este projeto foi desenvolvido para praticar conceitos de **testes unitários** em Java, utilizando a biblioteca **JUnit 5**. Ele implementa uma classe `Account` que simula operações bancárias básicas, como depósitos, saques e saques totais, com regras específicas de negócio. Além disso, utiliza uma fábrica (`AccountFactory`) para facilitar a criação de objetos de teste.

---

## Objetivo
O objetivo principal do exercício é:
1. **Implementar testes unitários** para validar o comportamento da classe `Account`.
2. Garantir que os métodos implementados respeitem as regras de negócio descritas.

---

## Estrutura do Projeto

src/ ├── entities/ │ └── Account.java ├── tests/ │ ├── entities/ │ │ └── AccountTests.java │ └── factory/ │ └── AccountFactory.java

- **`Account`**: Representa uma conta bancária com operações básicas.
- **`AccountFactory`**: Fornece métodos utilitários para criar instâncias da classe `Account` com dados pré-definidos.
- **`AccountTests`**: Contém os testes unitários para validar os comportamentos da classe `Account`.

---

## Regras de Negócio Implementadas

1. **Depósito (`deposit`)**:
   - Depósitos positivos aumentam o saldo, mas aplicam uma taxa percentual (2%).
   - Depósitos negativos não afetam o saldo.

2. **Saque Total (`fullWithdraw`)**:
   - Retorna todo o saldo da conta e o reduz para zero.

3. **Saque Parcial (`withdraw`)**:
   - Reduz o saldo em uma quantia específica, caso haja saldo suficiente.
   - Lança uma exceção (`IllegalArgumentException`) se o saldo for insuficiente.

---

## Testes Implementados
Os testes foram desenvolvidos na classe `AccountTests`, utilizando o framework **JUnit 5**.

### **1. Teste de Depósito com Quantia Positiva**
- **Objetivo**: Validar que o saldo aumenta corretamente após o depósito de uma quantia positiva, aplicando a taxa de 2%.
- **Cenário**:
  - Quantia: `200.0`
  - Saldo Inicial: `0.0`
  - Saldo Esperado: `196.0`

### **2. Teste de Depósito com Quantia Negativa**
- **Objetivo**: Verificar que um depósito com valor negativo não altera o saldo da conta.
- **Cenário**:
  - Saldo Inicial: `100.0`
  - Quantia: `-200.0`
  - Saldo Esperado: `100.0`

### **3. Teste de Saque Total**
- **Objetivo**: Garantir que o método `fullWithdraw` zera o saldo e retorna o valor total que estava na conta.
- **Cenário**:
  - Saldo Inicial: `800.0`
  - Saldo Final: `0.0`
  - Valor Retornado: `800.0`

### **4. Teste de Saque Parcial**
- **Objetivo**: Validar que o método `withdraw` reduz corretamente o saldo quando há fundos suficientes.
- **Cenário**:
  - Saldo Inicial: `800.0`
  - Quantia do Saque: `500.0`
  - Saldo Final: `300.0`

---

## Como Executar os Testes
1. Certifique-se de ter o **JUnit 5** configurado em seu projeto.
2. Execute os testes da classe `AccountTests` usando sua IDE favorita (Eclipse, IntelliJ, etc.) ou pela linha de comando com o Maven/Gradle.

---

## Tecnologias Utilizadas
- **Java 17**
- **JUnit 5** para testes unitários

---


