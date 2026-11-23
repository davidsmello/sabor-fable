# Linguagem visual "ficha técnica cartográfica"

Fonte de verdade: `PYCloud/pycloud-site/index.html` (bloco `<style>` e sprite SVG no início do `body`). Se este arquivo e o código divergirem, **vale o código**: releia o `<style>` antes de copiar valores.

## Índice
1. Conceito
2. Tokens de cor (dois temas)
3. Tipografia
4. Grid, espaçamento e superfícies
5. Componentes
6. Ícones
7. Mapa e movimento
8. Acessibilidade embutida

## 1. Conceito

A página lê como uma ficha técnica de engenharia desenhada sobre um mapa: dados reais (latência, sites, planos, preços) em destaque, linhas finas de 1 px separando tudo, pouco ornamento. O mapa do Paraguai com os Edge DCs abre a página e é a "assinatura" da marca. Credibilidade técnica vem de números concretos, não de adjetivos.

O que essa linguagem evita: gradientes chamativos, sombras grandes, cartões flutuando com cantos muito redondos, ilustrações genéricas de "nuvem", ícones decorativos em todo lugar, fundos preto puro ou branco puro.

## 2. Tokens de cor

Escuro é o tema padrão da marca. Claro é alternativo. Os fundos ficam **fora dos extremos** (grafite e cinza quente): o David achou o claro claro demais e o escuro escuro demais quando eram quase branco e quase preto (13 nov 2026).

| Token | Escuro | Claro | Uso |
|---|---|---|---|
| `--bg` | `#1A1816` | `#E9E6E1` | fundo da página |
| `--surface` | `#23201D` | `#FBFAF8` | cartões, faixas (`section.band`), um degrau acima do fundo |
| `--surface-2` | `#2C2824` | `#F0EDE8` | caixas internas (ex.: ícone de produto) |
| `--line` | `#413A33` | `#D5CFC7` | todas as linhas de 1 px |
| `--ink` | `#F3EFE9` | `#1C1814` | texto principal |
| `--muted` | `#B8B0A6` | `#585048` | texto secundário, legendas |
| `--orange` | `#F2822E` | (igual) | fundo de botão primário, marcas do mapa |
| `--orange-hover` | `#FF9C4E` | (igual) | hover do primário |
| `--orange-text` | `#F2822E` | `#984508` | laranja **em texto** e links (contraste AA) |
| `--orange-display` | = orange-text | `#CC5A0A` | laranja só em texto grande (24 px+) |
| `--amber` / `--amber-display` | `#FFC98A` | `#8F4F0B` / `#CC5A0A` | números grandes, rio no mapa |
| `--orange-soft` | `#3B2513` | `#F8E2CF` | fundos de destaque suaves |
| `--on-orange` | `#170D04` | (igual) | texto sobre laranja |
| `--ok` / `--err` | `#5CB884` / `#FF8A7A` | `#1E6A40` / `#B3261E` | status ativo / erro |

Regras:
- Laranja em texto usa sempre `--orange-text`, nunca `--orange` (no claro, `--orange` falha em contraste).
- No tema claro, destaque da abertura e números grandes usam um só laranja (`--orange-display` = `--amber-display` = `#CC5A0A`).
- Logo: nuvem em `#F2822E`/`#C4550F` no escuro e `#EE7419`/`#A9420A` no claro; o "PY" usa a cor do texto do tema. Arquivos em `PYCloud/marca/`.
- O site do grupo PTG usa os mesmos tokens de fundo/superfície/texto. Uma tela nova do grupo parte desta tabela.
- Toda cor nova vira variável nos **dois** temas. Nada de hex solto no meio do CSS.

## 3. Tipografia

- `--display`: **Archivo** (larga, peso alto) para títulos. Use `font-stretch` entre 110% e 125% e `letter-spacing` negativo.
- `--body`: **IBM Plex Sans** para texto.
- `--mono`: também IBM Plex Sans (antes era IBM Plex Mono; trocada a pedido do David em 13 nov 2026). A classe e o papel "mono" continuam: rótulos, legendas, dados técnicos, em 12–13 px, às vezes em maiúsculas com `letter-spacing: .06em`.
- Fontes locais em `fonts/` (licença OFL). Corpo `16px/1.6`, `font-variant-numeric: tabular-nums` na página toda (números alinhados).

