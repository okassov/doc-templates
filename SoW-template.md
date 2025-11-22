---
template_type: Statement of Work (SoW)
template_version: 1.0
document_language: Russian
last_updated: 2025-11-22
ai_agent_instructions: |
  This template generates Statement of Work documents for software development projects.
  Guidelines for AI agents:
  1. Replace all AI_PLACEHOLDER sections with project-specific content
  2. Maintain professional and technical tone throughout
  3. Ensure consistency between related sections (e.g., deliverables should align with scope)
  4. Keep examples as reference but replace with actual project data
  5. Validate all requirements against provided project information
  6. Preserve the document structure and numbering
  7. Use Russian language for all generated content
validation_rules:
  - All AI_PLACEHOLDER sections must be filled
  - Minimum 2 functional requirements (FR)
  - Minimum 2 non-functional requirements (nFR)
  - At least 3 deliverables defined
  - Acceptance criteria must be measurable
---

# Statement of Work (SoW)

## 1. Purpose

<!-- AI_PLACEHOLDER: purpose
Description: Describe the main purpose and scope of this SoW document. Explain what problem the project solves and what will be delivered. Include reference to source requirements document if applicable.
Required: Yes
Length: 2-4 paragraphs (150-300 words)
Tone: Professional, clear, concise
Structure:
  - Paragraph 1: What this document describes (project scope and boundaries)
  - Paragraph 2: Problem statement - what problem does this project solve
  - Paragraph 3: Reference to requirements document or related documentation
Example_below: ↓
-->

**ПРИМЕР:**

Этот документ описывает объём и границы проекта по разработке Voice-to-Text решения qCloudy для транскрибации и извлечения значений параметров из аудио-записей колл-центра, а также определяет ключевые компоненты, которые будут реализованы в рамках текущей фазы Proof of Concept.

Проект решает проблему значительных временных затрат операторов на ручное заполнение карточек клиентов в Bitrix24 после звонков. Основан на PoC Requirements Document.

## 2. Scope Definition

### 2.1. In Scope

<!-- AI_PLACEHOLDER: functional_requirements
Description: List all functional requirements (FR) that are included in the project scope. Each requirement should be specific, measurable, and numbered sequentially.
Required: Yes
Format: Numbered list with FR prefix (FR1, FR2, etc.)
Minimum_items: 2
Guidelines:
  - Start each item with FR number
  - Be specific and actionable
  - Include technical details when relevant
  - Group related sub-requirements under main requirement
Example_below: ↓
-->

**Функциональные требования (FR):**

**ПРИМЕР:**
- FR1. Классифицировать аудиозаписи по языку: ru / kz / shkz
- FR2. Выполнить транскрибацию аудио в текст с использованием модели Whisper на Amazon SageMaker
- FR3. Извлекать ключевые сущности из текста:
    - комнатность
    - предпочитаемая площадь
    - стоимость квартиры
    - первоначальный взнос
    - способ оплаты
    - проект ЖК
- FR4. Сохранять результаты транскрибации и сущностей в формате JSON

<!-- AI_PLACEHOLDER: non_functional_requirements
Description: List all non-functional requirements (nFR) that are included in the project scope. Cover performance, security, scalability, compatibility, etc.
Required: Yes
Format: Numbered list with nFR prefix and category in parentheses
Minimum_items: 2
Categories: Performance, Security, Scalability, Compatibility, Usability, Reliability, Maintainability
Guidelines:
  - Start with nFR number and category in parentheses
  - Include measurable criteria when possible
  - Be specific about constraints and limits
Example_below: ↓
-->

**Нефункциональные требования (nFR):**

**ПРИМЕР:**
- nFR1 (Языковая поддержка): система должна корректно работать для ru / kz / shkz (смешанная речь)
- nFR2 (Скорость): транскрибация + извлечение сущностей ≤ 10 минут на один аудиофайл
- nFR3 (Безопасность): все данные должны передаваться и храниться в зашифрованном виде

### 2.2. Out of Scope

<!-- AI_PLACEHOLDER: out_of_scope
Description: List features, functionality, and work items that are explicitly NOT included in this project. This helps set clear boundaries and manage expectations.
Required: Yes
Format: Bulleted list
Minimum_items: 3
Guidelines:
  - Be explicit about what will NOT be done
  - Include items that might be expected but are out of scope
  - Consider future phases or related work that's excluded
  - Help prevent scope creep
Example_below: ↓
-->

**ПРИМЕР:**
- Интеграция с Bitrix24 CRM
- Автоматическое заполнение карточек лидов в CRM
- Обработка аудиофайлов в реальном времени
- Дообучение моделей распознавания речи
- Голосовая аналитика и sentiment analysis
- Обработка других языков, кроме ru / kz / shkz

