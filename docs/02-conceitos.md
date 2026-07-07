# 02. Os 4 Pilares da Programação Orientada a Objetos

Com os conceitos de Classes e Objetos consolidados, entramos nos quatro pilares fundamentais que sustentam todo o paradigma da POO. Eles ditam como projetar sistemas robustos, escaláveis e fáceis de manter.

---

## 1. Abstração
Abstrair significa **isolar o que é essencial** para o contexto do seu sistema, descartando detalhes irrelevantes. 

* **Exemplo**: Se estamos modelando uma classe `Carro` para um *sistema de Detran*, precisamos de atributos como `placa`, `renavam` e `proprietario`. Se for para um *jogo de corrida*, precisamos de `velocidade_maxima`, `turbo` e `aerodinamica`. O objeto real é o mesmo, mas a abstração muda conforme a necessidade do software.

## 2. Encapsulamento
É a prática de **esconder os detalhes internos** de funcionamento de um objeto e proteger seus dados de acessos ou modificações externas indevidas. Criamos uma "cápsula" onde o estado interno só pode ser alterado por métodos controlados do próprio objeto (interface pública).

* **Na prática**: Usamos modificadores de acesso (atributos privados) e métodos de leitura/escrita conhecidos como **Getters** e **Setters**.
* **Benefício**: Garante a consistência dos dados (ex: impede que o saldo de uma conta bancária receba um valor negativo diretamente).

## 3. Herança
Permite que uma nova classe (classe filha ou subclasse) **herde atributos e comportamentos** de uma classe existente (classe mãe, superclasse ou classe base).

* **Objetivo**: Reutilização de código e eliminação de redundâncias.
* **Exemplo**: Uma classe mãe `Veiculo` possui o método `ligar()`. As classes filhas `Carro` e `Moto` herdam automaticamente esse método, sem a necessidade de reescrevê-lo do zero em cada uma.

## 4. Polimorfismo
A palavra significa "muitas formas". No desenvolvimento, é a capacidade de um objeto se comportar de maneiras diferentes dependendo do contexto, permitindo que classes filhas alterem o comportamento de métodos herdados da classe mãe.

* **Exemplo**: A classe mãe `Animal` define o método `emitir_som()`. 
  * A classe filha `Cachorro` sobrescreve esse método para fazer `Au Au`.
  * A classe filha `Gato` sobrescreve o mesmo método para fazer `Miau`.
   Ambos respondem ao mesmo método (`emitir_som`), mas cada um à sua própria maneira.