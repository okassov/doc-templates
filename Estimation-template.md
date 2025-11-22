---
template_type: Project Estimation Document
template_version: 1.0
document_language: Russian
last_updated: 2025-11-22
ai_agent_instructions: |
  This template generates detailed project estimation documents with effort breakdown.
  Guidelines for AI agents:
  1. Replace all AI_PLACEHOLDER sections with project-specific content
  2. Calculate effort estimates based on project requirements and complexity
  3. Ensure all task estimates align with functional and non-functional requirements
  4. Maintain consistency between Executive Summary totals and detailed breakdowns
  5. Keep examples as reference but replace with actual project data
  6. Validate all calculations (totals, percentages, FTE)
  7. Preserve the document structure and section hierarchy
  8. Use Russian language for all generated content
validation_rules:
  - All AI_PLACEHOLDER sections must be filled
  - Executive Summary totals must match detailed category totals
  - All percentages must sum to 100%
  - Team Allocation hours must match Grand Total
  - Timeline phases must be logical and sequential
  - All tables must be properly formatted in Markdown
  - Contingency percentage must be applied consistently
---

# Project Estimation Document

# Executive Summary

<!-- AI_PLACEHOLDER: executive_summary
Description: High-level summary table showing effort distribution across main categories. This is calculated from detailed breakdowns below.
Required: Yes
Format: Markdown table with columns: Category, Hours, Percentage
Guidelines:
  - List all major work categories
  - Calculate hours from detailed sections
  - Calculate percentage of total effort
  - Include Total Estimate row
  - Percentages should sum to 100%
  - Align with detailed breakdowns in sections below
Example_below: ↓
-->

**ПРИМЕР:**

| Category | Hours | Percentage |
|----------|-------|------------|
| ML Engineering | 104 | 33% |
| Backend Development | 72 | 23% |
| Infrastructure & DevOps | 64 | 20% |
| Testing & QA | 44 | 14% |
| Documentation | 20 | 6% |
| Project Management | 16 | 5% |
| **Total Estimate** | **320** | **100%** |

# 1. ML Engineering

<!-- AI_PLACEHOLDER: ml_engineering_tasks
Description: Detailed breakdown of ML Engineering tasks with effort estimates. Map tasks to functional/non-functional requirements.
Required: Yes
Format: Markdown table with columns: Task, Hours, Description
Minimum_items: 5 tasks
Guidelines:
  - Reference FR/nFR from SoW where applicable
  - Include research, development, testing, and optimization tasks
  - Provide specific descriptions for each task
  - Calculate subtotal that matches Executive Summary
  - Consider ML-specific activities: model selection, training, deployment, tuning
Example_below: ↓
-->

**ПРИМЕР:**

| Task | Hours | Description |
|------|-------|-------------|
| FR1: Исследование методов классификации языка | 8 | Анализ подходов для определения ru/kz/shkz |
| FR1: Разработка модуля классификации языка | 12 | Реализация language detection для аудио |
| FR1: Тестирование классификатора | 6 | Проверка точности на тестовых данных |
| FR2: Подготовка модели Whisper для SageMaker | 16 | Выбор версии, подготовка Docker образа |
| FR2: Развёртывание Whisper на SageMaker | 20 | Создание endpoint, настройка instance type, auto-scaling |
| FR2: Тестирование транскрибации | 8 | Проверка качества на ru/kz/shkz |
| nFR1: Валидация языковой поддержки ru | 8 | Тестирование транскрибации на русском |
| nFR1: Валидация языковой поддержки kz | 8 | Тестирование транскрибации на казахском |
| nFR1: Валидация языковой поддержки shkz | 8 | Тестирование на шалаказахском (смешанная речь) |
| nFR2: Оптимизация производительности SageMaker | 10 | Настройка instance type, batch processing, latency optimization |
| **Subtotal** | **104** | |

# 2. Backend Development

<!-- AI_PLACEHOLDER: backend_development_tasks
Description: Detailed breakdown of Backend Development tasks with effort estimates.
Required: Yes
Format: Markdown table with columns: Task, Hours, Description
Minimum_items: 5 tasks
Guidelines:
  - Reference FR/nFR from SoW where applicable
  - Include API development, business logic, integrations
  - Provide specific descriptions for each task
  - Calculate subtotal that matches Executive Summary
  - Consider backend-specific activities: API design, Lambda functions, data models
Example_below: ↓
-->

**ПРИМЕР:**

