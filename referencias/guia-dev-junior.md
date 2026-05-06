# Guia de Proteção Legal para o Desenvolvedor Júnior

> **Contexto:** Como um dev júnior no PicPay (ou qualquer Fintech) deveria se proteger legalmente em relação à LBI e WCAG?  
> **Fonte:** Legislação de Acessibilidade em Fintechs (DAD 2026)

---

## A Realidade do Dev Júnior

Você está numa hierarquia — mas o código que você escreve pode impactar milhares de usuários com deficiência. A lei não distingue "júnior" de "sênior" na hora de apurar responsabilidade técnica. O que te protege é **documentação** e **seguir padrões reconhecidos**.

---

## As 3 Proteções Principais

### 1. Dever de Informação e Alerta (Blindagem contra Negligência)

Se você identificar uma violação de LBI/WCAG, **formalize o risco antes de subir o código**.

- Registre no Jira/ticket
- Documente no PR (Pull Request)
- Se o PO decidir subir assim mesmo, **seu alerta documentado é sua proteção** — você não pode ser responsabilizado por uma decisão que não foi sua

```markdown
<!-- Template de comentário em PR -->
⚠️ **A11y Risk Identificado**
- Critério violado: WCAG 2.1 — 4.1.2 (Nível A) / LBI Art. 63
- Componente: `<div class="btn-pagar">` sem `role` e sem suporte a teclado
- Risco: inacessível para usuários de NVDA/VoiceOver e navegação por teclado
- Solução sugerida: substituir por `<button>` semântico
- Status: aguardando decisão do PO
```

### 2. Aderência à WCAG 2.1 (Nível AA) — Sua "Bíblia" Técnica

Seguir um padrão reconhecido **globalmente** demonstra boa-fé e diligência técnica em caso de perícia judicial.

Configure no repositório:

```bash
# eslint-plugin-jsx-a11y para projetos React
npm install --save-dev eslint-plugin-jsx-a11y
```

```json
// .eslintrc.json
{
  "plugins": ["jsx-a11y"],
  "extends": ["plugin:jsx-a11y/recommended"]
}
```

Inclua no *Definition of Done* de toda task:
> ✅ "Acessível conforme WCAG 2.1 AA"

### 3. Documentação de Impedimentos Estruturais

Se o Design System ou biblioteca de componentes da empresa for inacessível, **registre isso**. Você não pode ser responsabilizado por falha estrutural da qual é apenas o implementador.

```markdown
<!-- Exemplo no ticket/Jira -->
🚧 Impedimento de A11y:
O componente `Dropdown` do nosso Design System não implementa
`aria-expanded` nem suporte a teclado (violação WCAG 2.1.1 e 4.1.2).
Enquanto não for corrigido pela equipe de plataforma, este componente
não atinge conformidade WCAG AA.
Registrado em: [link do ticket de design system]
```

---

## Checklist de Conformidade — O que Guardar

| Evidência | Por quê guardar |
|-----------|-----------------|
| Relatórios de Lighthouse/Axe por release | Prova de esforço de conformidade em cada versão |
| Matriz de testes com NVDA, VoiceOver, TalkBack | Demonstra que testou com tecnologias assistivas reais |
| Comentários técnicos nos PRs | Explicam decisões de acessibilidade (ex: por que `aria-live` foi usado) |
| Tickets com alertas de risco documentados | Prova que você identificou e reportou antes de subir |
| Certificados de auditoria interna | Registros de conformidade ou planos de remediação |

---

## Ferramentas de Validação (Gratuitas)

| Ferramenta | O que faz | Como usar |
|------------|-----------|-----------|
| **Lighthouse** | Score de acessibilidade geral | DevTools do Chrome → aba Lighthouse |
| **Axe DevTools** | Identifica violações WCAG específicas | Extensão para Chrome/Firefox |
| **NVDA** | Leitor de tela (Windows) — simula experiência real | https://www.nvaccess.org/ |
| **VoiceOver** | Leitor de tela nativo (macOS/iOS) | Ativar em Ajustes → Acessibilidade |
| **ASES** | Verificador oficial do e-MAG | https://ases.softwarepublico.gov.br/ |

---

## Por que isso é Ética, não só Burocracia

> "Se o código impede um deficiente visual de gerir o próprio dinheiro, a empresa está violando o princípio da **dignidade da pessoa humana**. Documentar o trabalho não é apenas burocracia — é ética profissional e segurança jurídica."  
> — *Legislação de Acessibilidade em Fintechs, DAD 2026*

Em uma Fintech, acessibilidade é um pilar de **ESG** (Environmental, Social and Governance). Não é opcional — é o que separa uma empresa que respeita seus usuários de uma que os exclui.

---

## Fontes

- Pesquisa interna. *Legislação de Acessibilidade em Fintechs — Guia de Proteção Profissional para Desenvolvedores*. DAD 2026.
- W3C. *Accessibility Conformance Testing (ACT)*. https://www.w3.org/WAI/standards-guidelines/act/
- Código Civil (Brasil). Arts. 186 e 927 — Responsabilidade Civil. https://www.planalto.gov.br/ccivil_03/leis/2002/l10406compilada.htm
