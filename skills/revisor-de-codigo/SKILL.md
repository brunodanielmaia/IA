---
name: revisor-de-codigo
description: Revisa código ou um diff procurando bugs reais, falhas de segurança e problemas de manutenção, com achados priorizados e correções concretas. Use quando o usuário pedir code review, revisão de PR, "olha esse código", ou quiser saber se algo está pronto para subir.
---

# Revisor de código

Uma revisão útil encontra o que quebra em produção, não o que incomoda o gosto pessoal.

## Processo

1. **Entenda a mudança.** Leia o diff inteiro e o código ao redor que ele toca. Descubra a intenção: o que a mudança deveria fazer?
2. **Procure problemas nesta ordem de prioridade:**
   1. **Correção:** lógica errada, casos de borda (lista vazia, nulo, zero, fuso horário, concorrência), erros não tratados, off-by-one.
   2. **Segurança:** entrada do usuário sem validação, SQL/comando montado com string, segredos no código, falta de checagem de permissão, dados sensíveis em logs.
   3. **Dados e compatibilidade:** migrações irreversíveis, mudança de contrato de API, quebra de quem já usa a função.
   4. **Desempenho:** consulta dentro de loop (N+1), carregar tudo na memória, chamadas de rede repetidas.
   5. **Manutenção:** duplicação de lógica que já existe no projeto, nomes enganosos, complexidade sem necessidade.
   6. **Testes:** o comportamento novo e os casos de borda estão cobertos?
3. **Verifique cada achado antes de reportar.** Para cada suspeita, construa o cenário concreto: "com a entrada X, acontece Y em vez de Z". Se não conseguir montar o cenário, descarte ou marque como dúvida.
4. **Ignore** preferências de estilo que um linter resolveria, a não ser que o usuário peça.

## Formato da resposta

Comece com um veredito de uma linha: **pronto para subir**, **subir após ajustes** ou **precisa de retrabalho**.

Depois, os achados do mais grave ao menos grave:

```
### [Crítico | Importante | Sugestão] Título curto
**Onde:** arquivo.ext:linha
**Problema:** o que está errado.
**Cenário:** entrada/estado → resultado errado.
**Correção:** trecho de código ou passo concreto.
```

Termine com o que está bom na mudança (1 a 3 pontos), se houver algo que valha mencionar.
