# Tabela de Seções (40 bytes por seção)

| Hexadecimal | Significado | Valor | Bytes |
|----------|----------|----------|----------|
| 2E 73 72 64 61 74 61 00 | Nome | .srdata | (8 bytes) |
| 00 04 A8 01 | Tamanho Virtual | 0x1A80400 | (4 bytes) |
| 00 10 00 00 | Endereço Virtual | 0x1000 | (4 bytes) |
| 00 04 A8 01 | Tamanho no Disco | 0x1A80400 | (4 bytes) |
| 00 06 00 00 | Offset dos Dados Brutos | 0x600 | (4 bytes) |
| 00 00 00 00 | Relocações | 0x0 | (4 bytes) |
| 00 00 00 00 | Números de Linhas | 0x0 | (4 bytes) |
| 00 00 00 00 | Relocações / Números de Linhas | 0x0 | (4 bytes) |
| 20 00 00 40 | Características | 0x10000020 | (4 bytes) |


## Bytes 0-7: Nome (ASCII)
### Identifica a seção, como ".text" ou ".data"
```Hexidecimal
00 01 02 03 04 05 06 07
-----------------------
2E 73 72 64 61 74 61 00 -> 8 bytes
```
O que é? É o nome do capítulo (seção) escrito em letrinhas que o computador entende (ASCII).
Exemplo: .text (onde fica o código do programa), .data (onde ficam os dados).
Como é? Parece um nome de arquivo, mas tem no máximo 8 letras e termina com 00.
🧒 *"É como o título de um capítulo do livro: 'Capítulo 1 - O Código Secreto'!"*

## Bytes 8-11: Tamanho Virtual
### Quanto espaço a seção ocupa na memória RAM quando o programa está em execução
```Hexidecimal
08 09 0A 0B
-----------
00 04 A8 01 -> 4 bytes
```
O que é? Diz quanto espaço esse capítulo vai ocupar na memória RAM quando o programa rodar.
Exemplo: Se for 00 10 00 00, significa 4096 bytes (ou 4KB) na memória.
🧒 "É como dizer: 'Esse capítulo precisa de 10 páginas na sua memória quando você lê o livro!'"

## Bytes 12-15: Endereço Virtual (RVA)
### Onde a seção é carregada na memória (endereço relativo)
```Hexadecimal
0C 0D 0E 0F
-----------
00 10 00 00 -> 4 bytes
```
O que é? Diz onde o capítulo vai ficar na memória (o "endereço da casa" dele).
Exemplo: 00 10 00 00 significa que começa no endereço 0x1000 da RAM.
🧒 "É como o número da página onde o capítulo começa: 'Vá para a página 1000 para ler!'"

## Bytes 16-19: Tamanho no Disco
### Quanto espaço a seção ocupa fisicamente no arquivo .exe
```Hexadecimal
10 11 12 13
-----------
00 04 A8 01 -> 4 bytes
```
O que é? Diz quanto espaço o capítulo ocupa dentro do arquivo .exe (no disco).
Exemplo: Se for 00 04 00 00, são 1024 bytes (1KB) no arquivo.
🧒 "É o tamanho real do capítulo no livro físico. Pode ser diferente do tamanho na memória!"

## Bytes 20-23: Offset dos Dados Brutos
### Posição onde a seção começa dentro do arquivo .exe
```Hexadecimal
14 15 16 17
-----------
00 06 00 00 -> 4 bytes
```
O que é? Diz onde o capítulo começa dentro do arquivo .exe (o "número da página" no arquivo).
Exemplo: 00 06 00 00 significa que o capítulo começa no byte 1536 (0x600) do arquivo.
🧒 "É como um marcador de página: 'O Capítulo 3 começa na página 600 do livro!'"

## Bytes 24-27 Relocações
### Informações para ajustar endereços se o programa for carregado em posições diferentes
```Hexadecimal
18 19 1A 1B
-----------
00 00 00 00 -> 4 bytes
```

## Bytes 28-31 Números de Linhas
### Usado para depuração (relaciona código a linhas do arquivo fonte original)
```Hexadecimal
1C 1D 1E 1F
-----------
00 00 00 00 -> 4 bytes
```

## Bytes 32-35 Relocações / Números de Linhas
### Campo combinado raramente usado em arquivos modernos
```Hexadecimal
20 21 22 23
-----------
00 00 00 00 -> 4 bytes
```

## Bytes 36-39: Características (Permissões)
### Define se a seção é legível (R), gravável (W) ou executável (X)
```Hexadecimal
24 25 26 27
-----------
20 00 00 40 -> 4 bytes
```
O que é? Diz o que o capítulo pode fazer:
20 00 00 00 = Só pode ler (como um capítulo de história).
40 00 00 00 = Pode ler e escrever (como um caderno de anotações).
60 00 00 00 = Pode ler, escrever e executar (como um livro de feitiços que você pode rodar!).
🧒 "São as regras do capítulo: 'Você pode só ler? Pode escrever nele? Pode até executar como um feitiço?'"

