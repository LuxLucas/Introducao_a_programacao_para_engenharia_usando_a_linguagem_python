# 3 - Estruturas Fundamentais
São estruturas fundamentais para qualquer programa: **bloco sequencial de comandos**  sequência de instruções a serem executadas -, **instruções condicinais** - determinam condições 
necessárias para a execução de um determinado bloco de código - e **instruções de repetição** - indicam critérios para a repetição de um bloco de comando.

## Blocos de código
Uma diferença marcante de Python em relação outras linguagens é que blocos de código são determinados pela tabulação/identação, diferentemente do Java e Pascal que usam, respectivamente, `{ }`
e `begin`/`end`. A tabuação é necessária para organizar as linhas de código.

Quando for usar estruturas de repetição ou condicionais será necessário identificar o bloco contida nelas, para tal precisamos da tabulação/identação criada atravéz do `tab` - ou 4 espaços.

```py
# Cálculo do IMC - Índice de Massa Corporal

# Entrada
Altura = float(input("Sua Altura: "))
Peso = float(input("Seu Peso: "))
# Processamento
IMC = Peso/(Altura**2)
# Saída
print("IMC: ", IMC)
```

No código acima as instruções estão alinhadas da esquerda para a direita, formando assim um único bloco que será executado de maneira linear, de maneira sequencial.

## Condicionais
Uma estrutura condicional executa um bloco de código caso uma expressão lógica for verdadeira.
```py
# Determina se um número é par ou ímpar

# Realiza a leitura de um número
Numero = int(input("Entre com um número: "))

# Informa uma resposta padrão
Resposta = "Número é PAR"

# Se o resto do número por 2 for igual a 1
if (Numero % 2 == 1):
    # Altera a resposta para informar que é ímpar
    Resposta = "Número é ÍMPAR"
# Imprime o resultado
print(Resposta)
```

O comando `if` é usado para executar, ou não, blocos de código se uma expressão lógica for verdadeira. 

Numa estrutura condicional composta por dois ou mais blocos excludentes A, B e C, se a condição de A for atendida, o bloco A será executado e não o B ou o C. Se a condição de A não 
for atendida, será testado a condição de B e, caso retorne um valor `True`, executará o bloco B. Caso as condições de A e B não forem atendidas o bloco C será executado.

No exemplo dado, o bloco A seria o formado pelo `if`, com uma condição a ser testada. O bloco B seria formada por `elif`, também com uma condição a ser testada vindo logo após o `if`.
O bloco C representa o `else`, que não possui uma condição explícita para executar seu código, vindo após do `if` e do `elif`, se ouver.

```py
numero = int(input("Digite um numero de 0 a 10: "))

if (numero >= 0) and (numero < 4):
    # Bloco de instruções A
    print("O número que você digitou é maior ou igual a 0 e menor que 4")
elif (numero >= 4) and (numero < 8):
    # Bloco de instruções B
    print("O numero que você digitou é maior ou igual a 4 e menor que 8")
else:
    # Bloco de instruções C
    print("O número que você digitou é maior ou igual a 8")
```

Relembrando a tabela de operadores:

| Operador | É verdadeiro quando... |
| :------: | ---------------------- |
| a == | "a" é igual "b" |
| a != b | "a" é diferente de "b" |
| a > b | "a" for maior que "b" |
| a < b | "a" for menor que "b" |
| a >= b | "a" for maior ou igual a "b" |
| a <= b | "a" for menor ou igual a "b" |
| a or b | "a" e/ou "b" forem verdadeiros |
| a and b | "a" e "b" forem verdadeiros |
| not a | "a" for falso |

Um exemplo do uso de blocos condicionais:

```py
primeiro_numero = float(input("Seu primeiro número: "))
segundo_numero = float(input("Seu segundo número: "))
terceiro_numero = float(input("Seu terceiro número: "))

# Define um valor padrão
maior = primeiro_numero
menor = primeiro_numero
medio = primeiro_numero

# Define o maior número
if (segundo_numero > maior) and (segundo_numero > terceiro_numero):
    maior = segundo_numero
elif (terceiro_numero > maior) and (terceiro_numero > segundo_numero):
    maior = terceiro_numero

# Define o menor número
if (segundo_numero < menor) and (segundo_numero < terceiro_numero):
    menor = segundo_numero
elif (terceiro_numero < menor) and (terceiro_numero < segundo_numero):
    menor = terceiro_numero

# Define o número médio
if (primeiro_numero == maior or primeiro_numero == menor) and (terceiro_numero == maior or terceiro_numero == menor):
    medio = segundo_numero
elif (segundo_numero == maior or segundo_numero == menor) and (primeiro_numero == maior or primeiro_numero == menor):
    medio = terceiro_numero

# Retorna o resultado
print("O maior número é: ", maior, ". O número médio é: ", medio, ". O menor número é: ", menor)
```

