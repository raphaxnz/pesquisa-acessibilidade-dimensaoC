# Acessibilidade Digital — Dimensão C: Legislação Brasileira e Internacional

> **DAD 2026 · Aulas 17–19 · Instituto J&F — Escola de Tecnologia**  
> **Mesa:** [PENDENTE: Número da mesa]  
> **Integrantes:** [PENDENTE: Nomes dos integrantes]

---

## Sobre esta pesquisa

Investigação da **Dimensão C — Legislação**, com foco na pergunta central:  
*Quais leis obrigam a acessibilidade digital no Brasil e no mundo, e quais são as consequências reais para desenvolvedores que ignoram essas obrigações?*

---

## O que descobrimos (Principais Achados)

- **A LBI (Lei 13.146/2015) obriga acessibilidade digital em sites e plataformas de empresas com representação no Brasil** — incluindo Fintechs — sob pena de inquéritos civis, multas diárias (astreintes) e condenações por Dano Moral Coletivo (Art. 63 da LBI).  
  *Fonte: Lei nº 13.146/2015 — Art. 63; Legislação de Acessibilidade em Fintechs, 2026.*

- **Um produto digital inacessível é juridicamente classificado como "serviço defeituoso"** pelo Código de Defesa do Consumidor (CDC, Lei 8.078/1990, Arts. 6º e 39), o que pode gerar inversão do ônus da prova, multas do PROCON e indenizações individuais.  
  *Fonte: CDC — Art. 6º e 39; Legislação de Acessibilidade em Fintechs, 2026.*

- **O Banco Central regulamenta acessibilidade** por meio da Resolução BCB nº 155/2021, prevendo sanções administrativas, suspensão de atividades e impacto no rating de conformidade de Fintechs.  
  *Fonte: Resolução BCB nº 155/2021; Legislação de Acessibilidade em Fintechs, 2026.*

- **A LBI mudou o paradigma sobre deficiência no Brasil**: deixou de ser vista como "problema do indivíduo" para ser entendida como resultado da interação entre limitações da pessoa e barreiras impostas pela sociedade — o que transfere responsabilidade de inclusão para empresas e Estado.  
  *Fonte: Pesquisa sobre LBI — Lei Brasileira de Inclusão, 2026.*

- **O e-MAG (Modelo de Acessibilidade em Governo Eletrônico) é o padrão nacional de acessibilidade digital** para portais governamentais, baseado na WCAG internacional e verificável pelo software ASES.  
  *Fonte: e-MAG — Modelo de Acessibilidade em Governo Eletrônico, 2026.*

---

## Legislação — Marco Legal e Linha do Tempo

> Veja o infográfico completo em [`infografico/timeline.md`](./infografico/timeline.md).

### Brasil

| Ano | Marco Legal | Relevância para Acessibilidade Digital |
|-----|-------------|----------------------------------------|
| 1988 | Constituição Federal | Reconhece igualdade de direitos entre todos os cidadãos — base constitucional da inclusão |
| 2000 | Lei nº 10.098 — Lei de Acessibilidade | Estabelece normas gerais de acessibilidade para PcD |
| 2002 | Lei nº 10.436 — Lei de Libras | Reconhece a Língua Brasileira de Sinais como língua oficial |
| 2008 | Ratificação da Convenção da ONU sobre Direitos das PcD | Incorpora ao ordenamento brasileiro os padrões internacionais de direitos humanos para PcD |
| 2015 | **Lei nº 13.146 — LBI (Lei Brasileira de Inclusão)** | Art. 63 obriga acessibilidade em sites e plataformas; prevê penalidades civis e administrativas |
| 2018 | Decreto nº 9.406 | Regulamenta a LBI e estabelece cronograma de adaptação para o setor privado |
| 2021 | Resolução BCB nº 155 | Normatiza acessibilidade em canais digitais e plataformas de instituições financeiras |

### Internacional

| Ano | Marco Legal / País | Relevância |
|-----|--------------------|------------|
| 1990 | **ADA — Americans with Disabilities Act (EUA)** | Conjunto de leis federais que proíbem discriminação contra PcD em emprego, bens, serviços e programas governamentais — base legal para processos de acessibilidade digital nos EUA |
| 2016 | **Diretiva (UE) 2016/2102 — Web Accessibility Directive** | Obriga órgãos públicos europeus à conformidade WCAG 2.1 AA; prazos escalonados entre 2019 e 2021 |
| 2019 | **Robles v. Domino's Pizza — 9º Circuito (EUA)** | 9º Circuito: ADA se aplica a sites e apps. SCOTUS recusa revisão em out/2019. Precedente global de responsabilização digital |
| 2019 | **European Accessibility Act — Diretiva (UE) 2019/882** | Estende obrigações de acessibilidade ao setor privado europeu (bancos, e-commerce); enforcement a partir de 28 jun/2025 |
| 2023 | **4.605 processos ADA por acessibilidade digital (EUA)** | 3.086 federais + 1.519 estaduais; 97% contra sites; 77% das empresas processadas tinham faturamento < US$ 25 milhões |