| Task | Hours | Description |
|------|-------|-------------|
| FR1: Разработка Lambda Orchestrator | 12 | Координация процесса обработки, интеграция классификатора |
| FR2: Разработка Lambda для вызова SageMaker | 12 | Логика отправки аудио и получения транскрипции |
| FR3: Разработка правил извлечения сущностей | 16 | Regex и NLP паттерны для комнатности, площади, стоимости, взноса, способа оплаты, проекта ЖК |
| FR3: Интеграция с Amazon Bedrock | 12 | Настройка LLM для улучшения извлечения на kz/shkz |
| FR3: Разработка Lambda Entity Extractor | 8 | Реализация логики извлечения и валидации |
| FR4: Проектирование схемы данных | 4 | Структура JSON и схема DynamoDB |
| FR4: Разработка API для результатов | 8 | API Gateway + Lambda для чтения данных из DynamoDB |
| **Subtotal** | **72** | |

# 3. Infrastructure & DevOps

<!-- AI_PLACEHOLDER: infrastructure_devops_tasks
Description: Detailed breakdown of Infrastructure & DevOps tasks with effort estimates.
Required: Yes
Format: Markdown table with columns: Task, Hours, Description
Minimum_items: 5 tasks
Guidelines:
  - Reference FR/nFR from SoW where applicable (especially security and performance)
  - Include infrastructure setup, IaC, CI/CD, monitoring
  - Provide specific descriptions for each task
  - Calculate subtotal that matches Executive Summary
  - Consider DevOps activities: networking, security, automation, monitoring
Example_below: ↓
-->

**ПРИМЕР:**

| Task | Hours | Description |
|------|-------|-------------|
| Настройка AWS окружения | 8 | VPC, subnets, security groups, VPC endpoints |
| FR4: Настройка S3 bucket | 4 | Создание bucket для аудиофайлов |
| FR4: Настройка SQS queue | 4 | Создание очереди для асинхронной обработки |
| FR4: Настройка DynamoDB таблиц | 6 | Создание таблиц, индексов, настройка capacity |
| nFR2: Настройка асинхронной обработки | 6 | Оптимизация SQS, параллельная обработка |
| nFR2: Оптимизация Lambda функций | 6 | Настройка memory, timeout, concurrency |
| nFR3: Настройка шифрования S3 | 4 | Включение SSE-S3 encryption at-rest |
| nFR3: Настройка шифрования DynamoDB | 4 | Включение encryption at-rest |
| nFR3: Настройка AWS KMS | 6 | Создание и управление ключами шифрования |
| nFR3: Настройка TLS | 4 | Обеспечение encryption in-transit |
| nFR3: Настройка IAM ролей и политик | 6 | Принцип least privilege для всех компонентов |
| Infrastructure as Code (Terraform/SAM) | 12 | Написание IaC для всех компонентов |
| Настройка CI/CD пайплайна | 10 | GitHub Actions / AWS CodePipeline |
| Настройка CloudWatch логирования | 4 | Централизованное логирование |
| Настройка мониторинга и алертинга | 6 | CloudWatch Metrics, Alarms, SNS |
| **Subtotal** | **64** | |

# 4. Testing & QA

<!-- AI_PLACEHOLDER: testing_qa_tasks
Description: Detailed breakdown of Testing & QA tasks with effort estimates.
Required: Yes
Format: Markdown table with columns: Task, Hours, Description
Minimum_items: 5 tasks
Guidelines:
  - Reference FR/nFR from SoW for test cases
  - Include functional testing, performance testing, security testing
  - Include test data preparation and reporting
  - Calculate subtotal that matches Executive Summary
  - Consider QA activities: test planning, execution, validation, reporting
Example_below: ↓
-->

**ПРИМЕР:**

| Task | Hours | Description |
|------|-------|-------------|
| Подготовка тестовых данных | 4 | Сбор и разметка тестовой выборки аудиофайлов |
| FR1: Тестирование классификации языка | 4 | Проверка точности определения ru/kz/shkz |
| FR2: Тестирование транскрибации | 6 | Проверка качества транскрипции |
| FR3: Тестирование извлечения сущностей | 8 | Проверка точности извлечения параметров |
| FR4: Тестирование API и сохранения данных | 4 | Проверка корректности JSON и DynamoDB |
| nFR2: Performance тестирование | 6 | Замер времени обработки, проверка ≤10 минут |
| nFR3: Security тестирование | 4 | Проверка шифрования, IAM политик |
| Валидация критериев успеха | 6 | Проверка заполненности ≥90% (ru), ≥80% (kz/shkz) и точности ≥85% (ru), ≥70% (kz/shkz) |
| Подготовка отчёта о тестировании | 4 | Документирование результатов и метрик |
| **Subtotal** | **44** | |

# 5. Documentation

