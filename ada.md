# ADA — Americans with Disabilities Act (EUA)

> **Fonte:** ADA.md (DAD 2026)  
> **Fontes externas:** ADA Site Compliance (2023 Report); Saul Ewing LLP; UsableNet 2024 ADA Report

---

## O que é

A ADA é um **conjunto de leis federais dos Estados Unidos** que proíbe a discriminação contra pessoas com deficiência nas atividades do dia a dia — da mesma forma que outras leis americanas proíbem discriminação por raça, cor, sexo, nacionalidade, idade ou religião.

Ela garante que pessoas com deficiência tenham as **mesmas oportunidades** que todos nas áreas de:

- Emprego
- Compra de bens e serviços
- Participação em programas estatais e governamentais

---

## Quem ela protege

| Grupo | Descrição |
|-------|-----------|
| **PcD direta** | Pessoas com deficiência física ou mental que afete ao menos uma atividade diária |
| **Histórico de deficiência** | Pessoas que tiveram alguma condição no passado (ex: doenças que causaram limitação temporária) |
| **Percepção social** | Pessoas percebidas pelos outros como tendo deficiência — como alguém com cicatrizes visíveis de queimadura |

---

## Aplicação ao Ambiente Digital

Os tribunais americanos utilizam a **WCAG** como base técnica para julgar processos de acessibilidade digital sob a ADA. Não há um padrão legal específico definido em lei — a WCAG preenche esse vazio na prática jurídica.

---

## Processos por Acessibilidade Digital — EUA 2023

Em 2023, foram abertos **4.605 processos** por acessibilidade digital nos EUA (federal + estadual).

### Distribuição

| Esfera | Processos |
|--------|-----------|
| Tribunais federais | 3.086 |
| Tribunais estaduais | 1.519 |
| **Total** | **4.605** |

### O que revelam os dados

- **97%** dos processos tiveram como alvo **sites** — não apps móveis ou softwares SaaS
- **77%+** das empresas processadas tinham faturamento anual **inferior a US$ 25 milhões** — o risco legal não se limita a grandes corporações
- **+62%** de aumento em processos contra empresas que usavam **frameworks prontos de acessibilidade** (*overlay widgets*) — os processos alegam que essas ferramentas criam barreiras adicionais em vez de resolver problemas de código

---

## Principais Falhas Técnicas por Trás dos Processos

Todas as falhas abaixo são violações diretas da WCAG — e é por isso que são facilmente identificadas por ferramentas de auditoria, tornando-se alvos rápidos para escritórios especializados em ADA.

| Falha | Critério WCAG Relacionado | Impacto |
|-------|--------------------------|---------|
| **Incompatibilidade com leitores de tela** | 4.1.2 — Nome, Função, Valor | Sites sem código estruturado impedem que NVDA ou JAWS interpretem o conteúdo para pessoas cegas |
| **Falta de texto alternativo** | 1.1.1 — Conteúdo Não Textual | Ausência de `alt` em imagens e botões — usuário cego não sabe o que o elemento representa |
| **Falhas de navegação por teclado** | 2.1.1 — Teclado | Foco some ou fica preso em menus; sites projetados só para mouse excluem PcD motoras e visuais |
| **Contraste insuficiente** | 1.4.3 — Contraste Mínimo | Texto claro sobre fundo claro — ilegível para baixa visão e daltonismo |
| **Formulários sem rótulos** | 3.3.2 — Rótulos ou Instruções | Leitor de tela só diz "campo de texto" sem explicar o que deve ser digitado |
| **Uso ineficaz de widgets de acessibilidade** | — | +62% em processos em 2023 contra sobreposições automáticas que criam novas barreiras |
| **Vídeos sem legendas ou audiodescrição** | 1.2.2 / 1.2.5 | Conteúdo audiovisual sem suporte para surdos ou cegos |

---

## Paralelo com o Brasil

| Aspecto | ADA (EUA) | LBI (Brasil) |
|---------|-----------|--------------|
| Base legal de acessibilidade digital | ADA + orientação DoJ | Lei 13.146/2015, Art. 63 |
| Padrão técnico de referência | WCAG 2.1 (aplicada pelos tribunais) | WCAG 2.1 (referenciada na lei) |
| Quem pode processar | Qualquer cidadão / escritórios especializados | Ministério Público, cidadãos individualmente |
| Risco para pequenas empresas | Sim — 77% dos processados faturam < US$ 25M | Sim — abrange qualquer empresa com representação no Brasil |

