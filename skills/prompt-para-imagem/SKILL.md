---
name: prompt-para-imagem
description: Cria prompts detalhados para geradores de imagem (GPT Image, Midjourney, Gemini/Nano Banana, Flux, Ideogram, Stable Diffusion). Use quando o usuário quiser gerar, editar ou estilizar uma imagem, pôster, capa, logo, foto de produto ou transformar uma foto em outro estilo.
---

# Prompt para imagem

Converte uma ideia curta em um prompt visual preciso, que gera bons resultados na primeira tentativa.

## Perguntas rápidas (só se faltar)

- Qual o uso final? (post de Instagram, capa de YouTube, banner, impressão)
- Existe foto de referência? Se sim, o que precisa ser preservado (rosto, produto, cores da marca)?
- Precisa de texto escrito na imagem? Qual texto exato?

## Estrutura do prompt

Escreva em parágrafos descritivos, não em lista de palavras soltas. Modelos atuais entendem linguagem natural muito melhor que "tags". Cubra, nesta ordem:

1. **Tipo de imagem e finalidade:** "pôster vertical", "foto de produto para e-commerce", "ilustração para capa de livro".
2. **Sujeito principal:** quem ou o que, com detalhes concretos (idade aparente, roupa, material, cor, expressão).
3. **Ação e pose:** o que o sujeito está fazendo; postura e direção do olhar.
4. **Cenário:** lugar, época, hora do dia, elementos de fundo.
5. **Iluminação:** fonte, direção e cor da luz (luz dourada lateral, néon, luz de estúdio suave).
6. **Câmera e composição:** enquadramento, ângulo, lente, profundidade de campo, onde fica o espaço vazio.
7. **Estilo visual:** técnica (fotografia, pintura digital, 3D, aquarela), paleta, referências de movimento artístico.
8. **Texto na imagem:** o texto exato entre aspas, fonte, cor e posição.
9. **Formato:** proporção (1:1, 3:4, 9:16, 16:9) e resolução quando o modelo aceitar.

## Quando houver foto de referência

- Diga explicitamente o que preservar: "mantenha o rosto, o tom de pele, o penteado e as proporções de cada pessoa".
- Diga o que pode mudar: roupa, pose, fundo, estilo.
- Peça uma verificação final: "confira a semelhança dos rostos e a anatomia das mãos antes de finalizar".
- Preserve o número exato de pessoas.

## Ajustes por modelo

- **GPT Image / Gemini:** parágrafos longos e instruções diretas funcionam bem; são bons em texto dentro da imagem.
- **Midjourney:** prompt mais enxuto, parâmetros no final (`--ar 3:4 --stylize 250 --v 7`).
- **Flux / Stable Diffusion:** descreva bem o estilo e a luz; use prompt negativo quando disponível.
- **Ideogram:** o melhor para tipografia; coloque o texto entre aspas.

## Cuidados

- Inspire-se em estilos ("arte promocional de jogo de mundo aberto dos anos 80") em vez de copiar personagens ou logos protegidos para uso comercial.
- Não gere imagens realistas de pessoas reais em situações falsas ou comprometedoras.

## Entrega

1. O prompt final em bloco de código.
2. Uma variação alternativa (outro ângulo, luz ou estilo).
3. Uma linha dizendo qual modelo tende a se sair melhor para esse pedido.
