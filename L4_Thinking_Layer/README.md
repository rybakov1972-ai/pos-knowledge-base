# L4 — Thinking Layer

Агенты, Decision Support, Simulation.

## Правила

- L4 **генерирует артефакты**; артефакты **проходят валидацию до записи в L2**.
- Агент — не чат-бот. Три обязательных свойства:
  - **Контракт:** что на входе, что на выходе, как проверяется.
  - **След:** каждое решение пишется в [`Explainability_Log.md`](../Explainability_Log.md) с обоснованием.
  - **Право порождать:** агент может предложить нового агента или модуль L3; предложение проходит валидацию (человек + агент-валидатор).

## Состав на старте

| Агент | Роль | Контракт |
|---|---|---|
| Doctrine Agent | Интерпретирует правила и ROE | [`agents/doctrine_agent.md`](agents/doctrine_agent.md) |
| Threat Modelling Agent | Моделирует противника и его варианты действий | [`agents/threat_modelling_agent.md`](agents/threat_modelling_agent.md) |
| Red Team Agent | Автономный противник для проверки наших решений | [`agents/red_team_agent.md`](agents/red_team_agent.md) |
| Blue COA Agent | Курсы действий с оценкой «эффективность / риск / время» | [`agents/blue_coa_agent.md`](agents/blue_coa_agent.md) |
| Interoperability Agent | Семантический мост к SAPIENT, C2SIM и внешним системам | [`agents/interoperability_agent.md`](agents/interoperability_agent.md) |

Шаблон нового агента: [`agents/_AGENT_TEMPLATE.md`](agents/_AGENT_TEMPLATE.md).

## Прочее

- [`decision_support/`](decision_support/) — артефакты поддержки решений.
- [`simulation/`](simulation/) — сценарии и результаты моделирования.