<!-- AI_PLACEHOLDER: documentation_tasks
Description: Detailed breakdown of Documentation tasks with effort estimates.
Required: Yes
Format: Markdown table with columns: Task, Hours, Description
Minimum_items: 3 tasks
Guidelines:
  - Include technical documentation, user guides, deployment guides
  - Include knowledge transfer activities
  - Calculate subtotal that matches Executive Summary
  - Consider documentation types: architecture, API, deployment, user guides, KT
Example_below: ↓
-->

**ПРИМЕР:**

| Task | Hours | Description |
|------|-------|-------------|
| Техническая документация | 8 | Описание архитектуры, компонентов, API |
| Инструкции по развёртыванию | 4 | Руководство по установке и настройке |
| Инструкции по использованию | 4 | Руководство пользователя для операторов |
| Knowledge transfer сессии | 4 | Передача знаний команде клиента |
| **Subtotal** | **20** | |

# 6. Project Management

<!-- AI_PLACEHOLDER: project_management_tasks
Description: Detailed breakdown of Project Management tasks with effort estimates.
Required: Yes
Format: Markdown table with columns: Task, Hours, Description
Minimum_items: 3 tasks
Guidelines:
  - Include planning, coordination, reporting, risk management
  - Calculate subtotal that matches Executive Summary
  - Consider PM activities: planning, standups, reporting, demos, risk management
Example_below: ↓
-->

**ПРИМЕР:**

| Task | Hours | Description |
|------|-------|-------------|
| Планирование и координация | 8 | Sprint planning, daily standups, координация команды |
| Отчётность и демонстрации | 4 | Статус-репорты, демо для клиента |
| Управление рисками | 4 | Мониторинг и митигация рисков проекта |
| **Subtotal** | **16** | |

# Total Project Estimate

<!-- AI_PLACEHOLDER: total_estimate
Description: Summary of all effort with contingency. Must match sum of all category subtotals from sections above.
Required: Yes
Format: Markdown table with columns: Category, Hours
Guidelines:
  - List all categories with their subtotals from detailed sections
  - Calculate Total (sum of all categories)
  - Add Contingency percentage (typically 10-20%)
  - Calculate Grand Total (Total + Contingency)
  - Verify totals match Executive Summary and detailed breakdowns
Example_below: ↓
-->

**ПРИМЕР:**

| Category | Hours |
|----------|-------|
| ML Engineering | 104 |
| Backend Development | 72 |
| Infrastructure & DevOps | 64 |
| Testing & QA | 44 |
| Documentation | 20 |
| Project Management | 16 |
| **Total** | **320** |
| Contingency (10%) | 32 |
| **Grand Total** | **352 hours** |

# Team Allocation

<!-- AI_PLACEHOLDER: team_allocation
Description: Distribution of effort across team roles with FTE calculation. Total hours must match Grand Total.
Required: Yes
Format: Markdown table with columns: Role, Hours, FTE
Minimum_items: 3 roles
Guidelines:
  - List all team roles needed for the project
  - Allocate hours based on tasks assigned to each role
  - Calculate FTE (Full-Time Equivalent): hours / (project_weeks * 40)
  - Total hours must equal Grand Total from previous section
  - Sum FTE to show total team size
Example_below: ↓
-->

**ПРИМЕР:**

| Role | Hours | FTE |
|------|-------|-----|
| Solution Architect | 40 | 0.25 |
| ML Engineer | 80 | 0.5 |
| Backend Developer | 96 | 0.6 |
| DevOps Engineer | 56 | 0.35 |
| QA Engineer | 48 | 0.3 |
| Project Manager | 32 | 0.2 |
| **Total** | **352** | **2.2 FTE** |

# Timeline Estimate

<!-- AI_PLACEHOLDER: timeline_estimate
Description: Project timeline broken down into phases with dependencies. Duration calculated based on FTE working in parallel.
Required: Yes
Format: Opening statement + Markdown table with columns: Phase, Duration, Dependencies
Minimum_items: 3 phases
Guidelines:
  - State FTE assumption at the beginning
  - Break project into logical phases
  - Estimate duration per phase considering parallelization
  - Specify dependencies between phases
  - Calculate total duration
  - Consider critical path and parallel work streams
Example_below: ↓
-->

**ПРИМЕР:**

Assuming 2.2 FTE working in parallel:

| Phase | Duration | Dependencies |
|-------|----------|--------------|
| Phase 1: Infrastructure Setup | 1 week | None |
| Phase 2: SageMaker Whisper Deployment | 2 weeks | Phase 1 |
| Phase 3: Lambda Functions Development | 2 weeks | Phase 2 |
| Phase 4: Entity Extraction & Bedrock | 1.5 weeks | Phase 3 |
| Phase 5: Testing & Optimization | 1.5 weeks | Phase 4 |
| Phase 6: Documentation & KT | 1 week | Phase 5 |
| **Total Duration** | **9 weeks** | |

