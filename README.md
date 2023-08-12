# the-machine-enigma
The enigma machine that appears in the movie The Imitation Game

# Criar as listas alphabet, rotor e reflector
alphabet = ['a', 'b', 'c', 'd', 'e', 'f', 'g', 'h', 'i', 'j', 'k', 'l', 'm', 'n', 'o', 'p', 'q', 'r', 's', 't', 'u', 'v', 'w', 'x', 'y', 'z']
rotor = ['d', 'j', 'k', 'm', 'v', 'u', 'a', 's', 'i', 'n', 't', 'q', 'e', 'b', 'o', 'c', 'l', 'g', 'f', 'h', 'x', 'p', 'z', 'r', 'y', 'w']
reflector = ['q', 'w', 'e', 'r', 't', 'y', 'u', 'i', 'o', 'p', 'a', 's', 'd', 'f', 'g', 'h', 'j', 'k', 'l', 'z', 'x', 'c', 'v', 'b', 'n', 'm']

#uma def para as letras cifradas
def letra_cifrada(letter):
    if letter in alphabet:
        position = alphabet.index(letter)
        position += 1
        if position >= len(alphabet):
            position = 0
        return rotor[position]
    else:
        return letter
    
mensagem = "o naruto pode ser um pouco duro as vezes"
mensagem_cifrada = ""
for letter in mensagem:
    mensagem_cifrada += letra_cifrada(letter)

print("Mensagem Cifrada:" , mensagem_cifrada)
    
#def para as letras decifradas
def letra_decifrada(letter):
    if letter in alphabet:
        position = rotor.index(letter)
        position -= 1
        return alphabet[position]
    else:
        return letter
    
mensagem_decifrada = ""
for letter in mensagem_cifrada:
    mensagem_decifrada += letra_decifrada(letter)

print("Mensagem decifrada:" , mensagem_decifrada)