### 2.3. Assumptions

<!-- AI_PLACEHOLDER: assumptions
Description: List assumptions made during project planning. These are conditions believed to be true that affect project planning and execution.
Required: Yes
Format: Bulleted list
Minimum_items: 3
Guidelines:
  - State what you're assuming will be true or available
  - Include client responsibilities and dependencies
  - Cover resource availability, access, and inputs
  - Note any prerequisites from client side
  - If assumptions prove false, project scope may need adjustment
Example_below: ↓
-->

**ПРИМЕР:**
- Заказчик предоставляет репрезентативную выборку аудиозаписей на ru / kz / shkz для тестирования
- Доступ к AWS-аккаунту предоставляется на этапе разработки
- Аудиофайлы предоставляются в стандартных форматах (mp3, wav, flac)
- Эталонная разметка для проверки точности извлечения параметров будет предоставлена заказчиком
- Все коммуникации ведутся через согласованные каналы связи

### 2.4. Constraints

<!-- AI_PLACEHOLDER: constraints
Description: List constraints and limitations that restrict the project. These are fixed conditions that cannot be changed.
Required: Yes
Format: Bulleted list
Minimum_items: 2
Guidelines:
  - Technical constraints (technology stack, platforms, tools)
  - Time constraints (deadlines, processing time limits)
  - Resource constraints (budget, team size, infrastructure)
  - Regulatory/compliance constraints (security, data privacy)
  - Business constraints (vendor requirements, company policies)
Example_below: ↓
-->

**ПРИМЕР:**
- Использование только AWS-сервисов
- Время обработки одного аудиофайла не должно превышать 10 минут
- Все данные должны передаваться и храниться в зашифрованном виде
- Поддержка трёх языков: русский, казахский, шалаказахский

## 3. Deliverables

<!-- AI_PLACEHOLDER: deliverables
Description: Define concrete deliverables that will be provided to the client. Each deliverable should be tangible and verifiable.
Required: Yes
Format: Markdown table with columns: №, Deliverable, Description
Minimum_items: 3
Guidelines:
  - Each deliverable must be clearly defined and measurable
  - Include both technical and documentation deliverables
  - Number sequentially
  - Keep descriptions concise but specific
  - Align with scope and work breakdown
Example_below: ↓
-->

**ПРИМЕР:**

| № | Deliverable | Описание |
|---|-------------|----------|
| 1 | Voice-to-Text решение на AWS | Развёрнутое решение для транскрибации аудио с моделью Whisper на SageMaker |
| 2 | Upload API | API Gateway endpoint для загрузки аудиофайлов |
| 3 | Модуль классификации языков | Компонент для определения языка аудиозаписи (ru/kz/shkz) |
| 4 | Модуль извлечения сущностей | Компонент для извлечения ключевых параметров из транскрибированного текста |
| 5 | Results API | REST API для получения результатов в формате JSON |
| 6 | Отчёт о тестировании | Документ с результатами проверки критериев успеха на тестовой выборке |
| 7 | Техническая документация | Описание архитектуры, инструкции по развёртыванию и использованию |

## 4. Work Breakdown (High-Level)

<!-- AI_PLACEHOLDER: work_breakdown
Description: Provide a high-level breakdown of major work packages and tasks. This should align with deliverables and scope.
Required: Yes
Format: Bulleted list of work packages
Minimum_items: 5
Guidelines:
  - List major work items in logical order
  - Keep descriptions high-level (detailed tasks go in project plan)
  - Include setup, development, testing, and documentation phases
  - Ensure coverage of all deliverables
  - Consider dependencies and sequence
Example_below: ↓
-->

**ПРИМЕР:**
- Настройка AWS окружения и сервисов для транскрибации
- Разработка API Gateway для загрузки аудиофайлов
- Развёртывание модели Whisper на Amazon SageMaker
- Разработка модуля классификации языков (ru/kz/shkz)
- Настройка S3 events для триггера обработки
- Настройка и конфигурация транскрибации аудио в текст через SageMaker endpoint
- Разработка модуля извлечения ключевых сущностей
- Создание JSON API для получения результатов
- Настройка шифрования данных при передаче и хранении
- Тестирование на предоставленной выборке аудиозаписей
- Валидация критериев успеха и подготовка отчёта
- Подготовка технической документации

## 5. Roles & Responsibilities