# Risk Factors Affecting Estimate

<!-- AI_PLACEHOLDER: risk_factors
Description: Identify risks that could impact the estimate with potential hour impact and mitigation strategies.
Required: Yes
Format: Markdown table with columns: Risk, Impact on Estimate, Mitigation
Minimum_items: 3 risks
Guidelines:
  - List technical and non-technical risks
  - Quantify potential impact on hours (e.g., +10-20 hours)
  - Provide specific mitigation strategies
  - Consider: technical complexity, data availability, performance issues, integration challenges
Example_below: ↓
-->

**ПРИМЕР:**

| Risk | Impact on Estimate | Mitigation |
|------|-------------------|------------|
| Низкая точность Whisper на kz/shkz | +20-40 hours | Дообучение модели, использование Bedrock для пост-обработки |
| Недостаточная выборка тестовых данных | +10-20 hours | Запросить больше данных у клиента заранее |
| Проблемы с производительностью SageMaker | +15-30 hours | Использование более мощных instance types |
| Сложности с извлечением численных значений | +10-20 hours | Дополнительные валидационные правила |

---

## Template Validation Checklist

<!-- AI_AGENT_NOTE: Use this checklist to validate the generated document -->

**Before finalizing the Estimation document, ensure:**

- [ ] YAML frontmatter is present and correctly formatted
- [ ] All AI_PLACEHOLDER sections have been replaced with actual content
- [ ] Executive Summary totals match detailed category subtotals
- [ ] All percentages in Executive Summary sum to 100%
- [ ] Each detailed category section (ML, Backend, Infrastructure, Testing, Documentation, PM) has subtotal
- [ ] Subtotals from sections 1-6 sum to Total in "Total Project Estimate"
- [ ] Contingency percentage is applied and Grand Total calculated correctly
- [ ] Team Allocation total hours equal Grand Total
- [ ] FTE calculations are correct (hours / project_weeks / 40)
- [ ] Timeline phases are logical and sequential
- [ ] Phase dependencies make sense
- [ ] Total duration is realistic given FTE and total hours
- [ ] At least 3 risk factors are identified with quantified impact
- [ ] All tables are properly formatted in Markdown
- [ ] All task descriptions are clear and specific
- [ ] Tasks reference FR/nFR where applicable
- [ ] Document is in Russian language (unless specified otherwise)
- [ ] No placeholder text or example markers remain in the final document

---

## AI Agent Usage Tips

**Когда AI агент использует этот шаблон:**

1. **Извлечение требований**: Агент должен извлечь из SoW/требований проекта все FR и nFR для оценки
2. **Категоризация задач**: Распределить задачи по категориям (ML, Backend, Infrastructure, Testing, etc.)
3. **Оценка сложности**: Оценить каждую задачу на основе сложности и объема работы
4. **Расчет итогов**: Обеспечить математическую корректность всех сумм и процентов
5. **Распределение команды**: Назначить часы по ролям на основе типа задач
6. **Планирование фаз**: Определить логическую последовательность фаз с учетом зависимостей
7. **Валидация**: После генерации проверить все расчеты по чеклисту выше

**Принципы оценки:**

- **Исследование**: 20-30% от времени разработки для новых технологий
- **Разработка**: Основной объем работы, зависит от сложности
- **Тестирование**: 30-50% от времени разработки
- **Документация**: 5-10% от общего времени
- **PM**: 5-10% от общего времени
- **Contingency**: 10-20% от итоговой оценки

**Структура данных для передачи агенту (рекомендуемый JSON):**

```json
{
  "project_name": "string",
  "requirements": {
    "functional": [{"id": "FR1", "description": "string"}],
    "non_functional": [{"id": "nFR1", "description": "string"}]
  },
  "categories": [
    {
      "name": "ML Engineering",
      "tasks": [
        {"task": "string", "hours": number, "description": "string", "ref": "FR1"}
      ]
    }
  ],
  "team": [
    {"role": "string", "hours": number}
  ],
  "phases": [
    {"phase": "string", "duration": "string", "dependencies": "string"}
  ],
  "risks": [
    {"risk": "string", "impact": "string", "mitigation": "string"}
  ],
  "contingency_percent": number
}
```

**Формулы для расчетов:**

- **Percentage** = (Category Hours / Total Hours) × 100
- **FTE** = Role Hours / (Project Duration in Weeks × 40)
- **Total** = Sum of all category subtotals
- **Grand Total** = Total × (1 + Contingency %)
- **Project Duration** = Grand Total / (Total FTE × 40)