> Detalhes de todos os marcos internacionais disponíveis em [`conteudo/ada.md`](./conteudo/ada.md).

---

## Principais Leis e Consequências

Veja detalhes em:
- [`conteudo/lbi.md`](./conteudo/lbi.md) — LBI completa com objetivos, impactos e penalidades
- [`conteudo/emag.md`](./conteudo/emag.md) — e-MAG: padrão nacional de acessibilidade
- [`conteudo/ada.md`](./conteudo/ada.md) — ADA e legislação internacional
- [`conteudo/wcag-fintechs.md`](./conteudo/wcag-fintechs.md) — WCAG 2.1 aplicada ao setor financeiro
- [`conteudo/guia-dev-junior.md`](./conteudo/guia-dev-junior.md) — Como um dev júnior se protege legalmente

---

## Como isso afeta o nosso trabalho como desenvolvedores

### 1. Formalize riscos de acessibilidade no ticket, sempre

Se você identificar uma funcionalidade ou *user story* que viola LBI/WCAG, documente o risco no Jira/ticket **antes** de subir o código. Se o PO decidir "subir assim mesmo", seu alerta documentado é sua blindagem contra negligência profissional.

```markdown
<!-- Exemplo de comentário em PR/ticket -->
⚠️ A11y Risk: Este componente usa `div` clicável sem `role` e `tabindex`.
Viola WCAG 2.1 — Critério 4.1.2 (Nível A) e, por extensão, o Art. 63 da LBI.
Risco: inacessível por teclado e leitores de tela (NVDA, VoiceOver).
Solução sugerida: substituir por `<button>` semântico.
```

### 2. Siga WCAG 2.1 Nível AA como padrão mínimo — documente isso

O padrão WCAG é reconhecido internacionalmente e demonstra **boa-fé e diligência técnica** em caso de perícia judicial. Configure linting de acessibilidade no repositório:

```bash
# Instalar eslint-plugin-jsx-a11y em projetos React
npm install --save-dev eslint-plugin-jsx-a11y

# Adicionar no .eslintrc
{
  "plugins": ["jsx-a11y"],
  "extends": ["plugin:jsx-a11y/recommended"]
}
```

### 3. Exporte relatórios de validadores automáticos a cada release

Ferramentas como Axe DevTools, Lighthouse e ARES Toolkit geram evidências de conformidade. Esses relatórios, salvos por versão, reduzem drasticamente o valor de eventuais multas em caso de processo judicial.

```bash
# Gerar relatório Lighthouse via CLI
npx lighthouse https://seu-site.com \
  --only-categories=accessibility \
  --output=json \
  --output-path=./evidencias/lighthouse-v1.0.0.json
```

---

## Referências

| # | Autor/Organização | Título | Ano | URL |
|---|-------------------|--------|-----|-----|
| 1 | Presidência da República (Brasil) | Lei nº 13.146 — Lei Brasileira de Inclusão da Pessoa com Deficiência | 2015 | https://www.planalto.gov.br/ccivil_03/_ato2015-2018/2015/lei/l13146.htm |
| 2 | Governo Federal (Brasil) | e-MAG — Modelo de Acessibilidade em Governo Eletrônico | — | https://emag.governoeletronico.gov.br/ |
| 3 | Banco Central do Brasil | Resolução BCB nº 155/2021 | 2021 | https://www.bcb.gov.br/estabilidadefinanceira/exibenormativo?tipo=Resolu%C3%A7%C3%A3o%20BCB&numero=155 |
| 4 | W3C | Web Content Accessibility Guidelines (WCAG) 2.1 — Tradução PT-BR | 2018 | https://www.w3.org/Translations/WCAG21-pt-BR/ |
| 5 | ONU | Convention on the Rights of Persons with Disabilities | 2006 | https://www.un.org/development/desa/disabilities/convention-on-the-rights-of-persons-with-disabilities.html |
| 6 | Presidência da República (Brasil) | Decreto nº 9.406/2018 | 2018 | https://www.planalto.gov.br/ccivil_03/_ato2015-2018/2018/decreto/d9406.htm |
| 7 | Presidência da República (Brasil) | Lei nº 8.078/1990 — Código de Defesa do Consumidor | 1990 | https://www.planalto.gov.br/ccivil_03/leis/l8078compilado.htm |
| 8 | Aluno (Pesquisa interna) | Pesquisa sobre LBI — Lei Brasileira de Inclusão | 2026 | — |
| 9 | Aluno (Pesquisa interna) | Legislação de Acessibilidade em Fintechs | 2026 | — |
| 10 | U.S. Department of Justice | Guidance on Web Accessibility and the ADA | 2022 | https://www.ada.gov/resources/web-guidance/ |
