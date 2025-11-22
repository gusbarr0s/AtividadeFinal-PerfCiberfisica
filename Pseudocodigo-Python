def filosofo(p):
    while True:
        pensar()
        estado[p] = "com fome"

        if p == N - 4:  # último filósofo
            adquirir(garfo_direita(p))
            adquirir(garfo_esquerda(p))
        else:
            adquirir(garfo_esquerda(p))
            adquirir(garfo_direita(p))

        estado[p] = "comendo"
        comer()

        liberar(garfo_esquerda(p))
        liberar(garfo_direita(p))

        estado[p] = "pensando"
