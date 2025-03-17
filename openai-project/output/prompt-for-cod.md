Aqui está a implementação do algoritmo de Dijkstra em linguagem C. Este algoritmo encontra o caminho mais curto de um vértice inicial para todos os outros vértices em um grafo ponderado representado por uma matriz de adjacência:


#include <stdio.h>
#include <limits.h>
#include <stdbool.h>

#define V 5 // Número de vértices no grafo

int minDistance(int dist[], bool sptSet[]) {
    int min = INT_MAX, minIndex;

    for (int v = 0; v < V; v++)
        if (!sptSet[v] && dist[v] <= min) {
            min = dist[v];
            minIndex = v;
        }
    return minIndex;
}

void printSolution(int dist[]) {
    printf("Vértice \t Distância da origem\n");
    for (int i = 0; i < V; i++)
        printf("%d \t\t %d\n", i, dist[i]);
}

void dijkstra(int graph[V][V], int src) {
    int dist[V];
    bool sptSet[V];

    for (int i = 0; i < V; i++) {
        dist[i] = INT_MAX;
        sptSet[i] = false;
    }

    dist[src] = 0;

    for (int count = 0; count < V - 1; count++) {
        int u = minDistance(dist, sptSet);
        sptSet[u] = true;

        for (int v = 0; v < V; v++)
            if (!sptSet[v] && graph[u][v] && dist[u] != INT_MAX && dist[u] + graph[u][v] < dist[v])
                dist[v] = dist[u] + graph[u][v];
    }

    printSolution(dist);
}

int main() {
    int graph[V][V] = {
        {0, 10, 0, 0, 5},
        {10, 0, 1, 0, 2},
        {0, 1, 0, 4, 0},
        {0, 0, 4, 0, 3},
        {5, 2, 0, 3, 0}
    };

    dijkstra(graph, 0);

    return 0;
}

Como funciona:
O número de vértices do grafo é definido por V.

O grafo é representado por uma matriz de adjacência.

A função dijkstra calcula a menor distância do vértice de origem (src) para todos os outros.

A saída mostra o menor custo para cada vértice a partir do vértice de origem.



Aqui está a tradução do algoritmo de Dijkstra para Python:

import sys

V = 5  # Número de vértices no grafo

def minDistance(dist, sptSet):
    min_val = sys.maxsize
    min_index = -1

    for v in range(V):
        if not sptSet[v] and dist[v] <= min_val:
            min_val = dist[v]
            min_index = v

    return min_index

def printSolution(dist):
    print("Vértice \t Distância da origem")
    for i in range(V):
        print(f"{i} \t\t {dist[i]}")

def dijkstra(graph, src):
    dist = [sys.maxsize] * V
    sptSet = [False] * V

    dist[src] = 0

    for _ in range(V - 1):
        u = minDistance(dist, sptSet)
        sptSet[u] = True

        for v in range(V):
            if not sptSet[v] and graph[u][v] and dist[u] != sys.maxsize and dist[u] + graph[u][v] < dist[v]:
                dist[v] = dist[u] + graph[u][v]

    printSolution(dist)

if __name__ == "__main__":
    graph = [
        [0, 10, 0, 0, 5],
        [10, 0, 1, 0, 2],
        [0, 1, 0, 4, 0],
        [0, 0, 4, 0, 3],
        [5, 2, 0, 3, 0]
    ]

    dijkstra(graph, 0)

Diferenças principais para Python:
Estrutura de Dados Simples: Utilizamos listas ao invés de arrays fixos.

sys.maxsize: Usamos esse valor para representar o infinito (INT_MAX em C).

Funções e Sintaxe Python: Mais concisa e legível, aproveitando as funcionalidades da linguagem.
