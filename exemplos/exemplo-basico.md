# Exemplo Prático: Unificando os Conceitos de POO

Este arquivo apresenta uma implementação completa em Python que serve de base e gabarito para os desafios propostos no guia. Aqui você verá a aplicação real de **Abstração**, **Encapsulamento**, **Herança** e **Polimorfismo**.

---

## Código-Fonte de Exemplo

```python
# 1. ABSTRAÇÃO E ENCAPSULAMENTO (Conta Bancária)

class ContaBancaria:
    def __init__(self, titular, saldo_inicial=0.0):
        self.titular = titular
        # Atributo privado/protegido usando convenção de underscore (_)
        self._saldo = float(saldo_inicial)

    # Método Getter para leitura segura do saldo
    @property
    def saldo(self):
        return self._saldo

    # Método público para depósito com validação
    def depositar(self, valor):
        if valor > 0:
            self._saldo += valor
            print(f"Depósito de R$ {valor:.2f} realizado com sucesso!")
        else:
            print("Erro: O valor do depósito deve ser positivo.")

    # Método público para saque com validação de saldo
    def sacar(self, valor):
        if valor <= 0:
            print("Erro: O valor do saque deve ser positivo.")
        elif valor > self._saldo:
            print(f"Erro: Saldo insuficiente para sacar R$ {valor:.2f}.")
        else:
            self._saldo -= valor
            print(f"Saque de R$ {valor:.2f} realizado com sucesso!")

# 2. HERANÇA E POLIMORFISMO (Funcionários)

class Funcionario:
    def __init__(self, nome, salario_base):
        self.nome = nome
        self.salario_base = salario_base

    # Método que será sobrescrito pelas classes filhas (Polimorfismo)
    def calcular_salario(self):
        return self.salario_base


class Gerente(Funcionario):
    def __init__(self, nome, salario_base, bonus):
        # Chama o construtor da classe mãe (Funcionario)
        super().__init__(nome, salario_base)
        self.bonus = bonus

    # Sobrescrita de Método (Polimorfismo)
    def calcular_salario(self):
        return self.salario_base + self.bonus


class Desenvolvedor(Funcionario):
    def __init__(self, nome, salario_base, projetos_entregues):
        super().__init__(nome, salario_base)
        self.projetos_entregues = projetos_entregues

    # Sobrescrita de Método (Polimorfismo: 15% de bônus por projeto)
    def calcular_salario(self):
        gratificacao = self.salario_base * (0.15 * self.projetos_entregues)
        return self.salario_base + gratificacao

# TESTANDO A EXECUÇÃO DO SISTEMA

if __name__ == "__main__":
    print("--- Testando Encapsulamento ---")
    conta = ContaBancaria("Milani", 1000.0)
    conta.depositar(500)
    conta.sacar(2000)  # Deve falhar por saldo insuficiente
    conta.sacar(300)
    print(f"Saldo Final Protegido: R$ {conta.saldo:.2f}\n")

    print("--- Testando Herança e Polimorfismo ---")
    # Criando uma lista de funcionários diferentes (comportamento polimórfico)
    equipe = [
        Gerente("Alice", salario_base=8000.0, bonus=2000.0),
        Desenvolvedor("Bruno", salario_base=5000.0, projetos_entregues=2)
    ]

    for f in equipe:
        # Cada objeto responde ao método de forma diferente baseada na sua classe
        print(f"Funcionário(a): {f.nome} | Salário Total: R$ {f.calcular_salario():.2f}")