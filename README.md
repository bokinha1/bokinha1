ARQUIVO = "usuarios.txt"

def cadastrar_usuario():
    nome = input("Digite o nome: ")
    idade = input("Digite a idade: ")
    email = input("Digite o email: ")

    with open(ARQUIVO, "a", encoding="utf-8") as arquivo:
        arquivo.write(f"Nome: {nome} | Idade: {idade} | Email: {email}\n")

    print("\n✅ Usuário cadastrado com sucesso!\n")


def listar_usuarios():
    try:
        with open(ARQUIVO, "r", encoding="utf-8") as arquivo:
            print("\n📋 Usuários cadastrados:")
            print(arquivo.read())
    except FileNotFoundError:
        print("\n⚠️ Nenhum usuário cadastrado ainda.\n")


def menu():
    while True:
        print("==== MENU ====")
        print("1 - Cadastrar usuário")
        print("2 - Listar usuários")
        print("3 - Sair")

        opcao = input("Escolha uma opção: ")

        if opcao == "1":
            cadastrar_usuario()
        elif opcao == "2":
            listar_usuarios()
        elif opcao == "3":
            print("\n👋 Saindo do programa...")
            break
        else:
            print("\n❌ Opção inválida!\n")


menu()
