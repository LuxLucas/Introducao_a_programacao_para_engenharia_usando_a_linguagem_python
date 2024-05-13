# 2 - Como o Python vê o mundo

> Um comando muito utilizado é o `print()`. Ele escreve algo na saída padrão (no caso do Python, o console/tela)
> Formalmente o `print()` è:
> 
>  ```py
>   print(*objects, sep=' ', end='\n', file=sys.stdout)
>  ```
>  Onde:
> - _***objects:**_ lista de valores e/ou variáveis
> - _**sep = ' ':**_ caractere colocado entre cada valor escrito
> - _**end = '\n':**_ caractere usado no final da linha ('\n' pula a linha)
> - _**file = sys.stdout:**_ onde escrever as informações
>  
> Exemplos:  
> | PRINT | RESULTADO |
> | ----- | --------- |
> | print(1, 2, 3) | 1 2 3 |
> | print(1, 2, 3, sep=';') | 1;2;3 |

## Variáveis

O ato de declarar uma variável é: 
- (1) Reservar um espaço na memória RAM (Random Acess Memory).
- (2) Associar esse espaço a um identificador, ou seja, dar um nome a ele.

### Nomeação de variáveis
Assim como em outras linguagens, no Python, todo identificador:
- **Pode:**
  - **Começar com:** uma letra (caractere alfabético).
  - **Pode conter:** caracteres alfanuméricos (letra e números) e o "_" (underline).
  
- **Não pode:**
  - Espaço e caracteres especiais ("@", "-", "+", ".", "," ...).
  - _Palavras reservada_ (que possuem uso definido na linguagem), como: _for, if, int, print_ e entre outros.

O Python é case _sensitive_, ou seja, diferencia variáveis com letras minúsculas e maiúsculas. 
> Também, é aceito acentos em identificadores, mas não é recomendado para programadores.

**Tabela 2.1.** Nome de Identificadores
| Identificadores Válidos | Identificadores Inválidos |
| :---: | :---: |
| A | 1A |
| Nota1 | 1Nota |
| Media_Final | Média Final
| Aluno | Aluno-Curso |
| a12b12 | a12/b12 |
| escreva | print |

> **Exercício 2.1.** Explique os erros de sintaxe dos identificadores inválidos na Rabela 2.1.

> **Exercício 2.2.** Marque com um X os identificadores válidos no Python.
> | Coluna 1 | Coluna 2 | Coluna 3 |
> | --- | --- | --- |
> | [ ] media | [ ] x2 | [ ] xYZ |
> | [ ] salario-min | [ ] Km/h | [ ] W_12 |
> | [ ] Nome Carro | [ ] 4x4 | [ ] Alun@s |
> | [ ] SalaQ | [ ] "Média Final" | [ ] A13bq2_1 |

> **Exercício 2.3.** Classifique corretamente o tipo de cada uma das variáveis:
> 1. Salario_Minimo
> 2. Nome_Aluno
> 3. Sexo_Masculino
> 4. idade
> 5. Cidade_Natal
> 6. Hora_Consulta
> 7. Codigo_Curso
> 8. Peso
> 9. Ano_Nascimento

### Tipos de variáveis
A linguagem Python é _Dinâmicamente Tipada_. Significa que toda variável possui seu tipo alterado durante a execução do _script_, sendo o interpretador que decide.
```py
a = 1       # Inteiro
a = 1.0     # Float
a = "1"     # String
a = True    # Booleano
a = 3+12j   # Número complexo
```
> "#" (quadrilha) indica um comentário, tudo que o seguir, até o fim da linha, será ignorado pelo interpretador.  
> "\```" (crase) para comentar mais de uma linha, exemplo: \``` código ```.

**Tabela 2.2.** Tipos de Variáveis
| Tipo | Exemplo |
| --- | :---: |
| Booleano _(Bool)_ | True, False |
| Inteiro _(Int)_ | 1 |
| Ponto Flutuante _(Float)_ | 1.23 |
| Número complexo | 3+5x |
| String _(Str)_ | "12" |

