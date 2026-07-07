# 03. Desafios de Fixação

Chegou a hora de colocar a mão na massa e testar seus conhecimentos! Resolva as questões teóricas e, em seguida, desenvolva os scripts práticos em Python.

---

## 📝 Questões Teóricas

### 1. Uma classe está para um objeto assim como:
* a) Uma função está para uma variável.
* b) Uma planta arquitetônica está para uma casa construída.
* c) Um loop for está para um laço while.
* d) Um dado do tipo string está para um dado do tipo float.

### 2. Quando alteramos o modificador de acesso de um atributo para torná-lo privado, impedindo que ele seja modificado diretamente fora da classe e forçando o uso de métodos de validação, estamos aplicando qual pilar da POO?
* a) Abstração
* b) Herança
* c) Encapsulamento
* d) Polimorfismo

### 3. Imagine que uma classe mãe `FormaGeometrica` possui um método chamado `calcular_area()`. As classes filhas `Quadrado` e `Circulo` herdam esse método, mas cada uma implementa uma fórmula matemática diferente dentro dele. Esse comportamento é um exemplo clássico de:
* a) Encapsulamento
* b) Polimorfismo
* c) Abstração pura
* d) Acoplamento estrutural

---

## 💻 Desafios Práticos

### Desafio 1: Encapsulamento de Dados
**Cenário**: Sistema de Controle de Conta Bancária.

1. Crie uma classe chamada `ContaBancaria` com os atributos privados `titular` e `_saldo` (inicializado em `0.0`).
2. Proteja o atributo `_saldo` para que ele não possa ser alterado diretamente de fora da classe.
3. Crie um método público `depositar(valor)` que aceita apenas valores positivos.
4. Crie um método público `sacar(valor)` que verifica se o cliente possui saldo suficiente antes de efetuar a operação.
5. Crie um método getter para permitir a leitura segura do saldo atual.

---

## Desafio 2: Herança e Polimorfismo
**Cenário**: Gerenciamento de Funcionários de uma Empresa.

1. Crie uma classe mãe chamada `Funcionario` com os atributos `nome` e `salario_base`. Ela deve possuir um método `calcular_salario()` que apenas retorna o `salario_base`.
2. Crie uma classe filha chamada `Gerente` que herda de `Funcionario`. O gerente possui um atributo extra chamado `bonus`. Sobrescreva o método `calcular_salario()` para retornar o salário base somado ao bônus.
3. Crie outra classe filha chamada `Desenvolvedor` que herda de `Funcionario`. Sobrescreva o método `calcular_salario()` para retornar o salário base acrescido de uma gratificação fixa de 15% por projeto entregue (adicione um atributo para contar os projetos).
4. Instancie um objeto de cada tipo e exiba o cálculo final do salário de cada um para testar o comportamento polimórfico.