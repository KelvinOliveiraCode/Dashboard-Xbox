# Dashboard-Xbox — Dashboard de vendas do Xbox Game Pass em Excel

![Excel](https://img.shields.io/badge/Excel-217346?style=flat-square&logo=microsoftexcel&logoColor=white)
![XLSX](https://img.shields.io/badge/.xlsx-workbook-1D6F42?style=flat-square)
![SUMIFS](https://img.shields.io/badge/agrega%C3%A7%C3%A3o-SUMIFS-107C41?style=flat-square)
![Zero deps](https://img.shields.io/badge/depend%C3%AAncias-0-2EA44F?style=flat-square)

Dashboard de vendas executivo em **Microsoft Excel** modelando a operação comercial do **Xbox Game Pass** — planos Core, Standard e Ultimate, add-ons e ciclos de faturamento. Arquitetura de pastas de trabalho em 5 abas com separação rígida entre parâmetros, base transacional, camada de cálculo (`SUMIFS`) e apresentação: editar uma célula amarela recalcula base, KPIs e os 6 gráficos executivos — simulação de cenários sem tocar em fórmula.

---

## 🇧🇷 Português

### Arquitetura do workbook

| Aba | Função |
|-----|--------|
| **Parâmetros** | Única aba editável. Células em amarelo: preços por plano, metas, descontos de campanha, CAC e câmbio USD/BRL. |
| **Base de Dados** | Transações demo/artificiais. As colunas de Receita, Custo e Lucro são fórmulas que puxam os preços da aba Parâmetros — a base nunca guarda valores estáticos. |
| **Cálculos** | Camada de agregação via `SUMIFS` por Plano, Região, Ciclo de Faturamento, Add-on, Novos/Renovação e Evolução Mensal. |
| **Dashboard** | Cartões de KPI + 6 gráficos executivos que reagem aos Parâmetros. |
| **Instruções** | Guia de uso embutido. |

### KPIs

- **Receita Total (R$)** · **Assinantes (un.)** · **Lucro Total (R$)**
- **ARPU (R$)** · **Ticket Médio (R$)** · **Margem de Lucro**
- **% de Meta Atingida** — Receita, Assinantes e Câmbio USD

### Visualizações

1. Receita por Plano
2. Receita por Região
3. Receita por Ciclo de Faturamento
4. Receita por Add-on (EA Play, Minecraft Pass, Call of Duty Pass)
5. Novos vs. Renovação
6. Evolução Mensal da Receita

### Como usar

1. Abra `Dashboard_Xbox_Professional.xlsx` no Microsoft Excel.
2. Na aba **Parâmetros**, edite as células em **amarelo** (preços, metas, descontos, CAC, câmbio).
3. Base, KPIs e gráficos recalculam automaticamente.
4. Para simular cenários (ex.: preço do Ultimate +10%), altere os amarelos e observe o impacto.

> As fórmulas dependem do motor de cálculo do Excel — recomenda-se abrir no Excel, não em editores sem suporte a fórmulas nativas.

### Decisões de modelagem

- **Fonte única de verdade para preços**: a Base não guarda valores — puxa tudo da Parâmetros via fórmulas, então cenários recalculam em cascata;
- **Camada de cálculo separada da apresentação**: o Dashboard só lê agregações da aba Cálculos — mesmo princípio de separation of concerns de um BI;
- **`SUMIFS` como motor de agregação**: soma condicional multi-critério nativa, sem VBA e sem dependência externa.

### Autor

**Kelvin Oliveira** — [GitHub](https://github.com/KelvinOliveiraCode) · [LinkedIn](https://www.linkedin.com/in/kelvin-oliveira-code/)

---

## 🇺🇸 English

An executive sales dashboard in **Microsoft Excel** modeling the commercial operation of **Xbox Game Pass** — Core, Standard and Ultimate plans, add-ons and billing cycles. The workbook is organized in 5 sheets with strict separation between parameters, transactional base, calculation layer (`SUMIFS`) and presentation: edit one yellow cell and the base, KPIs and 6 executive charts all recalculate — scenario simulation without touching a single formula.

### Workbook architecture

| Sheet | Role |
|-------|------|
| **Parâmetros** | The only editable sheet. Yellow cells: plan prices, targets, campaign discounts, CAC and USD/BRL exchange rate. |
| **Base de Dados** | Demo transactions. Revenue, Cost and Profit are formulas pulling prices from Parâmetros — the base never holds static values. |
| **Cálculos** | Aggregation layer via `SUMIFS` by Plan, Region, Billing Cycle, Add-on, New/Renewal and Monthly Evolution. |
| **Dashboard** | KPI cards + 6 executive charts reacting to parameters. |
| **Instruções** | Embedded user guide. |

### KPIs

Total Revenue · Subscribers · Total Profit · ARPU · Average Ticket · Profit Margin · % of Target Achieved (Revenue, Subscribers, USD rate)

### Modeling decisions

- **Single source of truth for prices**: the base pulls everything from Parâmetros via formulas, so scenarios recalculate in cascade;
- **Calculation layer separated from presentation**: the Dashboard only reads aggregations — the same separation of concerns as a BI tool;
- **`SUMIFS` as the aggregation engine**: native multi-criteria conditional sum, no VBA, no external dependencies.

### How to use

Open `Dashboard_Xbox_Professional.xlsx` in Excel, edit the yellow cells in **Parâmetros**, and watch the whole dashboard recalculate. Requires a full Excel engine (native formula support).

### Author

**Kelvin Oliveira** — [GitHub](https://github.com/KelvinOliveiraCode) · [LinkedIn](https://www.linkedin.com/in/kelvin-oliveira-code/)
