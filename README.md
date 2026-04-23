 def validar_numero(entrada):
    # Verifica se a entrada contém apenas dígitos
    if not entrada.isdigit():
        return False, "Entrada inválida: digite apenas números."

    # Verifica se possui exatamente 4 dígitos
    if len(entrada) != 4:
        return False, "Entrada inválida: o número deve ter exatamente 4 dígitos."

    # Verifica se todos os dígitos são iguais
    if len(set(entrada)) == 1:
        return False, "Entrada inválida: os 4 dígitos não podem ser todos iguais."

    return True, ""


def rotina_kaprekar(numero):
    passos = 0

    print(f"\nIniciando a Rotina de Kaprekar com: {numero}\n")

    while numero != 6174:
        num_str = f"{numero:04d}"

        maior = int("".join(sorted(num_str, reverse=True)))
        menor = int("".join(sorted(num_str)))

        resultado = maior - menor
        passos += 1

        print(f"Passo {passos}: {maior:04d} - {menor:04d} = {resultado:04d}")

        numero = resultado

    print(f"\nConstante de Kaprekar atingida: {numero}")
    print(f"Total de passos: {passos}")


def main():
    entrada = input("Digite um número de 4 dígitos: ").strip()

    valido, mensagem = validar_numero(entrada)

    if not valido:
        print(mensagem)
        return

    numero = int(entrada)
    rotina_kaprekar(numero)


if __name__ == "__main__":
    main()
