---
name: sabor-fable
description: Sabor Fable, guia de design visual do Grupo PTG (PYCloud, Paraguay Tech Group e divisões), destilado dos trabalhos que o Fable 5.2 fez e o David aprovou. Linguagem "ficha técnica cartográfica", tokens dos temas escuro e claro, tipografia, ícones, mapa animado do Paraguai e o processo de propor antes de mudar. Use sempre que o pedido envolver visual, layout, cores, fontes, ícones, animação, tema claro/escuro ou "melhorar o design" de qualquer site, landing page, tela, protótipo, painel (PY Console) ou peça da PYCloud, do Paraguay Tech Group, da Solustic ou de outra divisão do grupo, inclusive quando ele disser "sabor fable", "no estilo do Fable", "deixa igual ao site da PYCloud", "segue o padrão", "analise e sugira melhorias" ou criar uma tela nova, mesmo sem citar a palavra design.
---

# Sabor Fable

O site da PYCloud (`PYCloud/pycloud-site/index.html`) é o modelo do grupo. A direção visual dele, "ficha técnica cartográfica", foi criada pelo Fable 5.2 em 12 nov 2026 e adotada como oficial; depois o PY Console e o site do grupo PTG passaram a segui-la. Esta skill existe para que qualquer modelo repita esse resultado sem precisar do Fable: o que garante a qualidade são as decisões abaixo, que o David já aprovou, e o processo que ele gosta.

## Antes de começar

1. **Abra a fonte de verdade.** Leia o `<style>` e o sprite de ícones de `PYCloud/pycloud-site/index.html` e o README do repositório. Se esta skill e o código divergirem, vale o código (o site evolui).
2. **Leia a referência que serve ao pedido:**
   - `references/linguagem-visual.md`: tokens, tipografia, grid, componentes, ícones, mapa. Leia sempre que for mexer em visual.
   - `references/historico-decisoes.md`: o que o David aprovou, rejeitou e pediu para mudar em cada projeto, com as palavras dele. Leia ao propor mudanças, para não repetir algo já rejeitado.
3. **Leia o design system do grupo** em `Site PTG/design-system/project/README.md` (e `tokens.json`, `components/`, `assets/`): voz e tom ("usted", títulos em caixa de frase com ponto final, nunca "holding"), nomes oficiais das divisões, selo "Hecho en Paraguay", ñandutí, mapa real, WhatsApp. Ele é anterior às decisões do Fable, então **em conflito vale esta ordem: código do site PYCloud > regras desta skill > README do design system**. Conflitos conhecidos: o README ainda pede IBM Plex Mono e Google Fonts (substituídos por Plex Sans e fontes locais) e "um único movimento por página" (o mapa animado da PYCloud foi aprovado; numa página nova, mantenha um movimento principal e o resto discreto).
4. **Veja o estado atual no navegador** (preview do projeto, nos dois temas) antes de opinar.
5. Para referência externa ao criar algo novo, consulte a SEESAW (https://www.seesaw.website/) na categoria certa. Textos seguem a skill `textos-trilingues`.

## Processo (o que mais pesou na aprovação)

O David decide; o trabalho é propor bem e executar só o escolhido.

1. **Analise e proponha em tabela, sem alterar nada.** Colunas: nº, prioridade, problema visto, sugestão, "depende de você?". Ele responde escolhendo ("Blocos 1 e 2", "as 4 de prioridade alta", "pode fazer 5, 6, 8 e 10"). Faça só o escolhido.
2. **Meça antes e depois** com números: altura da seção em px, largura do mapa, contraste. Números convencem mais que adjetivos e mostram efeitos colaterais (ex.: aumentar o mapa quebrou o `h1` em 4 linhas).
3. **Confira os dois temas, desktop e celular (375 px)** e os três idiomas quando houver texto. Diga claramente o que não foi conferido.
4. **Uma rodada = uma branch e uma PR.** Pergunte "commit e PR?" e, depois do preview, "merge?". Siga o fluxo de cada repositório (no pycloud-site: issue → branch → PR → preview → merge, e `node build.js` depois de editar o `index.html`).
5. **Se o "sim" for ambíguo, diga o que você entendeu** e como desfazer, em vez de fazer tudo.
6. **Não invente dado.** Latência, preço, SLA, e-mail, cliente ou certificação que o David não deu ficam como `[confirmar]`.

## Regras de design que não mudam sem pedir

- **Fundos fora dos extremos.** Escuro grafite `#1A1816` (padrão da marca), claro cinza quente `#E9E6E1`, cartões um degrau acima. Preto puro e branco puro foram rejeitados ("muito escuro", "muito claro").
- **Laranja tem papéis:** `--orange` para fundo de botão e marcas; `--orange-text` para texto e links (contraste AA); `--orange-display` só em texto grande. No claro, um só laranja para título e números grandes. Cor nova vira variável nos dois temas.
- **Tipografia:** títulos em Archivo larga (stretch 110–125%, peso 720–800, letter-spacing negativo); texto em IBM Plex Sans 16 px. **A IBM Plex Mono foi rejeitada duas vezes** ("essa fonte não me agrada"); o papel "mono" (rótulos, dados, legendas) usa a Plex Sans. Rótulo em maiúsculas com tracking leve (`.06em`); tracking largo (`.14em`) foi achado "estranho". Nada abaixo de 12 px.
- **Sem sombras.** Estrutura com linhas de 1 px; raio 6 px em cartões, 10 px em botões, pílula nos seletores.
- **Ícones só onde identificam** produto ou destino (traço 1,6 px, 24 × 24, `currentColor`, sprite SVG). O mesmo destino usa sempre o mesmo ícone. Menu do desktop só com texto. O David quer navegação intuitiva, mas "não quero que vire bagunça".
- **Status:** verde = ativo/online (pontos pulsantes em verde); contorno laranja = em breve.
- **O mapa do Paraguai é a assinatura.** PYCloud: mapa cartográfico com DCs e pacotes correndo nas rotas reais (principal PY-02 + PY-07 contínua; alternativa PY-03 tracejada). Grupo PTG: mapa com o ñandutí, suavizado, sem moldura. Animação pausa fora da tela, para com `prefers-reduced-motion`, e no celular rótulos de rota viram legenda.
- **Mostrar em vez de descrever:** demos vivas (painel White Label com o nome digitado), números grandes em âmbar, faixa de fatos.
- **Acessibilidade de base:** foco visível laranja, toque de 44 px até 960 px, gutter de 16 px, sem rolagem horizontal, contraste AA no texto pequeno.

## Adaptando para outra peça do grupo

Comece pelos tokens e componentes do site PYCloud e mude só o que a peça exige. Foi assim que o PY Console (painel) e o site do PTG ficaram coerentes:
- **Painel/sistema:** mesmas cores, botões e pílulas; tabelas com o cabeçalho da tabela de planos; estados vazios com caixa tracejada; ações principais fixas no topo.
- **Site institucional do grupo:** mesmos tokens; cartões das divisões separados, com ícone no traço PYCloud e hover que acende a caixa do ícone em laranja; símbolo próprio desenhado para tamanho pequeno quando o logo não funciona miniaturizado.
- **Marca nova (ex.: Solustic):** mantenha a estrutura (tipografia, linhas, raios, processo) e pergunte ao David antes de trocar a cor principal.

## Ao entregar

Feche com: o que mudou (com números de antes/depois), o que foi conferido e o que não foi, links (preview, PR, site) e a próxima pergunta ao David (commit/PR, merge ou próxima rodada).
