# primeirojogo

import os

palavra_secreta = 'jaguatirica'
letra_acertadas = ''
erro = 0
tentativas = 0
letras_digitadas = ''

while True:
    letra_digitada = input('Digite uma letra: ')
    tentativas += 1
    


    if len(letra_digitada) > 1:
        print('Digite apenas uma letra.')
        continue
    letras_digitadas += letra_digitada + '-'
    
    if letra_digitada in palavra_secreta:
        letra_acertadas += letra_digitada
    
    elif letra_digitada not in palavra_secreta:
        erro += 1
    
    if erro == 6:
        os.system('clear')
        print('YOU LOSER!!')
        print('A palavra secreta era:', palavra_secreta)
        break
    
    palavra_formada = ''
    
    for letra_secreta in palavra_secreta:
        if letra_secreta in letra_acertadas:
            palavra_formada += letra_secreta
        else:
            palavra_formada += '_.'
    
    print('Palavra formada:', palavra_formada)
    print(letras_digitadas)
    
    if palavra_formada == palavra_secreta:
        os.system('clear')
        print('CONGLATIONS!!')
        print('A palavra secreta era:', palavra_secreta)
        print('tentativas:', tentativas)
        print('tentativas incorretas:', erro)
        letra_acertadas = ''
        tentativas = 0
