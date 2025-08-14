Exercicio 1 - Livro
class Livro:
    def __init__(self, titulo, autor, numero_paginas):
        self.titulo = titulo
        self.autor = autor
        self.numero_paginas = numero_paginas
        self.pagina_atual = 0

    def abrir_livro(self):
        self.pagina_atual = 1
        print(f"Livro '{self.titulo}' aberto na página {self.pagina_atual}.")

    def ler_paginas(self, quantidade):
        if self.pagina_atual == 0:
            print("Abra o livro primeiro!")
        else:
            self.pagina_atual += quantidade
            if self.pagina_atual > self.numero_paginas:
                self.pagina_atual = self.numero_paginas
            print(f"Você leu mais {quantidade} páginas.")

    def exibir_progresso(self):
        lidas = self.pagina_atual
        faltam = self.numero_paginas - self.pagina_atual
        print(f"Páginas lidas: {lidas}")
        print(f"Páginas faltando: {faltam}")

livro1 = Livro("É assim que acaba", "Colleen Hoover", 368)
livro1.abrir_livro()
livro1.ler_paginas(30)
livro1.exibir_progresso()


Exercicio 2 - Conta Bancaria
class ContaBancaria:
    def __init__(self, titular, numero_conta):
        self.titular = titular
        self.numero_conta = numero_conta
        self.saldo = 0

    def depositar(self, valor):
        if valor > 0:
            self.saldo += valor
            print(f"Depósito de R${valor} feito com sucesso.")
        else:
            print("Valor inválido para depósito.")

    def sacar(self, valor):
        if valor <= self.saldo:
            self.saldo -= valor
            print(f"Saque de R${valor} realizado.")
        else:
            print("Saldo insuficiente.")

    def consultar_saldo(self):
        print(f"Saldo atual: R${self.saldo}")

    def exibir_extrato(self):
        print(f"Titular: {self.titular}")
        print(f"Número da Conta: {self.numero_conta}")
        print(f"Saldo: R${self.saldo}")

# Testando a classe
conta1 = ContaBancaria("Majulle", "9888345697")
conta1.depositar(2000)
conta1.sacar(300)
conta1.consultar_saldo()
conta1.exibir_extrato()
