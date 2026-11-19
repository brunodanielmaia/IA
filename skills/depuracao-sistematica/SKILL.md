---
name: depuracao-sistematica
description: Encontra a causa raiz de bugs com método científico (reproduzir, levantar hipóteses, testar, corrigir, prevenir) em vez de tentativa e erro. Use quando algo não funciona, um teste falha, aparece um erro ou stack trace, ou o comportamento é diferente do esperado.
---

# Depuração sistemática

Não chute correções. Cada mudança deve testar uma hipótese.

## 1. Reproduza

- Escreva o comando ou os passos exatos que mostram o erro.
- Anote o resultado esperado e o resultado obtido, com a mensagem de erro completa.
- Se não for possível reproduzir, colete mais dados (logs, versões, ambiente) antes de qualquer mudança.
- Quando der, transforme a reprodução em um teste automatizado que falha.

## 2. Leia o erro de verdade

- Leia a stack trace de baixo para cima até achar a primeira linha que é do código do projeto.
- Abra esse arquivo e leia a função inteira, não só a linha.
- Confira o que mudou recentemente: `git log -p`, `git diff`, atualizações de dependências.

## 3. Levante hipóteses

Liste de 2 a 4 causas possíveis, da mais provável à menos provável. Para cada uma, diga que evidência a confirmaria ou descartaria.

## 4. Teste uma hipótese por vez

- Use a forma mais barata de obter evidência: um log, um print, um breakpoint, rodar só um teste.
- Se o espaço de busca for grande, divida ao meio (`git bisect`, comentar metade do código, testar com metade dos dados).
- Registre o que foi descartado para não repetir.

## 5. Corrija a causa, não o sintoma

- A correção deve explicar todos os sintomas observados.
- Evite `try/catch` que esconde o erro, `sleep` para "resolver" corrida, ou casos especiais só para a entrada que falhou.
- Rode a reprodução de novo e a suíte de testes relacionada.

## 6. Previna

- Mantenha o teste que reproduz o bug.
- Remova logs temporários.
- Se o mesmo erro pode existir em outro lugar, procure (`grep` pelo padrão).

## Entrega

Resuma em poucas linhas: **causa raiz**, **por que acontecia**, **o que foi mudado** e **como foi verificado**. Se não chegou à causa, diga isso claramente e o que já foi descartado.
