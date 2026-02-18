# test-coffee-machine
Simulates the operation of a coffee machine, allowing the user to choose drinks, insert money, receive change, and see operation messages.

VISUALG

algoritmo "Maquina de Café"
// Função :
// Autor : Rodrigo Lima
// Data : 2/5/2026
// Seção de Declarações 


Var
   opcao : Inteiro
   valorInserido, precoBebida, troco : Real
    opcaoValida : Logico
Inicio
   Escreval("--- MÁQUINA DE CAFÉ ---")
   Escreva("Insira o valor (£): ")
   Leia(valorInserido)

   Escreval("--- MENU ---")
   Escreval("1 - Café Expresso (£ 0,70)")
   Escreval("2 - Cappuccino    (£ 0,75)")
   Escreval("3 - Chocolate     (£ 1,00)")
   Escreva("Escolha sua bebida ou 0 para cancelar: ")
   Leia(opcao)

   // Preços
   Escolha opcao
      Caso 1
         precoBebida <- 0.70
      Caso 2
         precoBebida <- 0.75
      Caso 3
         precoBebida <- 1.00
      Caso 0
         Escreval("Operação cancelada pelo usuário.")
      Outrocaso
      Escreval("Opção Inválida. Devolvendo seu dinheiro...")
      interrompa
      FimEscolha
      fimse




   // Verificação de Saldo
   Se valorInserido >= precoBebida Entao
      Escreval("Preparando sua bebida... Por favor, aguarde.")
      Escreval("Bebida pronta! Retire no local indicado.")

      troco <- valorInserido - precoBebida
      Se troco > 0 Entao
         Escreval("Retire seu troco: £ ", troco:4:2)
      FimSe
   Senao
      Escreval("Saldo insuficiente. Faltam £ ", (precoBebida - valorInserido):4:2)
      Escreval("Operação cancelada. Devolvendo £ ", valorInserido:4:2)
   FimSe

   Escreval("--- Obrigado. Volte sempre! ---")
FimAlgoritmo

