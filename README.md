# AnalisadorLexicoJava

```
:DECLARACOES
argumento:INT
fatorial:INT

:ALGORITMO
% Calcula o fatorial de um número inteiro
LER argumento
ATRIBUIR argumento A fatorial
SE argumento = 0 ENTAO ATRIBUIR 1 A fatorial
ENQUANTO argumento < 1000
   INICIO
      ATRIBUIR fatorial * (argumento - 1) A fatorial
      ATRIBUIR argumento - 1 A argumento
   FIM
IMPRIMIR fatorial
```

```
java -jar "/Users/daniellucredio/NetBeansProjects/AlgumaLex/dist/AlgumaLex.jar" /Users/daniellucredio/Desktop/teste.txt
```

# Análise Sintática

```
:DECLARACOES
numero1:INTEIRO
numero2:INTEIRO
numero3:INTEIRO
aux:INTEIRO

:ALGORITMO
% Coloca 3 números em ordem crescente
LER numero1
LER numero2
LER numero3
SE numero1 > numero2 ENTAO
   INICIO
      ATRIBUIR 2+3-4+5-6*5-1 A aux
      ATRIBUIR numero1 A numero2
      ATRIBUIR aux A numero1
   FIM 
SE numero1 > numero3 E numero2 <= numero4 E numero1 > 3 OU numero2 <> numero4 ENTAO
   INICIO
      ATRIBUIR (numero3) A aux
      ATRIBUIR numero1 A numero3
      ATRIBUIR aux A numero1
   FIM
SE numero2 > numero3 ENTAO
   INICIO
      ATRIBUIR numero3 A aux
      ATRIBUIR numero2 A numero3
      ATRIBUIR aux A numero2
   FIM
IMPRIMIR numero1
IMPRIMIR numero2
IMPRIMIR numero3
```


```
java -jar /Users/daniellucredio/NetBeansProjects/alguma-sintatico/target/alguma-sintatico-1.0-SNAPSHOT-jar-with-dependencies.jar /Users/daniellucredio/Desktop/teste.txt 
```

# Análise Semântica 

```
(34 - 3 + 2) * (41 + 3)
```


```
:DECLARACOES
numero1:INTEIRO
numero2:INTEIRO
numero3:INTEIRO
%numero4:INTEIRO
aux:INTEIRO

:ALGORITMO
% Coloca 3 números em ordem crescente
LER numero1
LER numero2
LER numero3
SE numero1 > numero2 ENTAO
   INICIO
      ATRIBUIR 2+3-4+5-6*5-1 A aux
      ATRIBUIR numero1 A numero2
      ATRIBUIR aux A numero1
   FIM 
SE numero1 > numero3 E numero2 <= numero4 E numero1 > 3 OU numero2 <> numero4 ENTAO
   INICIO
      ATRIBUIR (numero3) A aux
      ATRIBUIR numero1 A numero3
      ATRIBUIR aux A numero1
   FIM
SE numero2 > numero3 ENTAO
   INICIO
      ATRIBUIR numero3 A aux
      ATRIBUIR numero2 A numero3
      ATRIBUIR aux A numero2
   FIM
IMPRIMIR numero1
IMPRIMIR numero5 + 3
IMPRIMIR 2 + 2.4
IMPRIMIR 'FIM'
```

# Gerador de código


```
:DECLARACOES
num:INTEIRO
potencia:INTEIRO
aux:INTEIRO
resultado:INTEIRO
:ALGORITMO
LER num
LER potencia
SE potencia = 0
ENTAO
   ATRIBUIR 1 A resultado
SENAO
   INICIO
      ATRIBUIR num A resultado
      ATRIBUIR 1 A aux
      ENQUANTO aux < potencia
         INICIO
            ATRIBUIR resultado * num A resultado
            ATRIBUIR aux + 1 A aux
         FIM
   FIM
IMPRIMIR 'O resultado é:'
IMPRIMIR resultado
```


```
:DECLARACOES
argumento:INTEIRO
fatorial:INTEIRO

:ALGORITMO
% Calcula o fatorial de um número inteiro
LER argumento
ATRIBUIR argumento A fatorial
SE argumento = 0 ENTAO ATRIBUIR 1 A fatorial
ENQUANTO argumento > 1
   INICIO
      ATRIBUIR fatorial * (argumento - 1) A fatorial
      ATRIBUIR argumento - 1 A argumento
   FIM
IMPRIMIR fatorial
```