<!-- AI_PLACEHOLDER: roles_responsibilities
Description: Define key project roles and their responsibilities. Include both vendor and client team members.
Required: Yes
Format: Bulleted list with Role: responsibilities format
Minimum_items: 3
Guidelines:
  - List role title followed by key responsibilities
  - Include both technical and management roles
  - Specify client-side roles and responsibilities
  - Keep descriptions concise
  - Cover all aspects: planning, development, testing, acceptance
Example_below: ↓
-->

**ПРИМЕР:**
- **PM (Project Manager)**: планирование, координация, отчётность по критериям успеха
- **Architect**: проектирование архитектуры на AWS, выбор сервисов
- **ML Engineer**: настройка моделей транскрибации и извлечения сущностей
- **Backend Developer**: разработка API, интеграция компонентов
- **QA Engineer**: тестирование, валидация критериев успеха
- **Client Representative**: предоставление аудиозаписей и эталонной разметки, приёмка результатов

## 6. Acceptance Criteria

<!-- AI_PLACEHOLDER: acceptance_criteria
Description: Define specific, measurable criteria that must be met for the project to be accepted. These should directly relate to requirements and deliverables.
Required: Yes
Format: Bulleted list of measurable criteria
Minimum_items: 3
Guidelines:
  - Each criterion must be measurable and verifiable
  - Include performance metrics where applicable
  - Reference functional and non-functional requirements
  - Cover quality, completeness, and documentation
  - Use specific numbers and thresholds
  - Include client sign-off requirements
Example_below: ↓
-->

**ПРИМЕР:**
- Заполненность ключевых параметров: ≥90% (ru), ≥80% (kz/shkz) на тестовой выборке
- Точность извлечения параметров: ≥85% (ru), ≥70% (kz/shkz) при сравнении с эталонной разметкой
- Скорость обработки записи: ≤ 10 минут на один аудиофайл
- Все данные передаются и хранятся в зашифрованном виде
- Результаты предоставляются в формате JSON
- Техническая документация предоставлена и согласована
- Заказчик подтвердил соответствие ожидаемому результату согласно заранее сформированному чеклисту

---

## Template Validation Checklist

<!-- AI_AGENT_NOTE: Use this checklist to validate the generated document -->

**Before finalizing the SoW document, ensure:**

- [ ] YAML frontmatter is present and correctly formatted
- [ ] All AI_PLACEHOLDER sections have been replaced with actual content
- [ ] Purpose section contains 2-4 paragraphs describing the project
- [ ] At least 2 functional requirements (FR) are defined
- [ ] At least 2 non-functional requirements (nFR) are defined
- [ ] Out of Scope section has at least 3 items
- [ ] Assumptions section has at least 3 items
- [ ] Constraints section has at least 2 items
- [ ] Deliverables table has at least 3 entries and is properly formatted
- [ ] Work Breakdown has at least 5 major work items
- [ ] Roles & Responsibilities has at least 3 roles defined
- [ ] Acceptance Criteria has at least 3 measurable criteria
- [ ] All sections are consistent with each other
- [ ] All numerical values and metrics are realistic
- [ ] Technical terminology is used correctly
- [ ] Document is in Russian language (unless specified otherwise)
- [ ] No placeholder text remains in the final document

---

## AI Agent Usage Tips

**Когда AI агент использует этот шаблон:**

1. **Извлечение информации**: Агент должен извлечь из требований проекта ключевые данные для заполнения каждой секции
2. **Консистентность**: Убедиться, что Deliverables соответствуют Scope, а Acceptance Criteria измеряют выполнение Requirements
3. **Нумерация**: Сохранить последовательную нумерацию для FR, nFR, и других списков
4. **Таблицы**: Использовать правильный Markdown формат для таблиц
5. **Метрики**: Включить конкретные измеримые значения в nFR и Acceptance Criteria
6. **Валидация**: После генерации проверить документ по чеклисту выше

**Структура данных для передачи агенту (рекомендуемый JSON):**

```json
{
  "project_name": "string",
  "project_type": "string",
  "purpose": {
    "description": "string",
    "problem_statement": "string",
    "source_document": "string"
  },
  "functional_requirements": [
    {"id": "FR1", "description": "string", "sub_items": ["string"]}
  ],
  "non_functional_requirements": [
    {"id": "nFR1", "category": "string", "description": "string"}
  ],
  "out_of_scope": ["string"],
  "assumptions": ["string"],
  "constraints": ["string"],
  "deliverables": [
    {"number": 1, "name": "string", "description": "string"}
  ],
  "work_breakdown": ["string"],
  "roles": [
    {"role": "string", "responsibilities": "string"}
  ],
  "acceptance_criteria": ["string"]
}
```