A LBI brasileira foi **diretamente influenciada** pela Convenção da ONU sobre Direitos das PcD (2006), ratificada pelo Brasil em 2008. A WCAG 2.1, nível AA, é o parâmetro técnico tanto para a LBI quanto para a ADA — o que alinha tecnicamente Brasil e EUA no mesmo padrão.

---

## Caso Robles v. Domino's Pizza (EUA)

Um dos casos mais citados no direito de acessibilidade digital.

**Guillermo Robles**, que é cego, processou a Domino's Pizza porque o site e o app da empresa não eram compatíveis com seu leitor de tela, impedindo-o de fazer pedidos online.

| Evento | Data |
|--------|------|
| Processo inicial | 2016 |
| 9º Circuito decide que a ADA se aplica a sites e apps | Janeiro de 2019 |
| Suprema Corte recusa revisar o caso (certiorari negado) | Outubro de 2019 |
| Confirmação da aplicação da ADA ao digital em instância definitiva | 2019 |

**Impacto:** O caso estabeleceu que empresas com presença física nos EUA não podem ter sites ou apps inacessíveis. É o precedente mais citado em disputas ADA de acessibilidade digital. Após o caso ir e vir entre tribunais, Domino's e Robles chegaram a um acordo (settlement) em 2022.

---

## Diretiva Europeia de Acessibilidade Web e EAA

### Diretiva (UE) 2016/2102 — Setor Público

Obriga sites e apps de **órgãos públicos** europeus a atenderem a WCAG 2.1 nível AA.

| Prazo | Aplicação |
|-------|-----------|
| Dezembro de 2016 | Diretiva entra em vigor |
| 23 de setembro de 2019 | Sites novos do setor público |
| 23 de setembro de 2020 | Sites existentes do setor público |
| 23 de junho de 2021 | Aplicativos móveis do setor público |

### European Accessibility Act — Diretiva (UE) 2019/882 — Setor Privado

Publicada em junho de 2019, a EAA estende as obrigações de acessibilidade para o **setor privado** — incluindo bancos, e-commerce e serviços de transporte.

**Prazo de aplicação (enforcement): 28 de junho de 2025** — o que torna este um marco ativo no momento desta pesquisa.

---

## Indenizações ADA
A ADA não é uma lei de indenização, ela é uma lei de direitos civis. Então temos duas distinções para que aconteçam as indenizações:

**1. Multas civis (civil penalties)** — cobradas pelo governo federal via DOJ.
O Departamento de Justiça pode impor multas civis de até US$ 75.000 para a primeira violação e até US$ 150.000 para violações subsequentes.

**2. Indenizações em processos privados** — movidos por indivíduos
Aqui está o detalhe crucial: sob o Título III da ADA, as multas pesadas são apenas parte das penalidades por não conformidade. Em processos privados, a ADA em si não prevê indenização por danos financeiros, o autor geralmente só pode pedir medidas corretivas (o site ser consertado). Os valores altos que você vê em notícias vêm de acordos extrajudiciais ou de leis estaduais combinadas.

---

## Fontes

- ADA Site Compliance. *2023 ADA Web Accessibility Lawsuit Statistics — Full Report*. 2023. https://adasitecompliance.com/2023-ada-web-accessibility-lawsuit-statistics-full-report/
- Saul Ewing LLP. *ADA Website Accessibility Risk*. https://www.saul.com/insights/blog/ada-website-accessibility-risk
- UsableNet. *2024 ADA Report — Digital Accessibility Lawsuits*. 2024. https://3280432.fs1.hubspotusercontent-na1.net/hubfs/3280432/2024-ADA-Report-Digital-Accessibility-Lawsuits.pdf
- Comissão Europeia. *Diretiva (UE) 2016/2102 — Web Accessibility Directive*. https://eur-lex.europa.eu/legal-content/PT/TXT/?uri=CELEX%3A32016L2102
- Comissão Europeia. *Diretiva (UE) 2019/882 — European Accessibility Act*. https://ec.europa.eu/social/main.jsp?catId=1202
- Pesquisa interna (DAD 2026). *ADA — Americans with Disabilities Act*.
