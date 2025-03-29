# Sistema-banc-rio-DIO
Atividade do curso em Python na DIO

# Criando um sistema Bancário com Python.
Menu = """

[1] = Depositar
[2] = Sacar
[3] = Extrato
[4] = Sair


  Menu
=> Digite uma Opção: """

saldo = 2000
limite = 500
extrato = ""
número_de_saque = 0
limite_saque = 3

while True:
    
    opção = input(Menu)
    
    if opção == "1": 
        valor = float(input("Digite o valor do deposito: "))
        
        if valor > 0:
            saldo += valor 
            extrato += f"deposito: R$ {valor:.2f}\n"
            print("Deposito realizado com sucesso.")
        
            
        else:
            print("Operação invalida.")
        
        
    
    elif opção == "2":
        Valor = float(input("Digite o valor do saque: "))
        
    
        excedeu_saldo = Valor > saldo
        
        excedeu_limite = Valor > limite
        
        excedeu_saque = número_de_saque >= limite_saque 
       
        if excedeu_saldo:
           print("Operação invalida, saldo insuficiente.")
           
           
        elif excedeu_limite:
            print("Operação invalida, limite insuficiente.")
            print("consulte seu extrato.")
            
            
        elif excedeu_saque:
            print("Operação invalida, limite de saque atingido.")
            print("consulte seu extrato no Menu.")
            
            
        elif Valor > 0:
            saldo -= Valor
            extrato += f"Saque: R$ {Valor:.2f}\n"
            número_de_saque += 1 
            
        
            
            
        else:
            print("Operação invalida.")
            
       
    elif opção == "3":
        print("\n============== EXTRATO ============")
        print("Não foram realizado movimentações." if not extrato else extrato)
        print(f"\nsaldo: R$ {saldo:.2f}\n")
        print("=====================================")
        
        
    elif opção == "4":
        print("Obrigado e volte sempre.")
        break
        
    
    else:
        print("Opção invalida, Por favor selecione novamente as opções acima")
