<div align="center">

# 🧠 Family Meta Machine

**Семейство Custom GPT с общим протоколом диалога**

Уточнение цели, выбор стратегии и пошаговый разбор с участием пользователя.

![Custom GPT](https://img.shields.io/badge/Custom_GPT-412991?style=flat-square)
![Markdown](https://img.shields.io/badge/Markdown-181717?style=flat-square&logo=markdown)
![DLS](https://img.shields.io/badge/DLS-авторская_нотация-5267A5?style=flat-square)

[Открыть сайт](https://meta-machine.vercel.app/#home) · [Инструкции и FAQ](https://meta-machine.vercel.app/#guide) · [Архитектура](https://meta-machine.vercel.app/#architecture) · [Примеры диалогов](#примеры-диалогов)

</div>

<p align="center">
  <a href="https://github.com/user-attachments/assets/d05b6026-9d6d-4213-9de4-3f27457a19a9"><img src="https://github.com/user-attachments/assets/d05b6026-9d6d-4213-9de4-3f27457a19a9" alt="Историческая схема модулей и маршрута запроса Meta Machine" width="100%" /></a>
</p>

<p align="center"><sub>Модули и маршрут запроса Meta Machine</sub></p>

---

## О проекте

**Family Meta Machine** — авторский эксперимент по управлению поведением GPT через модульную систему инструкций. Общее ядро задаёт порядок диалога, а специализированные роли адаптируют его для обучения, исследований, проектирования и других задач.

Отправная точка — простая проблема: подробный ответ может оказаться ответом не на тот вопрос. Поэтому система сначала выясняет намерение пользователя, согласует направление и только затем переходит к содержательному разбору. В многошаговой работе пользователь управляет переходами между этапами.

| Задача | Решение в системе |
|---|---|
| Уточнить, что человек хочет получить | Обязательная проверка намерения в начале диалога, новой задачи или при смене цели |
| Выбрать подход к вопросу | Ролевой профиль и шесть шаблонов разбора |
| Удерживать направление работы | Центр когнитивной маршрутизации: цель, метод, глубина, стиль и прогресс |
| Разобрать объёмную тему по частям | Согласованный план и отдельные сообщения для итераций |
| Сделать результат удобным для чтения | Правила структуры, детализации и оформления ответа |

## Как проходит запрос

```mermaid
flowchart LR
    A["Запрос"] --> B["Уточнение и<br/>подтверждение цели"]
    B --> C["Роль и метод<br/>ЦКМ · ИПМ"]
    C --> D["Разбор и ответ"]
```

Итерационный режим предназначен уже для задач средней сложности, которые требуют нескольких содержательных сообщений. План согласуется отдельно; после каждой итерации, включая последнюю, система запрашивает подтверждение продолжения.

```mermaid
flowchart LR
    A["Согласованный план"] --> B["Одна итерация"]
    B --> C["Подтверждение<br/>пользователя"]
    C -->|Следующий этап| B
    C -->|Завершение| D["Итог"]
```

<details>
<summary><strong>Модули и исходные инструкции</strong></summary>

| Модуль | За что отвечает |
|---|---|
| [Правила запуска](00_Instructions.md) | Вход в диалог, порядок подключения компонентов и приоритет правил |
| [Ролевой профиль](00_Role_Definition_Layer.md) | Назначение роли и её исходные настройки |
| [ЦКМ — центр когнитивной маршрутизации](00_Cognitive_Routing_Center.md) | Единое состояние сессии: параметры, флаги и прогресс |
| [Принципы взаимодействия](01_Core_Principles_of_Interaction.md) | Работа с намерением, контекстом и обратной связью |
| [ИПМ — интеллектуальный процессор мышления](02_Core_Cognitive_Processor.md) | Выбор метода, организация разбора и обновление состояния |
| [Каталог шаблонов](03_Core_Template_List.md) | Шесть стратегий обработки запросов |
| [План итераций](04_Core_Iteration_Plan.md) | Декомпозиция и управляемые переходы между этапами |
| [Оформление ответа](05_Core_Text_Styling_Rules.md) | Структура текста и визуальная навигация |
| [Нотация DLS](Spec_Slang_DLS.md) | Обозначения слоёв, приоритетов, ссылок и директив |

[Исторический Firewall](00_Security_Check.md) сохранён отдельно и отключён в текущем протоколе.

</details>

## Стратегии разбора

| Стратегия | Когда полезна |
|---|---|
| Итерационный анализ | Разложить тему на этапы и последовательно проверить выводы |
| Диалоговое исследование | Сопоставить позиции, гипотезы и контраргументы |
| Концептуальный разбор | Упорядочить понятия, связи и уровни задачи |
| Интерактивный вызов | Найти альтернативы и проверить привычную точку зрения |
| Потоковый анализ | Развить ассоциации и исследовать ещё не оформленную идею |
| Адаптивное погружение | Уточнять подход по мере появления новых вводных |

## Роли и использование

На [сайте проекта](https://meta-machine.vercel.app/#home) собраны десять конфигураций Custom GPT:

| Роли | Направление |
|---|---|
| Meta Machine | Универсальная точка входа и уточнение задачи |
| Research · Sense · Analyst | Исследование, осмысление и анализ |
| Creative · Design | Идеи, концепции и проектирование |
| Code | Инженерные задачи и работа с кодом |
| Education | Обучение и персональные учебные маршруты |
| Strategy · Trader | Стратегии, сценарии и оценка рисков |

Выберите роль на сайте и откройте её в ChatGPT. Опишите задачу, ответьте на уточнение и согласуйте направление работы. Для объёмной темы система предложит план, по которому можно двигаться шаг за шагом.

## Технологии и подход

| Основа | Применение |
|---|---|
| OpenAI Custom GPT | Среда работы специализированных конфигураций |
| Markdown | Хранение и организация инструкций |
| DLS | Авторская нотация для описания правил и связей между модулями |
| Модульные инструкции | Роли, маршрутизация, шаблоны анализа и управление итерациями |

Параметры в файлах, в том числе `temperature`, глубина и ресурсы анализа, описывают желаемое поведение через инструкции. Это настройки протокола диалога, а не прямое управление вычислениями модели.

## Примеры диалогов

Материалы разработки на GPT-4o, o3 и GPT-5: знакомство с системой, учебные сценарии и сравнения ответов разных конфигураций.

### Знакомство

<table align="center" width="100%">
  <tbody>
    <tr>
      <td align="center" valign="top" width="33%"><a href="https://github.com/user-attachments/assets/04c8606b-cc2c-40dc-a8e7-920a720a83a3"><img src="https://github.com/user-attachments/assets/04c8606b-cc2c-40dc-a8e7-920a720a83a3" alt="Знакомство с Meta Machine, скриншот 1" width="100%" /></a></td>
      <td align="center" valign="top" width="33%"><a href="https://github.com/user-attachments/assets/51bcd42b-7ceb-4078-8ab7-64349f4705cf"><img src="https://github.com/user-attachments/assets/51bcd42b-7ceb-4078-8ab7-64349f4705cf" alt="Знакомство с Meta Machine, скриншот 2" width="100%" /></a></td>
      <td align="center" valign="top" width="33%"><a href="https://github.com/user-attachments/assets/1da9957b-3fb4-4638-9d9e-8440a9ab9c11"><img src="https://github.com/user-attachments/assets/1da9957b-3fb4-4638-9d9e-8440a9ab9c11" alt="Знакомство с Meta Machine, скриншот 3" width="100%" /></a></td>
    </tr>
  </tbody>
</table>



<details>
<summary><strong>Примеры использования</strong></summary>

### Общие примеры

<table align="center" width="100%">
  <tbody>
    <tr>
      <td align="center" valign="top" width="33%"><a href="https://github.com/user-attachments/assets/67db0396-5efa-4983-acfc-70cedb7e17df"><img src="https://github.com/user-attachments/assets/67db0396-5efa-4983-acfc-70cedb7e17df" alt="Общие примеры работы, скриншот 1" width="100%" /></a></td>
      <td align="center" valign="top" width="33%"><a href="https://github.com/user-attachments/assets/53052e54-6939-4a4b-b367-ed175dcca88f"><img src="https://github.com/user-attachments/assets/53052e54-6939-4a4b-b367-ed175dcca88f" alt="Общие примеры работы, скриншот 2" width="100%" /></a></td>
      <td align="center" valign="top" width="33%"><a href="https://github.com/user-attachments/assets/0fb1375f-8ab4-4fe2-b2d3-958d068d8d2d"><img src="https://github.com/user-attachments/assets/0fb1375f-8ab4-4fe2-b2d3-958d068d8d2d" alt="Общие примеры работы, скриншот 3" width="100%" /></a></td>
    </tr>
  </tbody>
</table>

### Персональный курс английского

<table align="center" width="100%">
  <tbody>
    <tr>
      <td align="center" valign="top" width="33%"><a href="https://github.com/user-attachments/assets/1965622a-ec6c-4538-83f1-3a2173948563"><img src="https://github.com/user-attachments/assets/1965622a-ec6c-4538-83f1-3a2173948563" alt="Проектирование курса английского, скриншот 1" width="100%" /></a></td>
      <td align="center" valign="top" width="33%"><a href="https://github.com/user-attachments/assets/1a992134-b2b5-44d6-b8da-eac22935e9a6"><img src="https://github.com/user-attachments/assets/1a992134-b2b5-44d6-b8da-eac22935e9a6" alt="Проектирование курса английского, скриншот 2" width="100%" /></a></td>
      <td align="center" valign="top" width="33%"><a href="https://github.com/user-attachments/assets/15a3af05-b9d4-4159-a687-f82542993baf"><img src="https://github.com/user-attachments/assets/15a3af05-b9d4-4159-a687-f82542993baf" alt="Проектирование курса английского, скриншот 3" width="100%" /></a></td>
    </tr>
  </tbody>
</table>

### Работа с кратким запросом

<table align="center" width="100%">
  <tbody>
    <tr>
      <td align="center" valign="top" width="33%"><a href="https://github.com/user-attachments/assets/5ad0e647-da73-4561-8bd6-0c337ca059d8"><img src="https://github.com/user-attachments/assets/5ad0e647-da73-4561-8bd6-0c337ca059d8" alt="Работа с минимально детализированным запросом, скриншот 1" width="100%" /></a></td>
      <td align="center" valign="top" width="33%"><a href="https://github.com/user-attachments/assets/26468373-e3d1-46e4-b2a3-6052101d1d75"><img src="https://github.com/user-attachments/assets/26468373-e3d1-46e4-b2a3-6052101d1d75" alt="Работа с минимально детализированным запросом, скриншот 2" width="100%" /></a></td>
      <td align="center" valign="top" width="33%"><a href="https://github.com/user-attachments/assets/97d8460b-21bb-4a91-a87e-e477f75fb961"><img src="https://github.com/user-attachments/assets/97d8460b-21bb-4a91-a87e-e477f75fb961" alt="Работа с минимально детализированным запросом, скриншот 3" width="100%" /></a></td>
    </tr>
  </tbody>
</table>

</details>

<details>
<summary><strong>Сравнение конфигураций и оценки ответов</strong></summary>

<table align="center" width="100%">
  <tbody>
    <tr>
      <td align="center" valign="top" width="33%"><a href="https://github.com/user-attachments/assets/41ab7793-2705-4b0d-b39c-5f56d95c5cb2"><img src="https://github.com/user-attachments/assets/41ab7793-2705-4b0d-b39c-5f56d95c5cb2" alt="Сравнение конфигураций и оценки ответов, скриншот 1" width="100%" /></a></td>
      <td align="center" valign="top" width="33%"><a href="https://github.com/user-attachments/assets/9a2847a3-a8c8-4406-bc22-836af4d95b36"><img src="https://github.com/user-attachments/assets/9a2847a3-a8c8-4406-bc22-836af4d95b36" alt="Сравнение конфигураций и оценки ответов, скриншот 2" width="100%" /></a></td>
      <td align="center" valign="top" width="33%"><a href="https://github.com/user-attachments/assets/a60c5fe0-1443-41cc-b2e0-01f68926a03a"><img src="https://github.com/user-attachments/assets/a60c5fe0-1443-41cc-b2e0-01f68926a03a" alt="Сравнение конфигураций и оценки ответов, скриншот 3" width="100%" /></a></td>
    </tr>
    <tr>
      <td align="center" valign="top" width="33%"><a href="https://github.com/user-attachments/assets/571cb2b4-f3ef-4e58-83bd-90fe99ab1f18"><img src="https://github.com/user-attachments/assets/571cb2b4-f3ef-4e58-83bd-90fe99ab1f18" alt="Сравнение конфигураций и оценки ответов, скриншот 4" width="100%" /></a></td>
      <td align="center" valign="top" width="33%"><a href="https://github.com/user-attachments/assets/5a7c4f59-782c-4964-8817-af0f7edf7d2d"><img src="https://github.com/user-attachments/assets/5a7c4f59-782c-4964-8817-af0f7edf7d2d" alt="Сравнение конфигураций и оценки ответов, скриншот 5" width="100%" /></a></td>
      <td align="center" valign="top" width="33%"><a href="https://github.com/user-attachments/assets/e5afee30-12ad-4149-868b-06d60286ea4c"><img src="https://github.com/user-attachments/assets/e5afee30-12ad-4149-868b-06d60286ea4c" alt="Сравнение конфигураций и оценки ответов, скриншот 6" width="100%" /></a></td>
    </tr>
    <tr>
      <td align="center" valign="top" width="33%"><a href="https://github.com/user-attachments/assets/91d6bdd8-b84a-41ce-a804-cc3252e33d98"><img src="https://github.com/user-attachments/assets/91d6bdd8-b84a-41ce-a804-cc3252e33d98" alt="Сравнение конфигураций и оценки ответов, скриншот 7" width="100%" /></a></td>
      <td align="center" valign="top" width="33%"><a href="https://github.com/user-attachments/assets/e5850328-c23b-4625-be7d-eb8687db3d6f"><img src="https://github.com/user-attachments/assets/e5850328-c23b-4625-be7d-eb8687db3d6f" alt="Сравнение конфигураций и оценки ответов, скриншот 8" width="100%" /></a></td>
      <td width="33%"></td>
    </tr>
  </tbody>
</table>

</details>

<details>
<summary><strong>Учебные сценарии: Education Machine и режим «Учёба»</strong></summary>

### GPT-5 в режиме «Учёба»

<table align="center" width="100%">
  <tbody>
    <tr>
      <td align="center" valign="top" width="50%"><a href="https://github.com/user-attachments/assets/47cdd904-6a4e-4b9d-b256-09c65b96f176"><img src="https://github.com/user-attachments/assets/47cdd904-6a4e-4b9d-b256-09c65b96f176" alt="GPT-5 в режиме Учёба, скриншот 1" width="100%" /></a></td>
      <td align="center" valign="top" width="50%"><a href="https://github.com/user-attachments/assets/b1cbf4cb-00a1-43c2-8290-bf6494fa52a4"><img src="https://github.com/user-attachments/assets/b1cbf4cb-00a1-43c2-8290-bf6494fa52a4" alt="GPT-5 в режиме Учёба, скриншот 2" width="100%" /></a></td>
    </tr>
  </tbody>
</table>

### Education Machine + GPT-5

<table align="center" width="100%">
  <tbody>
    <tr>
      <td align="center" valign="top" width="33%"><a href="https://github.com/user-attachments/assets/92d4d321-253e-44fd-939d-05c80a7abf93"><img src="https://github.com/user-attachments/assets/92d4d321-253e-44fd-939d-05c80a7abf93" alt="Education Machine на GPT-5, скриншот 1" width="100%" /></a></td>
      <td align="center" valign="top" width="33%"><a href="https://github.com/user-attachments/assets/68d65b02-0f24-45cc-9f2c-70c3dc00e857"><img src="https://github.com/user-attachments/assets/68d65b02-0f24-45cc-9f2c-70c3dc00e857" alt="Education Machine на GPT-5, скриншот 2" width="100%" /></a></td>
      <td align="center" valign="top" width="33%"><a href="https://github.com/user-attachments/assets/f681c023-2b93-4c75-8655-c19782b6e969"><img src="https://github.com/user-attachments/assets/f681c023-2b93-4c75-8655-c19782b6e969" alt="Education Machine на GPT-5, скриншот 3" width="100%" /></a></td>
    </tr>
  </tbody>
</table>

### Education Machine + o3

<table align="center" width="100%">
  <tbody>
    <tr>
      <td align="center" valign="top" width="33%"><a href="https://github.com/user-attachments/assets/9a1ff67f-800d-4466-a38a-34f49ea3e360"><img src="https://github.com/user-attachments/assets/9a1ff67f-800d-4466-a38a-34f49ea3e360" alt="Education Machine на o3, скриншот 1" width="100%" /></a></td>
      <td align="center" valign="top" width="33%"><a href="https://github.com/user-attachments/assets/76d3fa98-b67f-4b4b-a9a6-351f5e8c8512"><img src="https://github.com/user-attachments/assets/76d3fa98-b67f-4b4b-a9a6-351f5e8c8512" alt="Education Machine на o3, скриншот 2" width="100%" /></a></td>
      <td align="center" valign="top" width="33%"><a href="https://github.com/user-attachments/assets/c5a6e2a6-b0f2-4b6b-b552-0b72a1e61870"><img src="https://github.com/user-attachments/assets/c5a6e2a6-b0f2-4b6b-b552-0b72a1e61870" alt="Education Machine на o3, скриншот 3" width="100%" /></a></td>
    </tr>
  </tbody>
</table>

### Education Machine + GPT-4o

<table align="center" width="100%">
  <tbody>
    <tr>
      <td align="center" valign="top" width="33%"><a href="https://github.com/user-attachments/assets/0ddb13d9-5c1e-487c-b6ef-7bd37905270d"><img src="https://github.com/user-attachments/assets/0ddb13d9-5c1e-487c-b6ef-7bd37905270d" alt="Education Machine на GPT-4o, скриншот 1" width="100%" /></a></td>
      <td align="center" valign="top" width="33%"><a href="https://github.com/user-attachments/assets/07429d95-0561-4876-806d-98cdbb062a6c"><img src="https://github.com/user-attachments/assets/07429d95-0561-4876-806d-98cdbb062a6c" alt="Education Machine на GPT-4o, скриншот 2" width="100%" /></a></td>
      <td align="center" valign="top" width="33%"><a href="https://github.com/user-attachments/assets/d8de1859-1e5b-4ca6-9c58-6c0a25700d2e"><img src="https://github.com/user-attachments/assets/d8de1859-1e5b-4ca6-9c58-6c0a25700d2e" alt="Education Machine на GPT-4o, скриншот 3" width="100%" /></a></td>
    </tr>
  </tbody>
</table>

</details>

<details>
<summary><strong>Сравнение диалогов с Meta Machine и без неё</strong></summary>

### Базовая GPT

<table align="center" width="100%">
  <tbody>
    <tr>
      <td align="center" valign="top" width="33%"><a href="https://github.com/user-attachments/assets/6cedd4fe-9a6f-49ef-bcb2-5d189b44fc90"><img src="https://github.com/user-attachments/assets/6cedd4fe-9a6f-49ef-bcb2-5d189b44fc90" alt="Базовая GPT без Meta Machine, скриншот 1" width="100%" /></a></td>
      <td align="center" valign="top" width="33%"><a href="https://github.com/user-attachments/assets/70d91ea1-3027-4b86-b6f5-7f36f19a317f"><img src="https://github.com/user-attachments/assets/70d91ea1-3027-4b86-b6f5-7f36f19a317f" alt="Базовая GPT без Meta Machine, скриншот 2" width="100%" /></a></td>
      <td align="center" valign="top" width="33%"><a href="https://github.com/user-attachments/assets/96e58c80-d239-4d51-b92a-d9319f717069"><img src="https://github.com/user-attachments/assets/96e58c80-d239-4d51-b92a-d9319f717069" alt="Базовая GPT без Meta Machine, скриншот 3" width="100%" /></a></td>
    </tr>
  </tbody>
</table>

### Meta Machine

<table align="center" width="100%">
  <tbody>
    <tr>
      <td align="center" valign="top" width="33%"><a href="https://github.com/user-attachments/assets/5db5e9b5-42c3-41d8-973f-ce2dbda24281"><img src="https://github.com/user-attachments/assets/5db5e9b5-42c3-41d8-973f-ce2dbda24281" alt="Meta Machine, скриншот 1" width="100%" /></a></td>
      <td align="center" valign="top" width="33%"><a href="https://github.com/user-attachments/assets/30e1c9da-1449-474a-925f-7cb9a492a793"><img src="https://github.com/user-attachments/assets/30e1c9da-1449-474a-925f-7cb9a492a793" alt="Meta Machine, скриншот 2" width="100%" /></a></td>
      <td align="center" valign="top" width="33%"><a href="https://github.com/user-attachments/assets/c6f41067-4b78-4a0f-bb5e-25b0348689a0"><img src="https://github.com/user-attachments/assets/c6f41067-4b78-4a0f-bb5e-25b0348689a0" alt="Meta Machine, скриншот 3" width="100%" /></a></td>
    </tr>
    <tr>
      <td align="center" valign="top" width="33%"><a href="https://github.com/user-attachments/assets/d430768e-192f-489b-9fdd-a041001c228f"><img src="https://github.com/user-attachments/assets/d430768e-192f-489b-9fdd-a041001c228f" alt="Meta Machine, скриншот 4" width="100%" /></a></td>
      <td width="33%"></td>
      <td width="33%"></td>
    </tr>
  </tbody>
</table>

</details>

<details>
<summary><strong>Другие примеры работы</strong></summary>

<table align="center" width="100%">
  <tbody>
    <tr>
      <td align="center" valign="top" width="33%"><a href="https://github.com/user-attachments/assets/ac922614-4462-4302-a9fe-b67b219ccab4"><img src="https://github.com/user-attachments/assets/ac922614-4462-4302-a9fe-b67b219ccab4" alt="Другие примеры работы, скриншот 1" width="100%" /></a></td>
      <td align="center" valign="top" width="33%"><a href="https://github.com/user-attachments/assets/532756e9-1b98-4e7e-9c7b-6becb6cf6afb"><img src="https://github.com/user-attachments/assets/532756e9-1b98-4e7e-9c7b-6becb6cf6afb" alt="Другие примеры работы, скриншот 2" width="100%" /></a></td>
      <td align="center" valign="top" width="33%"><a href="https://github.com/user-attachments/assets/45177b19-78f1-40fb-9da5-434809096b32"><img src="https://github.com/user-attachments/assets/45177b19-78f1-40fb-9da5-434809096b32" alt="Другие примеры работы, скриншот 3" width="100%" /></a></td>
    </tr>
    <tr>
      <td align="center" valign="top" width="33%"><a href="https://github.com/user-attachments/assets/d820a308-c683-4e96-a819-3b1b18887522"><img src="https://github.com/user-attachments/assets/d820a308-c683-4e96-a819-3b1b18887522" alt="Другие примеры работы, скриншот 4" width="100%" /></a></td>
      <td align="center" valign="top" width="33%"><a href="https://github.com/user-attachments/assets/594a942f-ca44-4722-90af-1e9640b2c06a"><img src="https://github.com/user-attachments/assets/594a942f-ca44-4722-90af-1e9640b2c06a" alt="Другие примеры работы, скриншот 5" width="100%" /></a></td>
      <td align="center" valign="top" width="33%"><a href="https://github.com/user-attachments/assets/22c446d2-6342-405a-9ce7-14abe633084c"><img src="https://github.com/user-attachments/assets/22c446d2-6342-405a-9ce7-14abe633084c" alt="Другие примеры работы, скриншот 6" width="100%" /></a></td>
    </tr>
    <tr>
      <td align="center" valign="top" width="33%"><a href="https://github.com/user-attachments/assets/492c582d-c70e-43d6-8c3a-c48312b3f195"><img src="https://github.com/user-attachments/assets/492c582d-c70e-43d6-8c3a-c48312b3f195" alt="Другие примеры работы, скриншот 7" width="100%" /></a></td>
      <td align="center" valign="top" width="33%"><a href="https://github.com/user-attachments/assets/b324c20b-df2e-4462-b9e3-8e8555a4328d"><img src="https://github.com/user-attachments/assets/b324c20b-df2e-4462-b9e3-8e8555a4328d" alt="Другие примеры работы, скриншот 8" width="100%" /></a></td>
      <td align="center" valign="top" width="33%"><a href="https://github.com/user-attachments/assets/489b3fea-a634-4823-9bd3-78635a4de4a1"><img src="https://github.com/user-attachments/assets/489b3fea-a634-4823-9bd3-78635a4de4a1" alt="Другие примеры работы, скриншот 9" width="100%" /></a></td>
    </tr>
    <tr>
      <td align="center" valign="top" width="33%"><a href="https://github.com/user-attachments/assets/8ee5a3ca-e255-4e44-b531-168c87e9c922"><img src="https://github.com/user-attachments/assets/8ee5a3ca-e255-4e44-b531-168c87e9c922" alt="Другие примеры работы, скриншот 10" width="100%" /></a></td>
      <td align="center" valign="top" width="33%"><a href="https://github.com/user-attachments/assets/41a40651-3ff0-41d3-80cc-560a9ce44ddc"><img src="https://github.com/user-attachments/assets/41a40651-3ff0-41d3-80cc-560a9ce44ddc" alt="Другие примеры работы, скриншот 11" width="100%" /></a></td>
      <td align="center" valign="top" width="33%"><a href="https://github.com/user-attachments/assets/e1fe620c-6fae-47e4-8752-1c081753c2b2"><img src="https://github.com/user-attachments/assets/e1fe620c-6fae-47e4-8752-1c081753c2b2" alt="Другие примеры работы, скриншот 12" width="100%" /></a></td>
    </tr>
    <tr>
      <td align="center" valign="top" width="33%"><a href="https://github.com/user-attachments/assets/c40693f5-fd29-4d4c-8d2f-08fda7c6984b"><img src="https://github.com/user-attachments/assets/c40693f5-fd29-4d4c-8d2f-08fda7c6984b" alt="Другие примеры работы, скриншот 13" width="100%" /></a></td>
      <td align="center" valign="top" width="33%"><a href="https://github.com/user-attachments/assets/aa0c42bc-2c0c-4467-bbf2-6a50df9bc4ef"><img src="https://github.com/user-attachments/assets/aa0c42bc-2c0c-4467-bbf2-6a50df9bc4ef" alt="Другие примеры работы, скриншот 14" width="100%" /></a></td>
      <td align="center" valign="top" width="33%"><a href="https://github.com/user-attachments/assets/3bea75d5-9652-4772-ac44-3cb4c729f98c"><img src="https://github.com/user-attachments/assets/3bea75d5-9652-4772-ac44-3cb4c729f98c" alt="Другие примеры работы, скриншот 15" width="100%" /></a></td>
    </tr>
    <tr>
      <td align="center" valign="top" width="33%"><a href="https://github.com/user-attachments/assets/cff7c12a-d88a-477c-93b9-6a4eed017963"><img src="https://github.com/user-attachments/assets/cff7c12a-d88a-477c-93b9-6a4eed017963" alt="Другие примеры работы, скриншот 16" width="100%" /></a></td>
      <td width="33%"></td>
      <td width="33%"></td>
    </tr>
  </tbody>
</table>

</details>

## Статус

Развитие проекта приостановлено. Сохранены модульное ядро, сайт с конфигурациями Custom GPT и примеры диалогов разных этапов разработки. Исходный стиль системных файлов оставлен как часть истории эксперимента; правила запуска и связи между модулями согласованы.

[Сайт проекта](https://meta-machine.vercel.app/#home) · [Подробная архитектура](https://meta-machine.vercel.app/#architecture) · [Инструкции и FAQ](https://meta-machine.vercel.app/#guide)
