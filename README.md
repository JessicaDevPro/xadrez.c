#include <stdio.h>

// Constantes para as direções
#define CIMA "Cima"
#define BAIXO "Baixo"
#define ESQUERDA "Esquerda"
#define DIREITA "Direita"

// ==================== 🏅 NÍVEL NOVATO ====================

void movimentoNovato() {
    printf("=== NÍVEL NOVATO ===\n");
    
    // Movimento do Bispo - 5 casas na diagonal superior direita
    printf("\n--- Bispo: 5 casas na diagonal superior direita ---\n");
    for(int i = 1; i <= 5; i++) {
        printf("%s + %s\n", CIMA, DIREITA);
    }
    
    // Movimento da Torre - 5 casas para a direita
    printf("\n--- Torre: 5 casas para a direita ---\n");
    int contador = 1;
    while(contador <= 5) {
        printf("%s\n", DIREITA);
        contador++;
    }
    
    // Movimento da Rainha - 8 casas para a esquerda
    printf("\n--- Rainha: 8 casas para a esquerda ---\n");
    contador = 1;
    do {
        printf("%s\n", ESQUERDA);
        contador++;
    } while(contador <= 8);
}

// ==================== 🏅 NÍVEL AVENTUREIRO ====================

void movimentoAventureiro() {
    printf("\n=== NÍVEL AVENTUREIRO ===\n");
    
    // Movimento do Cavalo em L (para baixo e esquerda)
    // Padrão do movimento em L: 2 casas em uma direção + 1 casa na perpendicular
    printf("\n--- Cavalo: Movimento em L para baixo e esquerda ---\n");
    
    // Primeira parte do L: 2 casas para baixo
    for(int i = 1; i <= 2; i++) {
        printf("%s\n", BAIXO);
    }
    
    // Segunda parte do L: 1 casa para esquerda
    int contador = 1;
    while(contador <= 1) {
        printf("%s\n", ESQUERDA);
        contador++;
    }
    
    // Versão com loops aninhados (movimento completo do cavalo)
    printf("\n--- Cavalo: Movimento completo em L com loops aninhados ---\n");
    for(int movimentoVertical = 1; movimentoVertical <= 2; movimentoVertical++) {
        for(int movimentoHorizontal = 1; movimentoHorizontal <= 1; movimentoHorizontal++) {
            if(movimentoVertical == 1) {
                // Primeira iteração: apenas movimento vertical
                printf("%s\n", BAIXO);
            } else {
                // Segunda iteração: movimento horizontal
                printf("%s\n", ESQUERDA);
            }
        }
    }
}

// ==================== 🥇 NÍVEL MESTRE ====================

// Funções recursivas para as peças

// Função recursiva para o Bispo (5 casas na diagonal direita para cima)
void moverBispoRecursivo(int casasRestantes) {
    if(casasRestantes <= 0) {
        return; // Caso base da recursão
    }
    
    printf("%s + %s\n", CIMA, DIREITA);
    moverBispoRecursivo(casasRestantes - 1); // Chamada recursiva
}

// Função recursiva para a Torre (5 casas para a direita)
void moverTorreRecursivo(int casasRestantes) {
    if(casasRestantes <= 0) {
        return; // Caso base da recursão
    }
    
    printf("%s\n", DIREITA);
    moverTorreRecursivo(casasRestantes - 1); // Chamada recursiva
}

// Função recursiva para a Rainha (8 casas para a esquerda)
void moverRainhaRecursivo(int casasRestantes) {
    if(casasRestantes <= 0) {
        return; // Caso base da recursão
    }
    
    printf("%s\n", ESQUERDA);
    moverRainhaRecursivo(casasRestantes - 1); // Chamada recursiva
}

void movimentoMestre() {
    printf("\n=== NÍVEL MESTRE ===\n");
    
    // Bispo com função recursiva
    printf("\n--- Bispo (Recursivo): 5 casas na diagonal direita para cima ---\n");
    moverBispoRecursivo(5);
    
    // Torre com função recursiva
    printf("\n--- Torre (Recursivo): 5 casas para a direita ---\n");
    moverTorreRecursivo(5);
    
    // Rainha com função recursiva
    printf("\n--- Rainha (Recursivo): 8 casas para a esquerda ---\n");
    moverRainhaRecursivo(8);
    
    // Cavalo com loops complexos (1 vez em L para cima à direita)
    printf("\n--- Cavalo: 1 vez em L para cima à direita ---\n");
    
    // Usando loops com variáveis múltiplas e condições complexas
    for(int vertical = 0, horizontal = 0; vertical < 2 || horizontal < 1; ) {
        if(vertical < 2) {
            printf("%s\n", CIMA);
            vertical++;
            continue; // Continua para a próxima iteração
        }
        
        if(horizontal < 1) {
            printf("%s\n", DIREITA);
            horizontal++;
            break; // Para após completar o movimento horizontal
        }
    }
    
    // Bispo com loops aninhados (requisito adicional)
    printf("\n--- Bispo com Loops Aninhados: 5 casas na diagonal ---\n");
    for(int i = 1; i <= 5; i++) {
        for(int j = 1; j <= 1; j++) {
            printf("Movimento %d: %s + %s\n", i, CIMA, DIREITA);
        }
    }
}

// ==================== FUNÇÃO PRINCIPAL ====================

int main() {
    printf("♔ DESAFIO DE XADREZ - MATECHECK ♔\n");
    printf("===================================\n\n");
    
    // Executar todos os níveis            
    movimentoNovato();      // 🏅 Nível Novato
    movimentoAventureiro(); // 🏅 Nível Aventureiro  
    movimentoMestre();      // 🥇 Nível Mestre
    
    printf("\n===================================\n");
    printf("🎉 Todos os movimentos foram executados com sucesso! 🎉\n");
    
    return 0;
}
