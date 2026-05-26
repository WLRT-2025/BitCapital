# BitCapital

> Единая точка входа для участников, наблюдателей и инвесторов, которые хотят понять архитектуру BitCapital, текущее состояние Research Pool, правила управления и историю ежемесячной отчетности.

[![Pool Status](https://img.shields.io/endpoint?url=https%3A%2F%2Fraw.githubusercontent.com%2F%3CORG%3E%2F%3CREPO%3E%2Fmain%2F.status%2Fpool-status.json)](#состояние-пула)
[![Liquidity Mode](https://img.shields.io/endpoint?url=https%3A%2F%2Fraw.githubusercontent.com%2F%3CORG%3E%2F%3CREPO%3E%2Fmain%2F.status%2Fliquidity-mode.json)](#состояние-пула)
[![Last Monthly Report](https://img.shields.io/endpoint?url=https%3A%2F%2Fraw.githubusercontent.com%2F%3CORG%3E%2F%3CREPO%3E%2Fmain%2F.status%2Flast-report.json)](#ежемесячные-отчеты)
[![Governance Phase](https://img.shields.io/endpoint?url=https%3A%2F%2Fraw.githubusercontent.com%2F%3CORG%3E%2F%3CREPO%3E%2Fmain%2F.status%2Fgovernance-phase.json)](#управление-для-новых-участников)
[![Research Standard](https://img.shields.io/badge/research-standard%20first-blue)](research-publication-standard_ru.md)

## Назначение репозитория

BitCapital является внутренним исследовательским и прикладным слоем экосистемы WLRT, WaveCounter и WaveCounter IP S.L. Репозиторий фиксирует методологию, состояние Research Pool, отчеты по управлению ликвидностью, публикационные стандарты и рабочие материалы, необходимые для прозрачной навигации по проекту.

BitCapital Research Pool является внутренней средой управления ликвидностью, использующей собственные средства BitCapital. Он не является публичным фондом, клиентским пулом, офертой, инвестиционным продуктом или гарантией доходности для внешних участников.

## Быстрая навигация

| Раздел | Для кого | Ссылка |
|---|---:|---|
| Состояние пула | Инвесторы, наблюдатели, операторы | [Перейти](#состояние-пула) |
| Управление для новых участников | Новые участники, координаторы | [Перейти](#управление-для-новых-участников) |
| Ежемесячные отчеты | Инвесторы, аудиторы, аналитики | [Перейти](#ежемесячные-отчеты) |
| Экосистема | Партнеры, стратегические участники | [../architecture/ecosystem-overview.md](../architecture/ecosystem-overview.md) |
| Карта репозитория | Все участники | [../architecture/repository-map.md](../architecture/repository-map.md) |
| Стандарт публикаций | Авторы отчетов | [research-publication-standard_ru.md](research-publication-standard_ru.md) |
| Дисклеймер | Все читатели | [disclaimer_ru.md](disclaimer_ru.md) |

## Состояние пула

> В BitCapital термин "ликвидность" означает не только денежные средства или торговый объем, а способность системы перераспределять ресурсы между состояниями, активами и конфигурациями при сохранении непрерывности работы.

| Метрика | Текущее значение | Источник обновления |
|---|---:|---|
| Статус пула | `active research` | `.status/pool-status.json` |
| Режим ликвидности | `observation / reallocation / defensive / expansion` | `.status/liquidity-mode.json` |
| Последний отчет | `April 2026` | `.status/last-report.json` |
| Фаза управления | `internal research governance` | `.status/governance-phase.json` |
| Следующее обновление | `YYYY-MM-DD` | `docs/cases/` |

### Формат динамических бейджей

Динамические бейджи выше используют формат `shields.io/endpoint`. Для работы замените `<ORG>` и `<REPO>` на реальные GitHub-значения и храните JSON-файлы в папке `.status/`.

Пример `.status/pool-status.json`:

```json
{
  "schemaVersion": 1,
  "label": "pool",
  "message": "active research",
  "color": "brightgreen"
}
```

Пример `.status/liquidity-mode.json`:

```json
{
  "schemaVersion": 1,
  "label": "liquidity",
  "message": "reallocation",
  "color": "blue"
}
```

Пример `.status/last-report.json`:

```json
{
  "schemaVersion": 1,
  "label": "last report",
  "message": "April 2026",
  "color": "informational"
}
```

Пример `.status/governance-phase.json`:

```json
{
  "schemaVersion": 1,
  "label": "governance",
  "message": "internal research",
  "color": "purple"
}
```

## Управление для новых участников

### Перед началом

1. Изучите назначение BitCapital и Research Pool в этом README.
2. Прочитайте [экосистемный обзор](../architecture/ecosystem-overview.md), чтобы понять связку WLRT, WaveCounter, WaveCounter IP S.L., BitCapital, Research Pool и KEFEN.
3. Ознакомьтесь с последними ежемесячными отчетами, начиная с [последнего доступного отчета](cases/bitcapital-research-pool_april-2026_en.md).
4. Проверьте актуальные бейджи в верхней части README и JSON-статусы в `.status/`.
5. Примите дисклеймер: материалы имеют исследовательский характер и не являются инвестиционной рекомендацией.

### Роли участников

| Роль | Задача | Доступ |
|---|---|---|
| Observer | Читает отчеты, отслеживает динамику и задает вопросы | Read |
| Contributor | Предлагает улучшения отчетов, терминологии и структуры | Pull Request |
| Research Operator | Обновляет отчеты, статусы и методологические примечания | Maintainer |
| Governance Reviewer | Проверяет изменения, влияющие на правила управления и публикации | Review Required |

### Базовый цикл управления

1. **Наблюдение:** участник фиксирует изменение, риск, гипотезу или операционный факт.
2. **Формализация:** изменение оформляется как issue или pull request с контекстом, датой и ссылкой на затронутый отчет.
3. **Проверка:** Research Operator сверяет изменение с публикационным стандартом и историей отчетов.
4. **Решение:** Governance Reviewer подтверждает, отклоняет или отправляет изменение на доработку.
5. **Публикация:** после merge обновляются README, соответствующий отчет и динамические JSON-бейджи.

### Минимальные правила pull request

- Один pull request должен решать одну управленческую или отчетную задачу.
- Любое изменение статуса пула должно сопровождаться ссылкой на отчет, issue или внутреннюю заметку.
- Нельзя формулировать результаты как обещание доходности, гарантию ликвидности или предложение внешнего капитала.
- Если изменение касается KEFEN, нужно явно указать, что возможные access, status, execution или governance-функции не являются equity или гарантированными правами.

## Ежемесячные отчеты

> Если структура папок в вашем репозитории отличается, сохраните названия отчетов, но обновите относительные пути в таблице.

| Период | Язык | Отчет |
|---|---:|---|
| Январь 2026 | RU | [BitCapital Research Pool: январь 2026](cases/bitcapital-research-pool_january-2026_ru.md) |
| Февраль 2026 | RU | [BitCapital Итоги управления пулом ликвидности: февраль 2026](cases/bitcapital-research-pool_february-2026_ru.md) |
| Февраль 2026 | EN | [BitCapital Research Pool: February 2026](cases/bitcapital-research-pool_february-2026_en.md) |
| Март 2026 | RU | [BitCapital Итоги управления пулом ликвидности: март 2026](cases/bitcapital-research-pool_march-2026_ru.md) |
| Март 2026 | EN | [BitCapital Research Pool: March 2026](cases/bitcapital-research-pool_march-2026_en.md) |
| Апрель 2026 | EN | [BitCapital Research Pool: April 2026](cases/bitcapital-research-pool_april-2026_en.md) |

### Сводные отчеты

| Период | Язык | Отчет |
|---|---:|---|
| Январь - апрель 2026 | RU | [BitCapital Отчет по управлению пулом ликвидности: январь - апрель 2026](cases/bitcapital-research-pool_january-april-2026_ru.md) |
| Январь - апрель 2026 | EN | [BitCapital Research Pool Report: January - April 2026](cases/bitcapital-research-pool_january-april-2026_en.md) |
| Март - май 2026 | RU | [BitCapital Структурный отчет: март - май 2026](cases/bitcapital-research-pool_mar-may-2026_ru.md) |
| Март - май 2026 | EN | [BitCapital Research Pool Report: March - May 2026](cases/bitcapital-research-pool_mar-may-2026_en.md) |

## Рекомендуемая структура репозитория

```text
.
├── README.md
├── .status/
│   ├── pool-status.json
│   ├── liquidity-mode.json
│   ├── last-report.json
│   └── governance-phase.json
├── architecture/
│   ├── ecosystem-overview.md
│   └── repository-map.md
├── docs/
│   ├── index.md
│   ├── README_BitCapital_investor_entry_template.md
│   ├── research-publication-standard_ru.md
│   ├── research-publication-standard_en.md
│   ├── disclaimer_ru.md
│   ├── disclaimer_en.md
│   └── cases/
│       ├── bitcapital-research-pool_january-2026_ru.md
│       ├── bitcapital-research-pool_february-2026_ru.md
│       ├── bitcapital-research-pool_february-2026_en.md
│       ├── bitcapital-research-pool_march-2026_ru.md
│       ├── bitcapital-research-pool_march-2026_en.md
│       ├── bitcapital-research-pool_april-2026_en.md
│       ├── bitcapital-research-pool_january-april-2026_ru.md
│       └── bitcapital-research-pool_january-april-2026_en.md
└── governance/
    ├── proposals/
    └── decisions/
```

## Обновление README и статусов

### При публикации нового ежемесячного отчета

1. Добавьте отчет в `docs/cases/`.
2. Добавьте строку в таблицу [ежемесячных отчетов](#ежемесячные-отчеты).
3. Обновите `.status/last-report.json`.
4. Если изменился режим ликвидности, обновите `.status/liquidity-mode.json`.
5. Если изменился операционный или исследовательский статус пула, обновите `.status/pool-status.json`.
6. Создайте pull request с кратким summary, ссылкой на отчет и чек-листом проверки.

### Чек-лист перед merge

- [ ] Отчет добавлен в правильную папку.
- [ ] Ссылка на отчет открывается из README.
- [ ] Бейдж последнего отчета обновлен.
- [ ] Режим ликвидности соответствует формулировкам отчета.
- [ ] Нет обещаний доходности или инвестиционных гарантий.
- [ ] Дисклеймер и исследовательский характер материалов сохранены.

## Дисклеймер

Материалы BitCapital имеют исследовательский и информационный характер. Они не являются инвестиционной рекомендацией, публичной офертой, предложением участия в фонде, предложением привлечения капитала или гарантией финансового результата. Research Pool описывает внутреннюю исследовательскую среду BitCapital и не является клиентским пулом.

