Em algumas lógicas é necessário uma variável seja capaz de armazenar vários valores sequencialmente no endereço de memória. Em Python, essas estruturas de dados possuem métodos encapsulados
para manipular essas variáveis.

As principais estruturas de dados iteráveis são: `range`, `str`, `tuple`, `list`, `set`, e `dict`.

## Tuplas
Em Python, tupla é um identificador de um conjunto de dadosordenado e constante, depois de declarada uma tupla não pode adicionar um novo elemento, remover um existente ou alterar um valor existente. A nomeação de uma tupla ocorre atribuindo valores, divididos por vírgulas e delimitado por parênteses.

```py
tupla1 = ("apple", 2, "apple", True, False, 3.5)
tupla2 = ("maçã",)
nao_tupla = ("apple")

print(tupla1[0])
# "apple"

print(tupla1[0:4])  
# ("apple" 2 "apple" True)

print(tupla2)   
# ("maçã",)

print(len(tupla1), len(tupla2)) 
# 6 1

print(type(tupla1), type(tupla2), type(nao_tupla))
# 'tuple' 'tuple' 'str'
```
