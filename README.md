def rotina_kaprekar():
    numero = input("Digite um número de 4 dígitos: ").strip()


    if not numero.isdigit() or len(numero) != 4:
        print("Entrada inválida: digite exatamente 4 dígitos numéricos.")
        return


    if numero[0] == numero[1] == numero[2] == numero[3]:
        print("Entrada inválida: os 4 dígitos não podem ser iguais.")
        return

    print("\nPasso a passo da Rotina de Kaprekar:")

    passos = 0

    while numero != "6174":
 
        crescente = "".join(sorted(numero))
        decrescente = "".join(sorted(numero, reverse=True))

   
        resultado = int(decrescente) - int(crescente)

       
        numero_resultado = str(resultado).zfill(4)

        passos += 1
        print(f"Passo {passos}: {decrescente} - {crescente} = {numero_resultado}")

        numero = numero_resultado

    print(f"\nA constante de Kaprekar foi atingida: {numero}")
    print(f"Total de passos: {passos}")



rotina_kaprekar()
