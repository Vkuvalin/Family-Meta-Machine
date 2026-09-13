<div align="center">

# 🧠 Family Meta Machine

**Мета-когнитивная prompt-архитектура над GPT**

Маршрутизация запросов, режимы анализа, итерационная декомпозиция и когнитивная навигация.

**Legacy R&D · prompt / instruction orchestration framework**

[Сайт проекта](https://meta-machine.vercel.app/#home) · [Архитектура](https://meta-machine.vercel.app/#architecture)

</div>

---

## 📝 О проекте

**Meta Machine** — экспериментальная модульная prompt/instruction-архитектура, разработанная как управляющая надстройка над GPT.

Цель проекта — исследовать, насколько поведение LLM можно сделать более структурированным, адаптивным и управляемым с помощью декларативных инструкций, маршрутизации запросов, ролевых модулей, шаблонов рассуждений и пошаговой декомпозиции.

Вместо одного большого prompt система разбита на отдельные логические модули:

- **Core Instructions** — правила инициализации и порядок подключения компонентов.
- **Role Definition Layer** — ролевой и поведенческий профиль.
- **Cognitive Routing Center** — декларативное состояние текущей стратегии обработки.
- **Core Cognitive Processor** — маршрут анализа: вход → контекст → метод → обработка → адаптация → вывод.
- **Template Library** — набор стратегий обработки разных типов задач.
- **Iteration Plan** — пошаговая декомпозиция сложных запросов.
- **Text Styling Rules** — правила адаптивного оформления ответа.
- **DLS** — собственная нотация для директив, логических слоёв, приоритетов, маршрутов и semantic anchors.

> Проект представляет собой **legacy R&D snapshot** ранней системы prompt orchestration. Часть механизмов отражает ограничения и поведение моделей предыдущих поколений и не рассматривается как актуальная production-архитектура.

---

## 🧩 Архитектура

```text
User request
      ↓
GPT Core Instructions
      ↓
Role / Intent Layer
      ↓
Cognitive Routing Center
      ↓
Cognitive Processor
      ↓
Reasoning Template
      ↓
Iteration / Adaptation
      ↓
Output Formatting
```

<details>
<summary><strong>Показать архитектурную схему</strong></summary>
<br>

<p float="left">
  <img src="https://github.com/user-attachments/assets/d05b6026-9d6d-4213-9de4-3f27457a19a9" width="99%" />
</p>

</details>

---

## 🔧 Ключевые идеи

- **Prompt orchestration** — разделение поведения модели на независимые модули вместо монолитной инструкции.
- **Cognitive routing** — выбор режима обработки в зависимости от типа и контекста запроса.
- **Reasoning templates** — использование разных стратегий для анализа, исследования, объяснения и декомпозиции.
- **State-like configuration** — декларативное описание активного шаблона, глубины, фокуса, стиля и других параметров поведения.
- **Iteration control** — управляемая пошаговая работа со сложными задачами.
- **Adaptive output** — форматирование и уровень детализации подстраиваются под контекст.
- **Prompt-level guardrails** — отдельные правила проверки входа и поведения системы.
- **Custom instruction DSL** — собственная система директив, ссылок, приоритетов, операторов и semantic anchors.

---

## 🧠 Стратегии обработки

| Режим | Назначение |
|---|---|
| **Iterative** | пошаговая декомпозиция сложной задачи |
| **Dialogic** | исследование через вопросы, позиции и контраргументы |
| **Conceptual** | структурирование понятий, связей и уровней |
| **Interactive** | поиск альтернатив и слепых зон |
| **Stream** | более свободное ассоциативное исследование |
| **Adaptive** | динамическое уточнение стратегии по мере развития диалога |

---

## 🧰 Технологический контекст

Проект реализован преимущественно как **declarative no-code / low-code instruction system**:

- OpenAI GPT / Custom GPT
- Prompt engineering
- Instruction architecture
- Logic-first orchestration
- Markdown
- Structured prompting
- Meta-reasoning design
- UX-навигация
- Cognitive psychology / metacognition
- Собственная DLS-нотация для prompt modules

---

## 🔍 Что исследовалось

В рамках проекта проверялись и проектировались:

- маршрутизация пользовательского запроса;
- адаптивный выбор логической стратегии;
- управление глубиной и структурой ответа;
- декомпозиция сложных задач;
- снижение prompt drift;
- фиксация цели и контекста;
- шаблонизация типов рассуждений;
- визуальная навигация;
- автоматическая адаптация оформления;
- мета-правила самопроверки;
- повторяемость поведения на разных типах запросов.

Некоторые механизмы в старой архитектуре моделировали параметры вроде `temperature`, `analysis depth`, `resources` и `thinking trace`. В текущем прочтении их следует понимать как **семантические управляющие параметры instruction layer**, а не как прямой runtime-контроль inference-параметров модели.

---

## 📌 Статус проекта

Проект сохранён как **личный R&D и исторический этап развития собственной LLM-архитектуры**.

Часть решений сегодня я бы проектировал иначе — с меньшей связностью между инструкциями, более явными контрактами модулей, внешним orchestration/runtime layer и независимыми eval-наборами. Однако сам репозиторий сохраняет ценность как эксперимент по модульному управлению LLM до перехода к более зрелым agentic / workflow-подходам.

---

## 📸 Фотогалерея

> Скриншоты и результаты тестирования относятся к разным версиям системы и сохранены как исторические материалы.

### Знакомство

<p float="left">
  <img src="https://github.com/user-attachments/assets/04c8606b-cc2c-40dc-a8e7-920a720a83a3" width="32%" />
  <img src="https://github.com/user-attachments/assets/51bcd42b-7ceb-4078-8ab7-64349f4705cf" width="32%" />
  <img src="https://github.com/user-attachments/assets/1da9957b-3fb4-4638-9d9e-8440a9ab9c11" width="32%" />
</p>

---

### Примеры использования

<p float="left">
  <img src="https://github.com/user-attachments/assets/67db0396-5efa-4983-acfc-70cedb7e17df" width="32%" />
  <img src="https://github.com/user-attachments/assets/53052e54-6939-4a4b-b367-ed175dcca88f" width="32%" />
  <img src="https://github.com/user-attachments/assets/0fb1375f-8ab4-4fe2-b2d3-958d068d8d2d" width="32%" />
</p>

> Общие примеры. Старая архитектура.

<p float="left">
  <img src="https://github.com/user-attachments/assets/1965622a-ec6c-4538-83f1-3a2173948563" width="32%" />
  <img src="https://github.com/user-attachments/assets/1a992134-b2b5-44d6-b8da-eac22935e9a6" width="32%" />
  <img src="https://github.com/user-attachments/assets/15a3af05-b9d4-4159-a687-f82542993baf" width="32%" />
</p>

> Пример проектирования персонального курса обучения английскому.

<p float="left">
  <img src="https://github.com/user-attachments/assets/5ad0e647-da73-4561-8bd6-0c337ca059d8" width="32%" />
  <img src="https://github.com/user-attachments/assets/26468373-e3d1-46e4-b2a3-6052101d1d75" width="32%" />
  <img src="https://github.com/user-attachments/assets/97d8460b-21bb-4a91-a87e-e477f75fb961" width="32%" />
</p>

> Пример работы при минимально детализированном пользовательском prompt.

---

### Тестирование и сравнительный анализ 1

<p float="left">
  <img src="https://github.com/user-attachments/assets/41ab7793-2705-4b0d-b39c-5f56d95c5cb2" width="32%" />
  <img src="https://github.com/user-attachments/assets/9a2847a3-a8c8-4406-bc22-836af4d95b36" width="32%" />
  <img src="https://github.com/user-attachments/assets/a60c5fe0-1443-41cc-b2e0-01f68926a03a" width="32%" />
</p>

<p float="left">
  <img src="https://github.com/user-attachments/assets/571cb2b4-f3ef-4e58-83bd-90fe99ab1f18" width="19%" />
  <img src="https://github.com/user-attachments/assets/5a7c4f59-782c-4964-8817-af0f7edf7d2d" width="19%" />
  <img src="https://github.com/user-attachments/assets/e5afee30-12ad-4149-868b-06d60286ea4c" width="19%" />
  <img src="https://github.com/user-attachments/assets/91d6bdd8-b84a-41ce-a804-cc3252e33d98" width="19%" />
  <img src="https://github.com/user-attachments/assets/e5850328-c23b-4625-be7d-eb8687db3d6f" width="19%" />
</p>

---

### Тестирование и сравнительный анализ 2

> Историческое сравнение одной из специализированных конфигураций `Education Machine` с режимом «Учёба» в GPT-5.

<p float="left">
  <img src="https://github.com/user-attachments/assets/47cdd904-6a4e-4b9d-b256-09c65b96f176" width="49%" />
  <img src="https://github.com/user-attachments/assets/b1cbf4cb-00a1-43c2-8290-bf6494fa52a4" width="49%" />
</p>

> GPT-5 в режиме «Учёба».

<p float="left">
  <img src="https://github.com/user-attachments/assets/92d4d321-253e-44fd-939d-05c80a7abf93" width="31%" />
  <img src="https://github.com/user-attachments/assets/68d65b02-0f24-45cc-9f2c-70c3dc00e857" width="31%" />
  <img src="https://github.com/user-attachments/assets/f681c023-2b93-4c75-8655-c19782b6e969" width="31%" />
</p>

> `Education Machine` + GPT-5.

<p float="left">
  <img src="https://github.com/user-attachments/assets/9a1ff67f-800d-4466-a38a-34f49ea3e360" width="31%" />
  <img src="https://github.com/user-attachments/assets/76d3fa98-b67f-4b4b-a9a6-351f5e8c8512" width="31%" />
  <img src="https://github.com/user-attachments/assets/c5a6e2a6-b0f2-4b6b-b552-0b72a1e61870" width="31%" />
</p>

> `Education Machine` + o3.

<p float="left">
  <img src="https://github.com/user-attachments/assets/0ddb13d9-5c1e-487c-b6ef-7bd37905270d" width="31%" />
  <img src="https://github.com/user-attachments/assets/07429d95-0561-4876-806d-98cdbb062a6c" width="31%" />
  <img src="https://github.com/user-attachments/assets/d8de1859-1e5b-4ca6-9c58-6c0a25700d2e" width="31%" />
</p>

> `Education Machine` + GPT-4o.

---

### Тестирование и сравнительный анализ 3

<p float="left">
  <img src="https://github.com/user-attachments/assets/6cedd4fe-9a6f-49ef-bcb2-5d189b44fc90" width="31%" />
  <img src="https://github.com/user-attachments/assets/70d91ea1-3027-4b86-b6f5-7f36f19a317f" width="31%" />
  <img src="https://github.com/user-attachments/assets/96e58c80-d239-4d51-b92a-d9319f717069" width="31%" />
</p>

> Базовая GPT без Meta Machine.

<p float="left">
  <img src="https://github.com/user-attachments/assets/5db5e9b5-42c3-41d8-973f-ce2dbda24281" width="24%" />
  <img src="https://github.com/user-attachments/assets/30e1c9da-1449-474a-925f-7cb9a492a793" width="24%" />
  <img src="https://github.com/user-attachments/assets/c6f41067-4b78-4a0f-bb5e-25b0348689a0" width="24%" />
  <img src="https://github.com/user-attachments/assets/d430768e-192f-489b-9fdd-a041001c228f" width="24%" />
</p>

> Meta Machine. Старая архитектура.

---

### Другие работы

<p float="left">
  <img src="https://github.com/user-attachments/assets/ac922614-4462-4302-a9fe-b67b219ccab4" width="24%" />
  <img src="https://github.com/user-attachments/assets/532756e9-1b98-4e7e-9c7b-6becb6cf6afb" width="24%" />
  <img src="https://github.com/user-attachments/assets/45177b19-78f1-40fb-9da5-434809096b32" width="24%" />
  <img src="https://github.com/user-attachments/assets/d820a308-c683-4e96-a819-3b1b18887522" width="24%" />
</p>

<p float="left">
  <img src="https://github.com/user-attachments/assets/594a942f-ca44-4722-90af-1e9640b2c06a" width="24%" />
  <img src="https://github.com/user-attachments/assets/22c446d2-6342-405a-9ce7-14abe633084c" width="24%" />
  <img src="https://github.com/user-attachments/assets/492c582d-c70e-43d6-8c3a-c48312b3f195" width="24%" />
  <img src="https://github.com/user-attachments/assets/b324c20b-df2e-4462-b9e3-8e8555a4328d" width="24%" />
</p>

<p float="left">
  <img src="https://github.com/user-attachments/assets/489b3fea-a634-4823-9bd3-78635a4de4a1" width="24%" />
  <img src="https://github.com/user-attachments/assets/8ee5a3ca-e255-4e44-b531-168c87e9c922" width="24%" />
  <img src="https://github.com/user-attachments/assets/41a40651-3ff0-41d3-80cc-560a9ce44ddc" width="24%" />
  <img src="https://github.com/user-attachments/assets/e1fe620c-6fae-47e4-8752-1c081753c2b2" width="24%" />
</p>

<p float="left">
  <img src="https://github.com/user-attachments/assets/c40693f5-fd29-4d4c-8d2f-08fda7c6984b" width="24%" />
  <img src="https://github.com/user-attachments/assets/aa0c42bc-2c0c-4467-bbf2-6a50df9bc4ef" width="24%" />
  <img src="https://github.com/user-attachments/assets/3bea75d5-9652-4772-ac44-3cb4c729f98c" width="24%" />
  <img src="https://github.com/user-attachments/assets/cff7c12a-d88a-477c-93b9-6a4eed017963" width="24%" />
</p>

> Изображения относятся к старым версиям архитектуры. Актуальные на момент завершения проекта версии отдельно не документировались.

---

## R&D focus

**Cognitive Systems Design · Prompt Systems Architecture · LLM Interaction Design**

Personal R&D project.
