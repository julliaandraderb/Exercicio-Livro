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
