# Código da Atividade - Modelos de Camisetas

```
def main():
    modelos = ["Modelo 1", "Modelo 2", "Modelo 3", "Modelo 4"]
    tamanhos = ["P", "M", "G"]
    estoque = []

    # cadastro inicial
    for modelo in modelos:
        linha = []
        for tamanho in tamanhos:
            qtd = int(input(f"{modelo}, tamanho {tamanho}: "))
            while qtd < 0:
                print("Quantidade inválida!")
                qtd = int(input("Digite novamente: "))
            linha.append(qtd)
        estoque.append(linha)

    # menu
    while True:
        print("\n1-Consultar  2-Vender  3-Repor estoque")
        print("4-Estoque abaixo de 3  5-Mostrar tudo  6-Sair")
        op = input("Escolha: ")

        if op == "6":
            print("Programa encerrado!")
            break

        elif op == "4":
            verificar_estoque_baixo(estoque, modelos, tamanhos)

        elif op == "5":
            mostrar_tudo(estoque, modelos)

        elif op in ["1", "2", "3"]:
            gerenciar_operacao(estoque, modelos, tamanhos, op)

        else:
            print("Opção inválida!")


def verificar_estoque_baixo(estoque, modelos, tamanhos):
    for i in range(4):
        for j in range(3):
            if estoque[i][j] < 3:
                print(modelos[i], tamanhos[j], estoque[i][j])


def mostrar_tudo(estoque, modelos):
    print("       P   M   G")
    for i in range(4):
        print(modelos[i], estoque[i])


def gerenciar_operacao(estoque, modelos, tamanhos, op):
    m = int(input("Modelo (1 a 4): "))
    t = input("Tamanho (P, M ou G): ").upper()

    if m < 1 or m > 4 or t not in tamanhos:
        print("Modelo ou tamanho inválido!")
        return

    i = m - 1
    j = tamanhos.index(t)

    if op == "1":
        print("Quantidade disponível:", estoque[i][j])
    else:
        qtd = int(input("Quantidade: "))

        if qtd <= 0:
            print("A quantidade deve ser maior que zero!")
        elif op == "2" and qtd > estoque[i][j]:
            print("Estoque insuficiente!")
        elif op == "2":
            estoque[i][j] -= qtd
            print("Venda realizada!")
        else:
            estoque[i][j] += qtd
            print("Estoque atualizado!")


if __name__ == "__main__":
    main()
```
