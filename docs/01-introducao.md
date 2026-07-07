# 01. Introdução à Programação Orientada a Objetos (POO)

## A Mudança de Paradigma
Até agora, você provavelmente estruturou seus códigos seguindo o paradigma **Procedural/Estrutural**, focado em sequências de passos, funções e procedimentos isolados que manipulam dados passados de um lado para o outro. 

A **Programação Orientada a Objetos (POO)** muda essa mentalidade. Em vez de pensar no código como uma lista de tarefas a serem executadas de cima para baixo, passamos a enxergar o sistema como um ecossistema de **entidades interdependentes** que interagem entre si, aproximando a estrutura do software do modo como percebemos o mundo real.

## O Molde e a Forma: Classes vs. Objetos

Para compreender a POO, é essencial dominar dois conceitos fundamentais:

### 1. Classe
A **Classe** é um modelo, uma planta arquitetônica ou um molde de fábrica. Ela não existe fisicamente no sistema como um dado concreto; em vez disso, ela define as características que algo terá quando for criado. Uma classe especifica:
* **Atributos**: As características ou dados (ex: cor, modelo, velocidade).
* **Métodos**: Os comportamentos ou ações que ela pode executar (ex: acelerar, frear).

### 2. Objeto
O **Objeto** é a instância real e concreta criada a partir daquele molde. Se a classe é a planta de uma casa, o objeto é a casa construída com tijolo e concreto. É possível criar infinitos objetos únicos utilizando a mesma classe como base.

---

## Analogia Prática (em Python)

Abaixo, veja como definimos uma classe e instanciamos objetos:

```python
# Definindo a Classe (O Molde)
class Carro:
    def __init__(self, marca, modelo, cor):
        # Atributos
        self.marca = marca
        self.modelo = modelo
        self.cor = cor
        self.velocidade = 0

    # Métodos (Comportamentos)
    def acelerar(self, incremento):
        self.velocidade += incremento
        print(f"O {self.modelo} acelerou para {self.velocidade} km/h.")

# Instanciando Objetos (Criando instâncias reais na memória)
meu_carro = Carro("Chevrolet", "Onix", "Preto")
carro_do_amigo = Carro("Volkswagen", "Gol", "Branco")

# Interagindo com os objetos
meu_carro.acelerar(40)