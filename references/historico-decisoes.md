# Histórico de decisões (trabalhos com o Fable, 11–17 nov 2026)

Use para saber o que já foi aprovado ou rejeitado antes de propor algo. Citações são do David.

## 1. Site PYCloud, versão do Fable (12/11)

Briefing: "liberdade total de layout, tipografia, ritmo visual, hierarquia e microinterações. Não copie o layout atual. Mantenha o conteúdo e as regras de negócio." Sem inventar números, clientes ou certificações. ES padrão, PT, EN; escuro padrão e claro. Posicionamento: "Nube privada hecha en Paraguay" (nunca "primeira nuvem do Paraguai", nunca "brasileira"), foco em revendas.

O Fable entregou o conceito "ficha técnica cartográfica": mapa real do Paraguai abrindo a página, dados em destaque, demo ao vivo do White Label, sem sombras, divisórias de 1 px. **Adotado como oficial.**

Pedidos seguintes, atendidos:
- Animar o enlace Hernandarias–Asunción como tráfego: pacotes nos dois sentidos em ritmos levemente diferentes, brilho na chegada, pausa fora da tela, estático com reduced-motion.
- Rota alternativa Hernandarias → Troncal 4 → Katueté → Asunción, visualmente secundária (tracejada).
- Correção: a alternativa colava na principal e os rótulos se sobrepunham no celular. Solução: traçados pelas rodovias reais (principal PY-02 + PY-07, alternativa PY-03) e legenda no celular no lugar dos rótulos.
- Latências dadas pelo David (6, 4, 10 e 22 ms). Regras: números exatos, sem somar, sem "RTT"/"garantida", sem citar operadora, com nota "latência de referência, pode variar".

## 2. Refinamento do site PYCloud (13–17/11)

- "está muito claro no tema claro e muito escuro no tema escuro" → fundos saíram dos extremos: escuro `#0A0908` → `#1A1816`, cartões `#141210` → `#23201D`; claro `#F6F3EF` → `#E9E6E1`, cartões `#FFFFFF` → `#FBFAF8`. Texto pequeno do claro escurecido para contraste ≥ 4,5:1. **Aprovado.** (Esses fundos divergem do design system original; o site manda.)
- Laranja de título grande no claro mais vivo (`#984508` → `#CC5A0A`), só para texto grande. Depois o claro foi unificado num laranja a menos. **Aprovado** ("sim, pode fazer").
- Ícones: "acha possível inserir alguns ícones" nos produtos; "quero que a navegação fique mais intuitiva... mas também não quero que vire bagunça". Etiqueta = White Label, rack = Bare Metal, nuvem com cadeado = Nuvem Privada Virtual. Só em títulos de produto, menu do celular e abas de contato; desktop só texto. **Aprovado.**
- Fonte: "essa fonte não me agrada, por favor, substituir" (IBM Plex Mono, já criticada no Console) → papel mono passou para IBM Plex Sans. Depois: "espaçamento das letras está estranho" → tracking reduzido.
- "analise o design do site, pode sugerir melhorias, mas não as faça sem minha permissão" → tabela priorizada. Aprovou "as 4 de prioridade alta" (menu com seção ativa; preços recolhidos, seção de 1.870 → 1.132 px; rodapé completo; toque de 44 px) e depois "5, 6, 8 e 10" (mapa 369 → 416 px, porque 462 px quebrava o `h1`; um laranja a menos; títulos de apoio 60 → 42 px; mínimo de 12 px). Itens que dependiam de conteúdo dele ficaram pendentes.
- Retrabalho a evitar: fazer as duas opções quando o "sim" era ambíguo; conferir o tema escuro só no fim.

## 3. PY Console (11–16/11)

- "Quero utilizar o mesmo logotipo do PY Cloud... aqui no console." "Deixe o console no mesmo designer que o web site." → mesmos tokens, títulos largos, dados em "ficha", totais em âmbar, botões 10 px, pílulas, cartões 6 px sem sombra. **Aprovado** ("o protótipo oficial está aprovado").
- Vitrine de sistemas operacionais estilo marketplace, com logos (Simple Icons) na cor da marca ajustada ao tema; itens sem preço confirmado marcados `[confirmar]`.
- Pontos online pulsando "podem ser na cor verde" / "Verde também".
- "Ações rápidas precisa estar fixado no topo da página" → "Assim está bom."
- "Esse tipo de fonte não está agradando aos meus olhos... use a fonte que está em outras partes do sistema." "Trocar no site também."
- Perfis: Admin e Parceiro (cliente e parceiro numa visão só), com o mesmo visual.

## 4. Site do grupo PTG (16–17/11)

- "pode seguir o exemplo do site da PY Cloud. Analise e me sugira o que pode ser feito, só efetuar alterações após minha confirmação." → "Blocos 1 e 2" → "Aprovado, pode enviar."
- "Substitua pelo mesmo elemento que estamos usando no site da PY Cloud." "Seguir o mapa da PyCloud."
- Mapa do Paraguai com o ñandutí no espaço vazio; depois "suavizar o mapa... e animar esses enlaces" → sem fundo azul e sem moldura, brilho mais fraco, pontos de luz nos 23 enlaces em ritmos diferentes, pulso nos nós, parado com reduced-motion. Gerado por `tools/gerar-arte-animada.py`.
- "o mini logo no topo está estranho" → símbolo próprio para tamanho pequeno (contorno do Paraguai com enlaces saindo de Asunción), também favicon. Arte original intacta.
- Cartões das 6 divisões: de grade colada para cartões separados com ícone no traço PYCloud; hover acende a caixa do ícone em laranja.
- Correções de conteúdo: "Mantenha como troncal 4"; Hernandarias no lugar de Ciudad del Este; rodapé sem e-mail ("por agora o contato será via formulário").
