# Dashboard Xbox — Game Pass (Dashboard de Vendas Executivo)

Dashboard de vendas profissional desenvolvido em **Excel**, criado como solução para o desafio de transformar dados brutos em informações visuais claras e úteis para análise de desempenho e tomada de decisão baseada em dados.

O modelo simula a operação comercial do **Xbox Game Pass** (planos Core, Standard e Ultimate, add-ons e ciclos de faturamento) e permite simular cenários alterando apenas os parâmetros de negócio.

## Arquivo

- `Dashboard_Xbox_Professional.xlsx` — arquivo principal com o dashboard concluído.

## Estrutura do Workbook

O arquivo é composto por 5 abas:

| Aba | Descrição |
|-----|-----------|
| **Parâmetros** | Única aba que o usuário edita. Células em amarelo contêm preços, metas, CAC, desconto de campanha e câmbio USD/BRL. Qualquer alteração recalcula toda a base e o dashboard. |
| **Base de Dados** | Registros de transações (dados demo/artificiais). As colunas de Receita, Custo e Lucro usam fórmulas que puxam os preços da aba Parâmetros. |
| **Cálculos** | Agregações via `SUMIFS` por Plano, Região, Ciclo de Faturamento, Add-on, Novos/Renovação e Evolução Mensal. Totalmente automática. |
| **Dashboard** | Cartões de KPI + 6 gráficos executivos que reagem automaticamente aos Parâmetros. |
| **Instruções** | Guia de uso do dashboard. |

## Principais Indicadores (KPIs)

- **Receita Total (R$)**
- **Assinantes (un.)**
- **Lucro Total (R$)**
- **ARPU (R$)**
- **Ticket Médio (R$)**
- **Margem de Lucro**
- **% de Meta Atingida** (Receita, Assinantes e Câmbio USD)

## Visualizações

Seis gráficos executivos alimentados pelas agregações da aba Cálculos:

1. Receita por Plano
2. Receita por Região
3. Receita por Ciclo de Faturamento
4. Receita por Add-on
5. Novos vs Renovação
6. Evolução Mensal da Receita

## Como Reproduzir / Utilizar

1. Abra o arquivo `Dashboard_Xbox_Professional.xlsx` no Microsoft Excel.
2. Vá na aba **Parâmetros** e edite as células em **amarelo** (preços, metas, descontos, CAC, câmbio, etc.).
3. O dashboard e os gráficos são recalculados automaticamente.
4. Use filtros/segmentações no Excel para explorar as visões analíticas.
5. Para simular cenários (ex.: aumentar o preço do Ultimate ou a meta de receita), basta alterar os valores amarelos e observar o impacto nos KPIs e gráficos.

> Observação: as fórmulas dependem de recursos do Excel para recálculo automático; recomenda-se abrir no Excel (não em editores que não suportam fórmulas nativas).

## Requisitos

- Microsoft Excel (versão com suporte a gráficos e `SUMIFS`).
- Nenhuma instalação adicional ou dependência externa.

## Fonte de Dados

Base de dados de transações contida na própria aba **Base de Dados** (dados artificiais/demo para fins de desafio), com campos como Data, Ciclo, Região, Canal, plano contratado e add-ons (EA Play, Minecraft Pass, Call of Duty Pass).