```
:DECLARACOES
numero1:INTEIRO
numero2:INTEIRO
numero3:INTEIRO
aux:INTEIRO

:ALGORITMO
% Coloca 3 números em ordem crescente
LER numero1
LER numero2
LER numero3
SE numero1 > numero2 ENTAO
   INICIO
      ATRIBUIR numero2 A aux
      ATRIBUIR numero1 A numero2
      ATRIBUIR aux A numero1
   FIM 
FIMSE
SE numero1 > numero3 ENTAO
   INICIO
      ATRIBUIR numero3 A aux
      ATRIBUIR numero1 A numero3
      ATRIBUIR aux A numero1
   FIM
FIMSE
SE numero2 > numero3 ENTAO
   INICIO
      ATRIBUIR numero3 A aux
      ATRIBUIR numero2 A numero3
      ATRIBUIR aux A numero2
   FIM
FIMSE
IMPRIMIR numero1
IMPRIMIR numero2
IMPRIMIR numero3
```

# P-Code Machine

Nesta pasta você encontra detalhes sobre a máquina P-Código, utilizada nas aulas sobre geração de código.

## Conteúdo
- [Executável (arquivo .jar)](pcodemachine-executable.zip)
- [Código-fonte (projeto do NetBeass)](pcodemachine-source)

## Instruções

As seguintes instruções são aceitas pela P-Code Machine:

| Instrução | Descrição |
|-----------|-----------|
| `rdi`     | Retira um endereço `A` do topo da pilha, lê um valor `X` da entrada e armazena `X` na memória, no endereço `A` |
| `wri`     | Retira um valor `X` do topo da pilha e escreve `X` na saída |
| `lda A`   | Insere o endereço `A` no topo da pilha |
| `ldc C`   | Insere a constante `C` no topo da pilha |
| `lod A`   | Lê o conteúdo da memória no endereço `A` e o insere no topo da pilha |
| `mpi`     | Retira um valor `X` do topo da pilha, retira outro valor `Y` do topo da pilha, e insere `X * Y` no topo da pilha |
| `dvi`     | Retira um valor `X` do topo da pilha, retira outro valor `Y` do topo da pilha, e insere `Y / X` no topo da pilha |
| `adi`     | Retira um valor `X` do topo da pilha, retira outro valor `Y` do topo da pilha, e insere `X + Y` no topo da pilha |
| `sbi`     | Retira um valor `X` do topo da pilha, retira outro valor `Y` do topo da pilha, e insere `Y - X` no topo da pilha |
| `sto`     | Retira um valor `X` do topo da pilha, retira um endereço `A` do topo da pilha, e armazena `X` na memória, no endereço `A` |
| `grt`     | Retira um valor `X` do topo da pilha, retira outro valor `Y` do topo da pilha, e armazena `Y > X` (um booleano) no topo da pilha |
| `let`     | Retira um valor `X` do topo da pilha, retira outro valor `Y` do topo da pilha, e armazena `Y < X` (um booleano) no topo da pilha |
| `gte`     | Retira um valor `X` do topo da pilha, retira outro valor `Y` do topo da pilha, e armazena `Y >= X` (um booleano) no topo da pilha |
| `lte`     | Retira um valor `X` do topo da pilha, retira outro valor `Y` do topo da pilha, e armazena `Y <= X` (um booleano) no topo da pilha |
| `equ`     | Retira um valor `X` do topo da pilha, retira outro valor `Y` do topo da pilha, e armazena `X == Y` (um booleano) no topo da pilha |
| `neq`     | Retira um valor `X` do topo da pilha, retira outro valor `Y` do topo da pilha, e armazena `X != Y` (um booleano) no topo da pilha |
| `and`     | Retira um valor booleano `X` do topo da pilha, retira outro valor booleano `Y` do topo da pilha, e armazena `X && Y` (um booleano) no topo da pilha |
| `or`      | Retira um valor booleano `X` do topo da pilha, retira outro valor booleano `Y` do topo da pilha, e armazena `X || Y` (um booleano) no topo da pilha |
| `lab L`   | Sem efeito na execução. Apenas marca uma posição de código com um rótulo `L` |
| `ujp L`   | Salta para a instrução marcada com `L` |
| `fjp L`   | Retira um valor booleano `X` do topo da pilha e caso seja falso, salta para a instrução marcada com `L`. Caso seja verdadeiro, não executa nada. |
| `stp`     | Interrompe a execução |
