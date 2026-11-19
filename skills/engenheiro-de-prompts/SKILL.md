---
name: engenheiro-de-prompts
description: Reescreve e melhora prompts para modelos de IA (Claude, ChatGPT, Gemini e outros). Use quando o usuário pedir para melhorar, revisar, otimizar ou criar um prompt, um system prompt, instruções de agente ou um prompt reutilizável.
---

# Engenheiro de prompts

Transforma um pedido vago ou um prompt fraco em um prompt claro, testável e reutilizável.

## Processo

1. **Entenda o objetivo antes de escrever.** Identifique:
   - Qual tarefa o modelo deve executar e para quem é o resultado.
   - Como é uma resposta boa (formato, tamanho, tom, nível de detalhe).
   - Quais entradas variam a cada uso (viram variáveis como `{{texto}}`).
   - O que costuma dar errado hoje.
   Se faltar algo essencial, faça no máximo 3 perguntas. Caso contrário, assuma o mais razoável e diga o que assumiu.

2. **Escreva o prompt com esta estrutura** (omita as seções que não fizerem sentido):
   - **Contexto:** quem é o usuário final, por que a tarefa existe, o que está em jogo.
   - **Tarefa:** o que fazer, em frases diretas no imperativo.
   - **Entradas:** cada variável delimitada por tags XML (`<documento>{{documento}}</documento>`).
   - **Critérios de qualidade:** o que torna a resposta boa, explicando o porquê de cada regra.
   - **Formato de saída:** estrutura exata esperada; use um exemplo quando o formato for rígido.
   - **Exemplos (opcional):** 1 a 3 exemplos variados, dentro de `<exemplo>`.

3. **Aplique as boas práticas atuais:**
   - Diga o que fazer, não só o que evitar. "Escreva em parágrafos corridos" funciona melhor que "não use listas".
   - Explique o motivo das regras. O modelo generaliza melhor quando entende a intenção.
   - Evite CAIXA ALTA, "SEMPRE" e "NUNCA" em excesso: modelos atuais seguem instruções à risca e podem exagerar.
   - Seja específico sobre o nível de esforço desejado ("vá além do básico", "responda em 3 frases").
   - Coloque documentos longos no início e a pergunta no final.
   - Para tarefas de raciocínio, peça para pensar antes de responder ou use o modo de raciocínio do modelo.
   - Não peça para o modelo "fingir ser um especialista" como única instrução: descreva o que o especialista faria.

4. **Revise o próprio prompt** com estas perguntas:
   - Uma pessoa inteligente, sem contexto, entenderia exatamente o que fazer?
   - Existem instruções contraditórias?
   - O formato de saída é verificável?
   - Há palavras que não mudam nada no resultado? Corte.

## Entrega

Entregue:
1. O prompt final em um bloco de código, pronto para copiar.
2. Uma lista curta das principais mudanças e por que foram feitas.
3. 2 ou 3 entradas de teste sugeridas, incluindo um caso difícil, para o usuário validar o prompt.
