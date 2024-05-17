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
