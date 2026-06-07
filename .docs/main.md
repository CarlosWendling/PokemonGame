# main

## Visão Geral

O arquivo `main.cpp` é o ponto de entrada da aplicação.

Sua responsabilidade é:

1. definir os times participantes;
2. gerar todos os confrontos possíveis;
3. construir os grafos de batalha;
4. executar as análises;
5. consolidar os resultados.

---

# Fluxo Geral

```text
Inicialização
      │
      ▼
Criação dos Times
      │
      ▼
Combate Pokémon x Pokémon
      │
      ▼
Construção do Grafo
      │
      ▼
Análise do Grafo
      │
      ▼
Relatório Final
```

---

# Criação dos Times

Dois vetores armazenam os participantes.

```cpp
std::vector<Pokemon*> team1
std::vector<Pokemon*> team2
```

Cada Pokémon possui:

- tipos;
- atributos base;
- conjunto de movimentos.

---

# Geração dos Confrontos

O programa executa:

```cpp
for (auto* p1 : team1)
{
    for (auto* p2 : team2)
    {
        ...
    }
}
```

Essa estratégia produz todas as combinações possíveis entre os dois times.

---

## Complexidade

Se:

```text
n = tamanho do time 1
m = tamanho do time 2
```

então:

```text
O(n × m)
```

combates serão analisados.

---

# Construção do Grafo

Para cada confronto:

```cpp
CombatGraph cg(p1, p2);
```

é criado.

O construtor:

1. cria o estado inicial;
2. gera todos os estados alcançáveis;
3. armazena as transições.

---

# Execução das Análises

A classe `MetaAnalyzer` é utilizada para responder perguntas sobre o combate.

---

## Taxa de Vitória

```cpp
CalculateWinRateP1()
```

Calcula a proporção de estados terminais vencidos pelo Pokémon 1.

---

## Vencedor Absoluto

```cpp
CheckAbsoluteWinner()
```

Verifica se apenas um dos combatentes pode vencer.

---

## Ciclos

```cpp
DetectEndlessBattles()
```

Detecta batalhas potencialmente infinitas.

---

## Simulação Demonstrativa

```cpp
PrintSampleBattle()
```

Exibe uma trajetória específica de estados para fins ilustrativos.

---

# Consolidação dos Resultados

Após todos os confrontos:

- taxas de vitória são acumuladas;
- pontuações individuais são calculadas;
- métricas globais são produzidas.

---

# Perguntas Respondidas pelo Programa

Ao final da execução, o sistema responde:

## 1. Qual equipe possui maior dominância?

Comparação do desempenho agregado dos dois times.

---

## 2. Qual Pokémon teve melhor desempenho individual?

Análise do score acumulado de vitórias.

---

## 3. Existem vitórias absolutas?

Busca por dominância total de um combatente.

---

## 4. Existem batalhas intermináveis?

Detecção de ciclos no espaço de estados.

---

## 5. A vantagem de tipo é sempre determinante?

Verificação de casos onde atributos ou velocidade compensam desvantagens elementais.

---

# Papel do main.cpp

O arquivo não contém regras de negócio da batalha.

Sua função é coordenar os componentes do sistema:

```text
main
 ├── cria Pokémon
 ├── cria CombatGraph
 ├── executa MetaAnalyzer
 └── gera relatório
```

Dessa forma, a lógica principal permanece encapsulada nas classes especializadas do projeto.
