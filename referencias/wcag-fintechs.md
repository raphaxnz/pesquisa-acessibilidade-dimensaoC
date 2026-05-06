# WCAG 2.1 Aplicada ao Setor Financeiro (Fintechs)

> **Fonte:** Legislação de Acessibilidade em Fintechs (DAD 2026)  
> **Base normativa:** WCAG 2.1, LBI Art. 63, Resolução BCB nº 155/2021

---

## Por que Fintechs têm obrigações extras?

Em Fintechs, a acessibilidade não é só inclusão — é **requisito de conformidade regulatória** com múltiplas camadas:

1. **LBI (Lei 13.146/2015)** — Art. 63: obriga acessibilidade em todos os sites e plataformas
2. **CDC (Lei 8.078/1990)** — produto inacessível = serviço defeituoso
3. **Resolução BCB nº 155/2021** — regulação específica do Banco Central

---

## Os 4 Princípios WCAG Aplicados a Pagamentos

### 1. Compreensível (Understandable) — O mais crítico em Fintechs

**Por quê?** Trata da prevenção de erros financeiros — área de maior risco jurídico.

| Critério | Nível | Aplicação Prática em Fintechs |
|----------|-------|-------------------------------|
| **3.3.4** — Prevenção de Erros (Financeiros) | AA | Telas de Pix e boleto devem permitir: (1) reverter a transação, (2) verificar dados antes de finalizar, ou (3) confirmar antes de submeter. A "Revisão de Pagamento" não é UX — é requisito legal. |
| **3.3.2** — Rótulos ou Instruções | A | Campos de cartão e CVV devem ter `<label>` visíveis e persistentes. Usar só `placeholder` é violação — ele some quando o usuário digita, prejudicando pessoas com déficits cognitivos. |
| **1.3.5** — Identificar a Finalidade do Input | AA | Use `autocomplete` correto: `cc-number`, `cc-csc`, `cc-exp`. Reduz esforço motor e cognitivo do usuário. |

```html
<!-- ✅ Correto -->
<label for="card-number">Número do cartão</label>
<input id="card-number" type="text" autocomplete="cc-number" />

<!-- ❌ Errado — placeholder some quando o usuário digita -->
<input type="text" placeholder="Número do cartão" />
```

---

### 2. Operável (Operable)

| Critério | Nível | Aplicação Prática |
|----------|-------|-------------------|
| **2.1.1** — Teclado | A | Todo o fluxo de pagamento (selecionar parcelas, confirmar Pix) deve ser navegável via `Tab` e `Enter/Space`. `div` customizado sem tratamento de teclado = inacessível. |
| **2.2.1** — Ajuste de Tempo | A | Sessões com timeout de segurança devem exibir modal de aviso antes de expirar, permitindo ao usuário solicitar mais tempo. |

```javascript
// ✅ Componente de seletor de parcelas acessível por teclado
<select aria-label="Número de parcelas">
  <option value="1">1x sem juros</option>
  <option value="3">3x de R$ 100,00</option>
</select>

// ❌ Div customizado sem suporte a teclado (violação 2.1.1)
<div class="parcelas-custom" onClick={handleSelect}>...</div>
```

---

### 3. Perceptível (Perceivable)

| Critério | Nível | Aplicação Prática |
|----------|-------|-------------------|
| **1.4.3** — Contraste Mínimo | AA | Texto de valores (`R$ 1.500,00`) e letras miúdas de taxas devem ter contraste mínimo de **4,5:1**. Cores apagadas em taxas podem ser juridicamente interpretadas como má-fé (Art. 6º do CDC). |
| **1.4.11** — Contraste de Conteúdo Não Textual | AA | Focus rings de campos e botões de pagamento: mínimo **3:1** contra o fundo. Usuário que não vê o foco não consegue pagar. |

---

### 4. Robusto (Robust)

| Critério | Nível | Aplicação Prática |
|----------|-------|-------------------|
| **4.1.2** — Nome, Função, Valor | A | Switches ("Salvar cartão") devem ter `role="switch"` e `aria-checked="true/false"`. Leitor de tela não pode anunciar só "Botão" — precisa dizer "Salvar cartão, ativado". |

```html
<!-- ✅ Switch acessível -->
<button role="switch" aria-checked="false" aria-label="Salvar cartão para próxima compra">
  <!-- visual do toggle aqui -->
</button>
```

---

## Implicações Legais do Descumprimento

- **Inquérito Civil** pelo Ministério Público (LBI)
- **Multas diárias (astreintes)** por descumprimento de obrigação de fazer
- **Dano Moral Coletivo** — não precisa de vítima individual para processar
- **Inversão do ônus da prova** (CDC) — empresa precisa provar que era acessível
- **Sanções administrativas do BACEN** — pode suspender atividades da Fintech

---

## Fontes

- W3C. *WCAG 2.1 — Success Criterion 3.3.4 (Level AA)*. https://www.w3.org/TR/WCAG21/#error-prevention-legal-financial-data
- W3C. *WCAG 2.1 — Success Criterion 2.1.1 (Level A)*. https://www.w3.org/TR/WCAG21/#keyboard
- Banco Central do Brasil. *Resolução BCB nº 155/2021*. https://www.bcb.gov.br/
- Presidência da República. *Lei nº 8.078/1990 — CDC, Arts. 6º e 39*. https://www.planalto.gov.br/ccivil_03/leis/l8078compilado.htm
- Pesquisa interna. *Legislação de Acessibilidade em Fintechs*. DAD 2026.
