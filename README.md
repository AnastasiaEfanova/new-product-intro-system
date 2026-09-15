# New Product Intro System

## Автоматизация процесса ввода новых блюд в сети закусочных «Замысловатость»

Репозиторий содержит проектную документацию **New Product Intro System** —
информационной системы для автоматизации процесса ввода новых блюд в сети
закусочных «Замысловатость».

Документация подготовлена с использованием подхода **Docs-as-Code** и включает
описание целей и границ проекта, Roadmap, состава команды, проектных рисков,
выбранного решения, архитектуры, нефункциональных требований и API-контрактов.

---

## 📚 Документация проекта

| № | Раздел | Описание |
|---|---|---|
| 1 | [Общая информация](https://github.com/AnastasiaEfanova/new-product-intro-system/blob/main/docs/01-overview.md) | Назначение проекта, предпосылки и общая информация |
| 2 | [Цели внедрения проекта](https://github.com/AnastasiaEfanova/new-product-intro-system/blob/main/docs/02-goals.md) | Цели автоматизации и ожидаемые результаты |
| 3 | [Описание проекта и основных задач](https://github.com/AnastasiaEfanova/new-product-intro-system/blob/main/docs/03-project-description.md) | Описание проекта, As-Is / To-Be и основные решаемые задачи |
| 4 | [Roadmap проекта](https://github.com/AnastasiaEfanova/new-product-intro-system/blob/main/docs/04-roadmap.md) | Этапы реализации, спринты, Roadmap, диаграмма Ганта и ключевые вехи |
| 5 | [Команда проекта](https://github.com/AnastasiaEfanova/new-product-intro-system/blob/main/docs/05-team.md) | Состав проектной команды, роли и зоны ответственности |
| 6 | [Риски проекта](https://github.com/AnastasiaEfanova/new-product-intro-system/blob/main/docs/06-risks.md) | Реестр рисков, матрица рисков, RBS и мероприятия по управлению |
| 7 | [Описание выбранного решения](https://github.com/AnastasiaEfanova/new-product-intro-system/blob/main/docs/07-solution.md) | Концепция New Product Intro System и основные функциональные возможности |
| 8 | [Архитектура проекта](https://github.com/AnastasiaEfanova/new-product-intro-system/blob/main/docs/08-architecture.md) | C4, сервисы, интеграции, Kafka, Outbox, НФТ и результаты ATAM |
| 9 | [Заключение](https://github.com/AnastasiaEfanova/new-product-intro-system/blob/main/docs/09-conclusion.md) | Итоги проекта, ожидаемый эффект и личные точки роста |

---

## 🏗 Архитектура

Архитектура New Product Intro System описана с использованием **C4 Model**.

Основные архитектурные решения:

- микросервисная архитектура;
- REST API для синхронного взаимодействия;
- **Apache Kafka** для событийного взаимодействия;
- **Outbox** для надёжной публикации событий;
- отдельный **Integration Service**;
- хранение состояния интеграционных операций;
- **Synchronization Worker** и retry-механизмы;
- централизованная авторизация;
- мониторинг и логирование.

Подробное описание:

➡️ **[Перейти к архитектуре проекта](https://github.com/AnastasiaEfanova/new-product-intro-system/blob/main/docs/08-architecture.md)**

### Архитектурные схемы

- [C4 — System Context](/images/C4%20System%20Context.png)
- [C4 — Container](/images/C4%20Container.png)
- [C4 — Component](/images/C4%20Component.png)

---

## 🔌 API-контракты

Синхронные REST-интерфейсы системы документируются с использованием
**OpenAPI 3.0**.

| API | Назначение |
|---|---|
| [Product Management API](API/product-management-api.yaml) | Создание, получение и изменение карточек новых блюд |
| [Integration API](API/integration-api.yaml) | Получение состояния интеграционных задач и результатов синхронизации |

API-контракты хранятся в одном Git-репозитории с проектной документацией
и версионируются вместе с изменениями системы.

---

## 🗺 Roadmap

Плановый период реализации проекта:

**15.05.2026 — 29.11.2026**

Проект включает следующие основные этапы:

**Анализ → Архитектура → UX/UI → Разработка → Интеграции → Тестирование → Инфраструктура → Внедрение**

Работы частично выполняются параллельно в соответствии с зависимостями
и доступностью проектных ресурсов.

➡️ **[Roadmap и диаграмма Ганта](docs/04-roadmap.md)**

---

## ⚠️ Управление рисками

В рамках проекта сформирован реестр проектных рисков, выполнена их оценка
по вероятности и влиянию и разработана **Risk Breakdown Structure (RBS)**.

К критическим рискам проекта относятся:

- **R1** — задержка согласования требований;
- **R2** — ограниченность ресурсов разработки;
- **R3** — сложность интеграций с информационными системами.

➡️ **[Реестр и матрица рисков](docs/06-risks.md)**

---

## 📐 Нефункциональные требования

Для анализа архитектуры и нефункциональных требований использовался
**ATAM (Architecture Tradeoff Analysis Method)**.

В рамках проекта рассматриваются следующие атрибуты качества:

- надёжность;
- интегрируемость;
- производительность;
- масштабируемость;
- безопасность;
- сопровождаемость;
- наблюдаемость.

Наиболее высокий архитектурный приоритет имеют **надёжность** и
**интегрируемость**.

➡️ **[НФТ и архитектурные решения](docs/08-architecture.md#нефункциональные-требования)**

---

## 📁 Структура репозитория

```text
.
├── README.md
│
├── docs/
│   ├── 01-general-information.md
│   ├── 02-project-goals.md
│   ├── 03-project-description.md
│   ├── 04-roadmap.md
│   ├── 05-project-team.md
│   ├── 06-risks.md
│   ├── 07-solution-description.md
│   ├── 08-architecture.md
│   └── 09-conclusion.md
│
├── api/
│   ├── product-management-api.yaml
│   └── integration-api.yaml
│
└── images/
    ├── C4-System-Context.png
    ├── C4-Container.png
    └── ...
```

---

## 📌 О проекте

**Проект:** New Product Intro System  
**Предметная область:** сеть закусочных «Замысловатость»  
**Тип решения:** автоматизация процесса ввода нового блюда  
**Подход к документации:** Docs-as-Code  
**Плановый период:** 15.05.2026–29.11.2026  
**Архитектурный подход:** микросервисная архитектура  
**Описание архитектуры:** C4 Model  
**Описание REST API:** OpenAPI 3.0  
**Метод анализа архитектуры:** ATAM