## Laços
Certas ocasiões precisamos que um pedaço de código seja repetido uma quantidade _x_ de vezes, seja essa quantidade determinada ou não. Assim como outras linguagens, o Python utiliza os
comando `for` e `while`, mas com algumas peculiaridades - como veremos no `for`.

### While
O comando `while` repete um bloco de código enquanto uma condição for verdadeira. Quando ele termina uma execução, retorna para testar a condição e, se for verdadeira, reexecuta o pedaço deo programa, se não, sai do laço de repetição. Segue o exemplo.

```py
from random import randint

# Computador sorteia um número inteiro entre 1 e 100
num_computador = randint(1, 100)

# Número de tentativas máxima
tentativas_max = 10

# Número de tentativas inicial
tentativas = 0

num_digitado = 0
while (tentativas < tentativas_max) and (num_digitado != num_computador):
    print("\nVocê tem", tentativas_max - tentativas, "chances")
    num_digitado = int(input('Qual o número do computador?: '))

    # Incrementa o número de tentativas
    tentativas += 1

    # Informa se o número digitado for menor que o escolhido pelo computador
    if (num_computador < num_digitado):
        print("O número sortedo é menor que", num_digitado)

    # Informa se o número digiado for maior que o escolhido
    elif (num_computador > num_digitado):
        print("O número sortedo é maior que", num_digitado)

# Informa o resultado
if num_digitado == num_computador:
    print("Parabéns, você acertou o número escolhido pelo computador em", tentativas, "tentativas")
else:
    print("Você perdeu o número escolhido foi:", num_computador)
```

### For
Diferente de linguagens como Visual Basic, PHP e Java, o `for`do Python lida com um conjunto de dados iterativos. Ao contrário das linguagens citadas o, a instrução `for` do Python não altera uma variável sequencialmente de forma a atingir um limite superior ou inferior. Dados iterativos no Python são: `list`, `set`, `range`, `dict` e `tuple`.

Examine o comando com **for x in conjunto:**. Primeiro inicia-se pela palavra reservada `for` e, depois, uma variável "x" de cada elemto do conjunto.

Suponha um conjunto de elementos inteiros formados por: [0, 1, 2, 3, 4]. Para cada repetição a variável "x" receberá um valor de cada elemento do conjunto, na primeira repetição "x" receberá 0, na segunda, 1, assim por diante até receber o último elemento do conjunto - no caso 4. Quando uma repetição termina, "x" recebe o próximo elemento do conjunto. Esse tipo de repetição idealmente só termina quando "x" recebe o último valor do conjunto.

Uma maneira de utilizar o `for` como nas outras linguagens é por meio da função `range()`, que recebe um número inteiro _n_ e retorna um conjunto de _n_ números, padronizadamente, de 0 até _n_.

```py
for x in range(4):
    print(x, end=" ")
    # Escreve 0 1 2 3
print() # Quebra de linha
 
for x in range(1, 4):   # Utiliza o início e o fim do range
    print(x, end=" ")
    # Escreve 1 2 3
print() # Quebra de linha

for x in range(1, 8, 2):    # Utiliza o início, fim e o incremento
    print(x, end=" ")
    # Escreve 1 3 5 7 
print()

for x in range(8, 1, -2):   # Utiliza o for de maneira decrescente
    print(x, end=" ")
    # Escreve 8 6 4 2
print()
```

### O _break_ e o _else_
Há duas instruções que podem ser usadas junto de laços de repetição:

- O _break_ interrompe a execução do laço de repetição mais próximo em que está inserindo
- O _else_ define um bloco de código que será executado após o fim do laço de repetição, desde que _não tenha sido interrompido pelo break_

```py
for x in range(3):
    for y in range(3):
        if x <= y:
            break
        print(x, y)
# Resultado:
# 1 0
# 2 0
# 2 1
```

```py
soma_repeticao = 0
for i in range(3):
    for j in range(5):
        soma_repeticao += x + j
else:
    print(soma_repeticao)
    # Escreve 60
```
