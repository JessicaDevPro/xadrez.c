# xadrez.c
Jogo de xadrez
DESAFIO DE XADREZ - MATECHECK
=============================

DESCRIÇÃO DO PROJETO:
Este programa simula os movimentos de peças de xadrez utilizando diferentes
estruturas de programação em C, atendendo aos três níveis do desafio.

NÍVEIS IMPLEMENTADOS:

🏅 NÍVEL NOVATO:
- Bispo: 5 casas na diagonal superior direita (usando FOR)
- Torre: 5 casas para a direita (usando WHILE)
- Rainha: 8 casas para a esquerda (usando DO-WHILE)

🏅 NÍVEL AVENTUREIRO:
- Cavalo: Movimento em L para baixo e esquerda
- Utiliza loops aninhados (FOR + WHILE)

🥇 NÍVEL MESTRE:
- Bispo, Torre e Rainha: Funções recursivas
- Cavalo: Loops com variáveis múltiplas, continue e break
- Bispo: Loops aninhados adicionais

CARACTERÍSTICAS TÉCNICAS:
- Linguagem: C
- Compilador: Compatível com GCC
- Estruturas utilizadas: FOR, WHILE, DO-WHILE, loops aninhados, funções recursivas
- Comandos especiais: CONTINUE, BREAK

INSTRUÇÕES DE COMPILAÇÃO E EXECUÇÃO:

1. Compilação:
   gcc xadrez_matecheck.c -o xadrez

2. Execução:
   ./xadrez

ESTRUTURA DO CÓDIGO:
- Constantes definidas para direções
- Funções separadas para cada nível
- Funções recursivas para movimentos
- Main function organizando a execução

AUTOR: [JÉSSICA SOUZA DOS ANJOS BARBOSA]
DATA: [31-10-25]