Escala usada:
- `h1` da abertura: `clamp(38px, 6.6vw, 84px)`, peso 800, stretch 125%, `letter-spacing -.035em`, `line-height .96`. A segunda linha (`em`) vai em laranja display, em bloco.
- `h2`: `clamp(32px, 5.2vw, 60px)`, peso 780, stretch 118%, `max-width 17ch`, `text-wrap: balance`.
- `h2` de seções de apoio (Preços, FAQ, Comece aqui): menor, `clamp(28px, 3.6vw, 42px)`, para variar o ritmo.
- `h3`: 22 px, peso 720.
- `.lede`: 19 px, `--muted`, `max-width 58ch`.
- Menor texto do site: 12 px. Não desça disso.

## 4. Grid, espaçamento e superfícies

- Largura máxima `--max: 1180px`; gutter lateral 16 px (com `safe-area-inset`). Cabeçalho `--hdr: 60px`, fixo, com fundo do tema a 88% e `backdrop-filter: blur(12px)`.
- Seções: `padding-block: clamp(64px, 9vw, 120px)`, separadas por `border-bottom: 1px solid var(--line)`. Seções alternadas podem usar `section.band` (fundo `--surface`).
- Grids assimétricos em frações (`7.5fr 4.5fr` na abertura, `5fr 6fr` em produto, `6fr 5fr` em parceiros), sempre `minmax(0, …)`.
- Grade de fatos: células separadas por 1 px de `--line` (técnica `gap: 1px` com fundo `--line`).
- Raio: 6 px em cartões e blocos, 10 px em botões, 4 px em inputs, 999 px em seletores pílula. Sem sombras.
- Fundo da abertura: grade de pontos (28 px) com máscara radial, sutil.

## 5. Componentes

- **Eyebrow** acima do título: 12 px mono, maiúsculas, laranja-texto, com um traço de 28 × 1 px antes.
- **Botões:** altura mínima 46 px, raio 10 px, peso 700. Primário em `--orange` com texto `--on-orange`. Secundário só com borda `--muted`, hover em laranja-texto. Seta `→` que anda 3 px no hover.
- **Faixa de números** (`.strip`): 4 colunas com divisórias de 1 px; número grande em Archivo 30 px âmbar, legenda mono 12 px.
- **Tabela comparativa** (`.cmp`): coluna da PYCloud em `--surface` com borda superior laranja de 2 px.
- **Produto em destaque** (`.feature`): nome grande, frase em laranja, lista com "ticks" desenhados em CSS (não ícones), linha de condições com número em âmbar.
- **Mock de painel** (White Label): mostra o produto funcionando em vez de descrever. Linhas mono com status verde.
- **Seletores** de idioma e tema: pílula segmentada, opção ativa em laranja.
- **Menu:** item da seção visível destacado com `aria-current` e sublinhado laranja de 2 px.
- **Listas longas recolhidas:** preços mostram 4 planos e "ver todos"; adicionais começam fechados com contador.

## 6. Ícones

- Um só conjunto SVG, traço 1,6 px, 24 × 24, `stroke: currentColor`, `fill: none`, definido uma vez num sprite e usado com `<use href="#i-…">`.
- Aparecem só onde **identificam** um produto ou destino: título dos três produtos (caixa `.pico` 48 × 48 com borda e fundo `--surface-2`), menu do celular, abas de contato.
- O mesmo destino usa sempre o mesmo ícone em todo lugar.
- No computador o menu do cabeçalho fica só com texto.
- Teste antes de pôr ícone: "isso ajuda a achar algo?" Se for enfeite, fica de fora. O David pediu ícones para a navegação ficar mais intuitiva, mas sem "virar bagunça".

## 7. Mapa e movimento

- Mapa SVG do Paraguai: país em `--surface` com contorno `--muted`, rio em âmbar, DCs ativos em `--ok` com anel pulsando, DCs futuros vazados em laranja.
- Pacotes de dados correm nas rotas com `offset-path`. Rota principal contínua, alternativa tracejada. Velocidades em variáveis (`--flow-a/b`, `--alt-a/b`).
- A animação pausa fora da tela e fica parada com `prefers-reduced-motion: reduce`.
- Rótulos do mapa em mono 11,5 px. Legenda abaixo, mono 12 px.
- Movimento só quando conta algo (dados trafegando). Transições de interface curtas: `.15s`–`.2s`.

## 8. Acessibilidade embutida

- `:focus-visible` com contorno de 2 px em laranja-texto.
- Link "pular para o conteúdo".
- Área de toque de 44 × 44 px até 960 px de largura.
- Contraste AA no texto nos dois temas (por isso existem `--orange-text` e `--orange-display`).
- Sem rolagem horizontal; layout testado em 375 px.
