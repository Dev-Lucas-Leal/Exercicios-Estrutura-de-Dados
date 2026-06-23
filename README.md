# Estruturas de Dados I (2026.1) — Exercícios Blindados: Era da IA 🛡️

Este repositório contém as resoluções e análises críticas desenvolvidas para a atividade **Exercícios Blindados: Era da IA**, referente à unidade de Arrays e Vetores em C. 

O objetivo central deste laboratório é atuar como auditor de códigos gerados por modelos de Inteligência Artificial, diagnosticando falhas clássicas de lógica, estouro de escopo e gerenciamento de memória em baixo nível, propondo as correções adequadas e documentando o comportamento indefinido (*undefined behavior*).

---

## 🎯 Estrutura do Projeto

Os exercícios foram documentados conforme as diretrizes formais da disciplina, estruturados em tarefas de diagnóstico conceitual, refatoração e análise comparativa de algoritmos.

*   **Documento de Referência:** `ED1_Blindados2_Arrays_Vetores.pdf`
*   **Entrega Oficial:** `ED1-Arrays-Vetores-LucasLeal.txt` (Arquivo unificado de respostas e códigos auditados)

---

## 💻 Detalhamento dos Exercícios Auditados

### 🧪 Exercício 1: O Censo da Colônia Lunar
*   **Tópico Principal:** *Buffer Overflow* (Estouro de Índice) e Limites de Iteração.
*   **Contexto da IA:** Um sistema para cadastrar a população de 5 setores habitáveis que compila perfeitamente, mas apresenta comportamentos erráticos ou travamentos em execução.
*   **Abordagem Técnica:** Análise do comportamento de loops usando condições de parada incorretas (`<=` em vez de `<`) em arrays de tamanho fixo. Discussão teórica sobre a ausência de verificação implícita de limites em C (*bounds checking*) versus o comportamento de exceções disparadas em linguagens de alto nível como Java e Python.

### 🛡️ Exercício 2: O Banco de Dados da SHIELD
*   **Tópico Principal:** Inicialização de Arrays e Lixo de Memória (*Garbage Memory*).
*   **Contexto da IA:** Um sistema de cadastro de IDs de agentes onde o somatório acumulado falha de forma inconsistente. A IA assumiu erroneamente que arrays locais em C zeram seus blocos por padrão.
*   **Abordagem Técnica:** Investigação teórica e prática sobre os ciclos de vida e escopo de variáveis (locais vs. globais). Implementação de duas estratégias de correção: inicialização explícita via agregação de chaves (`int agentes[MAX] = {0}`) e otimização das restrições de controle do laço de repetição.

### 🚀 Exercício 3: O Sistema de Temperatura da Nostromo
*   **Tópico Principal:** Passagem de Arrays para Funções e Decaimento para Ponteiros.
*   **Contexto da IA:** Um módulo para exibir temperaturas de setores antes e depois de uma conversão de escala. A IA assumiu que arrays de parâmetros eram passados por cópia em C, resultando em mutações colaterais indesejadas no vetor original.
*   **Abordagem Técnica:** Estudo sobre o comportamento de decaimento (*decay*) de arrays para ponteiros ao cruzar o escopo de funções. Explicação analítica baseada no funcionamento da Pilha de Chamadas (*Call Stack*) e aplicação de padrões de preservação de dados originais.

### 🛰️ Exercício 4: A Remoção de Tripulantes da ISS
*   **Tópico Principal:** Algoritmos de Deslocamento (*Shift*) e Acesso Inválido.
*   **Contexto da IA:** Um sistema de exclusão de registros que gera falhas ou corrupção de dados ao tentar remover o último elemento válido da estrutura.
*   **Abordagem Técnica:** Correção de lógica em loops de movimentação indexada (`v[j] = v[j+1]`) para conter acessos fora dos limites alocados (`v[n]`). Introdução à análise de complexidade de tempo assintótica, avaliando o custo operacional $O(n)$ de operações de remoção em arrays contíguos em comparação com listas encadeadas.

### 📡 Exercício 5: O Gerador de Sinais do SETI
*   **Tópico Principal:** Geração Pseudo-aleatória (`rand` / `srand`) e Escopo de Sementes.
*   **Contexto da IA:** Um simulador de frequências gerando vetores com elementos de valores estáticos idênticos devido ao reset contínuo do estado do gerador.
*   **Abordagem Técnica:** Correção de escopo no posicionamento do inicializador de semente pseudo-aleatória (`srand`), movendo-o para fora do fluxo iterativo estruturado. Investigação teórica diferenciando Geradores de Números Pseudo-Aleatórios (PRNG) de Geradores de Números Aleatórios Reais (TRNG) para uso em sistemas criptográficos e simulações críticas.

---

## 🛠️ Tecnologias e Padrões Aplicados

*   **Linguagem de Programação:** C (Compilação GCC / Padrão ANSI)
*   **Padrões de Escrita:** Identação e tabulação limpa de escopo, aplicação rigorosa de diretivas de pré-processador (`#define`) para manutenção de constantes.
*   **Abordagem Crítica:** Explicações dissertativas personalizadas, evitando reproduções automatizadas e priorizando a semântica conceitual detalhada.

---
Prof. Edkallenn Lima — Estruturas de Dados I
