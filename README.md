menu = """

[d] Depositar
[s] Sacar
[e] extrato
[q] sair

=> """

saldo = 0
limite = 500
extrato = ""
numero_saque = 0 
LIMITE_SAQUES = 3

while True:

    opcao = input(menu)

if opcao == "d":
    valor = float(input("informe o valor do depósito: "))

    if valor > 0:
      saldo += valor
      extrato += f"depósito: R$ {valor:.2f}\n"


    else:
        print("operação falhou! o valor informado é inválido.")  
elif opcao == "s":
    valor = float(input("infomre o valor do saque:"))

    excedeu_saldo = valor > Saldo

    excedeu_limite = valor  > Limite

    excedeu_saques = numero_saques >= LIMITE_SAQUES

    if excedeu_saldo:
        print("Operação falhou! Você não tem saldo suficiente.")

    elif excedeu_limite:
         print("Operação falhou! valor de saque excede o limite.")        
    
    elif valor > 0:
        saldo -= valor
        extratp += f"Saque: R$ {valor:,}\n"
        numero_saques += 1

    else:
        print("Operação falhou! O valor informado é inválido.")  


elif opcao == "e":
    print("\n============ EXTRATO =============")
    print("Não foram realizados movimentações." if not extrato else extrato) 
    print(f"\nSaldo: R$ {saldo: .2f}")
    print("=============================")  

elif opcao == "q":
    break

else:
    print("Operação inválida, por favor selecione novamente a operação desejada.d")
 
