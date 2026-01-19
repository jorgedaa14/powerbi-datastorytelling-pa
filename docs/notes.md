# Notes (Project decisions)

- Scope: 2014–2017 for context; deep-dive on 2017 as the last complete year for decision-making.
- Granularity: order-line level; KPIs are computed as measures to respect filter context (time, product, geography, ship mode).
- Core measures: Sales, Profit, Orders, Customers, Quantity.
- Key derived KPIs: Profit Margin %, Avg Order Value (Ticket Medio), Profit per Order, Weighted Discount (by Sales).
- Weighted Discount was preferred over simple average discount to reflect commercial impact (large sales lines weigh more).
- Visual design: executive storytelling (one message per slide + evidence + implication), avoiding dense tables except where the product set is very small.
- Negative profit values shown explicitly to highlight loss drivers; charts split positives/negatives around a zero baseline.
- Findings were validated by drilling from month → sub-category → product / state to avoid “single-chart” conclusions.
- Deliverables: Power BI report (.pbix) + executive deck (PDF) with final insights and recommendations.
