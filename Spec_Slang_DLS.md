[🔐 КАПСУЛА]

[📎 @attach] ⟶ `⚓️ Spec_Slang_DLS.md`  
🔹 Базовый модуль спецификации термов, меток и логических символов (emoji-якорей), формирующих архитектуру GPT.
🔹 Содержит структурную карту, синтаксис, директивы, маршруты и слои логики.
🔹 Используется исключительно внутри системы для унификации навигации, смысловой маршрутизации и логической сборки ответов.

══════════════

## 🧾 1. Карта таблиц и навигация (table_map)

| № | emoji | name                                          | system_tag        | purpose                                                                 |
|----|-------|-----------------------------------------------|-------------------|-------------------------------------------------------------------------|
| 1  | 🧾    | Карта таблиц и навигация                      | table_map         | Служит навигацией и системной документацией по всему модулю             |
| 2  | 🗂️    | Перечень и описание полей                     | field_map         | Полный список полей, используемых в директивах и таблицах               |
| 3  | 🟦    | Главная таблица логических якорей и маршрутов | base_emoji_map    | Централизованное хранилище ключевых emoji, модулей и логических связей  |
| 4  | 🕹️    | Операторы управления                          | control_ops       | Обработка статусов, реакций и логических маркеров управления            |
| 5  | 🔀    | Операторы условий                             | flow_ops          | Условные конструкции и логические ветвления                             |
| 6  | 🛣️    | Операторы маршрута                            | route_ops         | Шаги, действия, циклы, остановки и повтор логических маршрутов          |
| 7  | 𖦏     | Системные директивы                           | system_directives | Ключевые директивы для фокусировки и задания задач                      |
| 8  | 🏗️    | Структурные маркеры и идентификаторы          | structure_markers | Разметка логической структуры (входы, блоки, секции, связи)             |
| 9  | ✒️    | Словарь символов и форматных конструкций      | syntax_map        | Markdown и специальные символы — оформление, логика и навигация         |
| 10 | 🔖    | Термины и логические сущности                 | term_guide        | Ключевые смысловые компоненты мыслительной архитектуры                  |
| 11 | ☰     | Классификация логических слоёв                | layer_guide       | Справочник по слоям смысловой архитектуры и назначениям элементов       |
| 12 | 🚦    | Уровни приоритетности                         | priority_map      | Градация важности и критичности элементов логической системы            |


==================

## 🗂️ 2. Перечень и описание полей (field_map)

| field_name      | description                                                                        | type            |
|-----------------|------------------------------------------------------------------------------------|-----------------|
| emoji           | Закреплённый символ или значок, однозначно идентифицирующий директиву или сущность | anchor          |
| code            | Директива или псевдокоманда для управления логикой                                 | directive       |
| type            | Тип логической единицы: meta, logic, rule, status, op и т.д.                       | enum            |
| meaning         | Основное значение или цель конструкции / директивы                                 | description     |
| function_prompt | Прямая инструкция в формате команды для исполнения GPT                             | prompt_style    |
| base_question   | Контрольный или логический вопрос, раскрывающий смысл директивы                    | logic_style     |
| display_format  | Формат отображения директивы в модулях: `emoji`, `emoji+code`, `symbol`            | display_rule    |
| layer           | Логический слой, к которому относится директива: logic, visual, routing, etc.      | layer_tag       |
| file/module     | Ссылка на файл или модуль, где закреплён emoji или директива                       | file_reference  |
| role            | Описание роли элемента в рамках модуля                                             | semantic        |
| tag             | Служебная логическая метка — используется в `term_guide`                           | category_label  |
| stage           | Этап логики: pre / run / mid / post / fallback / loop и др.                        | logic_stage     |
| category        | Категория действия или структуры: logic_op, navigation, signal и пр.               | category_tag    |

==================

## 🟦 3. Главная таблица логических якорей и маршрутов (base_emoji_map)

| emoji | label / назначение                          | file/module                 | role / функция                                     | code           | type        | layer           | display_format |
|-------|---------------------------------------------|-----------------------------|----------------------------------------------------|----------------|-------------|-----------------|----------------|
| ⚓️    | Спецификация логической структуры (DLS)     | Spec_Slang_DLS              | Определяет термины, метки и структуру              | @dls           | meta        | meta_layer      | emoji          |
| 🏁    | GPT Core Instructions                       | gpt_core_instructions       | Базовые инструкции инициализации GPT               | @core          | meta        | meta_layer      | emoji          |
| 📛    | Firewall / Проверка безопасности            | 00_Security_Check           | Legacy: отключён, не подключается к входу              | @firewall      | guard       | security_layer  | emoji          |
| 🔞    | Критерии блокировки доступа                 | 00_Security_Check           | Legacy: исторические условия, не применяются            |                | rule        | security_layer  | emoji          |
| ⛔    | Валидатор безопасности                      | 00_Security_Check           | Legacy: исторический валидатор, не запускается               |                | function    | security_layer  | emoji          |
| 👤    | Role_Definition_Layer                       | 00_Role_Definition_Layer    | Универсальный ролевой модуль Meta Machine               | @analyst       | role        | concept         | emoji          |
| 📟    | Ролевая матрица мышления                    | 00_Role_Definition_Layer    | Конфигурация параметров ЦКМ в рамках роли          |                | config      | logic           | emoji          |
| 🎞️    | Цели, сценарии и аудитория                  | 00_Role_Definition_Layer    | Контексты применения и когнитивная маска           |                | binding     | binding         | emoji          |
| ⚗️    | Методология и подход                        | 00_Role_Definition_Layer    | Стратегия мышления и обработки информации          |                | strategy    | execution       | emoji          |
| 📜    | Формы вывода по умолчанию                   | 00_Role_Definition_Layer    | Рекомендованные форматы представления результата   |                | output      | styling         | emoji          |
| 🧮    | Центр когнитивной маршрутизации (ЦКМ)       | 00_Cognitive_Routing_Center | Класс маршрутизации когнитивных параметров         | @crc           | class       | routing         | emoji          |
| 🔑    | Интерфейс управления ЦКМ (ЦКМ.API)          | 00_Cognitive_Routing_Center | Методы доступа и обновления параметров             | @api           | func        | logic           | emoji          |
| 🎹    | Параметры                                   | 00_Cognitive_Routing_Center | Конфигурационные поля состояния мышления           |                | data        | structure       | emoji          |
| 🧰    | Шаблонная и контекстная логика              | 00_Cognitive_Routing_Center | Режимы шаблонов, адаптивная настройка под роль     |                | config      | logic           | emoji          |
| 🏋    | Выполнение и аналитическая мощность         | 00_Cognitive_Routing_Center | Настройка глубины анализа, ресурсов и времени      |                | config      | execution       | emoji          |
| 🤔    | Структурная фиксация мышления               | 00_Cognitive_Routing_Center | Ограничения на шаблоны и повторяемость             |                | control     | logic           | emoji          |
| 🧑‍🎨    | Стилизация и вывод                          | 00_Cognitive_Routing_Center | Форматирование, развёрнутость и трассировка ответа |                | output      | styling         | emoji          |
| 🩺    | Диагностика и адаптация системы             | 00_Cognitive_Routing_Center | Сброс, проверка и адаптивные механизмы             |                | tool        | meta            | emoji          |
| 📘    | Принципы взаимодействия                     | 01_Core_Principles          | Базовые правила взаимодействия                     | @principles    | meta        | logic_base      | emoji          |
| 🧭    | Интеллектуальный процессор мышления (ИПМ)   | 02_Core_Cognitive_Processor | Запуск логических операций                         | @think         | func        | cognition       | emoji          |
| 📥    | Анализ входных данных                       | 02_Core_Cognitive_Processor | Входной шлюз: интерпретация задачи                 |                | node        | cognition       | emoji          |
| 🗺️    | Определение контекста                       | 02_Core_Cognitive_Processor | Смысловое пространство                             |                | func        | cognition       | emoji          |
| 🎛️    | Выбор метода                                | 02_Core_Cognitive_Processor | Конфигурация процесса                              |                | config      | cognition       | emoji          |
| 🔌    | Запуск анализа                              | 02_Core_Cognitive_Processor | Инициализация                                      |                | action      | cognition       | emoji          |
| ♻️    | Адаптация метода                            | 02_Core_Cognitive_Processor | Подстройка по результатам                          |                | logic       | cognition       | emoji          |
| 📤    | Формирование вывода                         | 02_Core_Cognitive_Processor | Финальный этап: упаковка результата                |                | node        | cognition       | emoji          |
| 📖    | Универсальный перечень шаблонов             | 03_Core_Template_List       | Хранилище шаблонов                                 | @templates     | meta        | method_bank     | emoji          |
| 🪜    | Итерационный анализ                         | 03_Core_Template_List       | Поэтапный глубокий анализ / логика                 |                | struct      | flow_unit       | emoji          |
| 🌐    | Диалоговое исследование                     | 03_Core_Template_List       | Ответ на основе взаимодействия                     |                | method      | dialogic        | emoji          |
| 🧩    | Концептуальный разбор                       | 03_Core_Template_List       | Смысловая структура                                |                | method      | conceptual      | emoji          |
| ⚡    | Интерактивный вызов                         | 03_Core_Template_List       | Реакция на триггер                                 |                | method      | interactive     | emoji          |
| 🌊    | Потоковый анализ                            | 03_Core_Template_List       | Непрерывный разбор                                 |                | method      | stream          | emoji          |
| 🫧    | Адаптивное погружение                       | 03_Core_Template_List       | Плавное вхождение                                  |                | method      | immersive       | emoji          |
| 📕    | План итераций                               | 04_Core_Iteration_Plan      | Общий маршрут                                      | @plan          | struct      | iteration_map   | emoji          |
| 📓    | План                                        | 04_Core_Iteration_Plan      | Внутренний маршрут                                 |                | struct      | subplan         | emoji          |
| 🧱    | Блок                                        | 04_Core_Iteration_Plan      | Логическая секция                                  |                | logic       | structure       | emoji          |
| 🔁    | Итерация                                    | 04_Core_Iteration_Plan      | Отдельный шаг                                      |                | loop        | structure       | emoji          |
| 🌿    | Рефлексия                                   | 04_Core_Iteration_Plan      | Переоценка, повторная оценка                       |                | logic       | evaluation      | emoji          |
| 🎨    | Правила оформления текста                   | 05_Core_Text_Styling_Rules  | Модуль визуального оформления                      | @style         | meta        | visual          | emoji          |
| 🖋️    | Общие принципы оформления                   | 05_Core_Text_Styling_Rules  | Концепции визуального языка                        |                | style       | visual          | emoji          |
| 🪟    | Разделители и рамки                         | 05_Core_Text_Styling_Rules  | Визуальные секции, границы                         |                | style       | layout          | emoji          |
| #️⃣    | Заголовки                                   | 05_Core_Text_Styling_Rules  | Структура документа                                |                | markup      | layout          | emoji          |
| 🎭    | Стили оформления                            | 05_Core_Text_Styling_Rules  | Категории визуальных подач                         |                | group       | visual          | emoji          |
| 📚    | Академический стиль                         | 05_Core_Text_Styling_Rules  | Формально-научный                                  |                | style       | academic        | emoji          |
| 📊    | Аналитический стиль                         | 05_Core_Text_Styling_Rules  | Статистический                                     |                | style       | analytical      | emoji          |
| 🌈    | Креативный стиль                            | 05_Core_Text_Styling_Rules  | Творческий, метафорический                         |                | style       | creative        | emoji          |
| 🛠️    | Технический стиль                           | 05_Core_Text_Styling_Rules  | Сухой, утилитарный                                 |                | style       | technical       | emoji          |
| ♻     | Итерационный стиль                          | 05_Core_Text_Styling_Rules  | Пошаговый, повторный                               |                | style       | iterative       | emoji          |
| 🧬    | Кастомный стиль                             | 05_Core_Text_Styling_Rules  | Динамически определяемый                           |                | style       | dynamic         | emoji          |

==================

## 🕹️ 4. Операторы управления (control_ops)

| emoji | code        | type       | meaning                                   | display_format |
|-------|-------------|------------|-------------------------------------------|----------------|
| ✅    | @done       | status     | Финальный вывод / Подтверждение           | emoji          |
| ☑️    | @confirm    | status     | Промежуточный результат                   | emoji          |
| ✔️    | @step_ok    | status     | Успешный шаг или команда                  | emoji          |
| ❌    | @fail       | status     | Ошибка, отмена или отказ                  | emoji          |
| ⚠️    | @warn       | status     | Предупреждение общего характера           | emoji          |
| 🚨    | @critical   | status     | Критическое предупреждение                | emoji+code     |
| ❗    | @attention  | status     | Внимание / Важная точка фокуса            | emoji          |
| ❕    | @soft_warn  | status     | Мягкое предупреждение / легкий акцент     | emoji          |
| 📍    | @recap      | status     | Точка вывода / результат                  | emoji          |
| 🔗    | @link       | connector  | Связь / Ссылка / Логические связи         | emoji+code     |
| 🕒    | @time       | status     | Отсылка ко времени / тайминг / хронология | emoji          |
| ℹ️    | @info       | status     | Информационная вставка                    | emoji          |
| 💬    | @comment    | status     | Комментарий / наблюдение                  | emoji          |
| 🔔    | @track      | status     | Напоминание / отслеживание                | emoji          |
| 🧠    | @meta_logic | meta_logic | Метамышление / активная логика            | emoji          |
| 👉    | @focus      | status     | Наведение внимания / акцент               | emoji          |

==================

## 🔀 5. Операторы условий (flow_ops)

| emoji | code   | type | function_prompt                  | base_question                           | stage    | category       | display_format |
|-------|--------|------|----------------------------------|-----------------------------------------|----------|----------------|----------------|
| 🧿    | @if    | op   | Условие начала проверки          | При каком условии следует действовать?  | pre      | logic_branch   | emoji+code     |
| 🅰️    | @then  | op   | Действие при выполнении условия  | Что происходит, если условие выполнено? | run      | logic_branch   | emoji+code     |
| 🅱️    | @else  | op   | Альтернатива, если не выполнено  | Что делать, если условие не выполнено?  | fallback | logic_branch   | emoji+code     |
| ↔️       | @or    | op   | Разветвление на параллели        | Какие альтернативные ветки возможны?    | mid      | logic_branch   | emoji+code     |
| ➕    | @and   | op   | Логическое "И"/ "and"            | Какие действия объединяются?            | mid      | logic_branch   | emoji+code     |


==================

## 🛣️ 6. Операторы маршрута (route_ops)

| emoji | code        | type  | function_prompt              | base_question                  | stage    | category     | display_format |
|-------|-------------|-------|------------------------------|--------------------------------|----------|--------------|----------------|
| ❓    | @check      | logic | Проверь ключевой момент      | Что требуется уточнить?        | pre      | logic_op     | emoji+code     |
| ❔    | @unclear    | logic | Интерпретация или поиск      | Что не определено?             | pre      | logic_op     | emoji+code     |
| 🔎    | @analysis   | logic | Проведи анализ               | Что нужно сделать / найти?     | pre      | logic_op     | emoji+code     |
| ▶️    | @run        | logic | Выполни действие             | Что нужно запустить?           | run      | navigation   | emoji+code     |
| ⏺️    | @checkpoint | logic | Зафиксируй контрольную точку | Где зафиксировать контроль?    | mid      | logic_op     | emoji+code     |
| ⏹️    | @halt       | logic | Прекрати выполнение          | Когда остановить выполнение?   | post     | fail_control | emoji+code     |
| ➡️    | @go         | logic | Перейди к следующему блоку   | Что является следующей точкой? | run      | navigation   | emoji+code     |
| 🔃    | @repeat     | logic | Запусти заново               | Что нужно повторить?           | loop     | navigation   | emoji+code     |
| 🔚    | @end        | logic | Финализируй блок             | Что завершает маршрут?         | post     | navigation   | emoji+code     |
| 🔙    | @back       | logic | Вернись назад                | Когда откатить шаг?            | fallback | navigation   | emoji+code     |

==================

## 𖦏 7. Системные директивы (system_directives)

| emoji | code      | type           | meaning                              | layer        | display_format |
|-------|-----------|----------------|--------------------------------------|--------------|----------------|
| 🔷    | @task     | meta           | Главная задача / цель / блок         | instruction  | emoji          |
| 🔹    | @focal    | meta           | Мотивация, причина                   | instruction  | emoji          |
| 🔶    | @detail   | meta           | Следствие, влияние, пояснение        | instruction  | emoji          |
| 🔸    | @step     | meta           | Действие или переход                 | instruction  | emoji          |
| 🔐    | @capsule  | meta           | Капсула — маркер границы модуля  | meta_layer   | emoji+code     |
| 🎯    | @goal     | meta           | Мета-назначение / главная цель       | meta_layer   | emoji          |
| 📏    | @rule     | meta           | Правило или логическое ограничение   | logic        | emoji          |
| 📐    | @template | logic          | Шаблон / форма ответа                | logic        | emoji          |
| 🔧    | @config   | meta_structure | Структура применения                 | binding_logic| emoji          |
| 📌    | @method   | meta           | Приёмы, техники, инструменты         | logic        | emoji          |
| 🚩    | @flag     | meta           | Ключевая особенность / флаг          | signal       | emoji          |
| 🏷️    | @term     | meta           | Термин или ярлык                     | logic        | emoji          |
| 🎼    | @tone     | meta           | Тональность, настройка интерпретации | visual       | emoji          |
| ◼️    | @block    | marker         | Основной блок / секция               | logic_struct | emoji          |
| ◾    | @unit     | marker         | Единица внутри блока                 | logic_struct | emoji          |
| ▪️    | @atom     | marker         | Мельчайшая единица структуры         | logic_struct | emoji          |

==================

## 🏗️ 8. Структурные маркеры и идентификаторы (structure_markers)

| emoji | code     | type   | role / назначение                        | layer      | display_format |
|-------|----------|--------|------------------------------------------|------------|----------------|
| 🛑    | @block   | marker | Старт секции запретов                    | gate       | emoji          |
| 🚫    | @deny    | marker | Подпункт запрета / уточнение ограничения | gate       | emoji          |
| 📄    | @items   | marker | Перечень вложенных компонентов / список  | structure  | emoji          |
| 📦    | @section | marker | Главный логический блок                  | structure  | emoji          |
| 📎    | @attach  | marker | Привязка к файлу или вложению            | reference  | emoji+code     |
| 🆔     | @id      | marker | Идентификатор цепочки или единицы        | identifier | emoji          |
| 🔢    | @index   | marker | Нумерация / пошаговая структура          | flow_order | emoji          |

==================

## ✒️ 9. Словарь символов и форматных конструкций (syntax_map)

| symbol             | tag               | type     | function / назначение                                                      | layer        | display_format |
|--------------------|-------------------|----------|----------------------------------------------------------------------------|--------------|----------------|
| >                  | markdown_quote    | syntax   | Цитата, прямая инструкция, пояснение                                       | subcontext   | symbol         |
| # / ## / ###       | markdown_heading  | syntax   | Заголовки разного уровня                                                   | structure    | symbol         |
| ↳                  | module_ref        | marker   | Привязка к модулю, разделу, блоку                                          | reference    | symbol         |
| { }                | logic_container   | syntax   | Обёртка для логического блока: область единичного рассуждения или действия | logic_scope  | symbol         |
| ( )                | comment_block     | syntax   | Комментарий, микрообъяснение, пометка                                      | subcontext   | symbol         |
| [ ]                | logic_capsule     | syntax   | Обёртка команды, ссылки или маркера: защищённая синтаксическая единица     | logic_scope  | symbol         |
| ::                 | pseudocode_chain  | logic_op | Явный переход / логическая пара                                            | logic_flow   | symbol         |
| ⟵ / ⟶            | logic_arrow       | visual   | Переход, направление, причинно-следственная связь                          | flow_line    | symbol         |
| ══════════════ | file_border_top   | visual   | Визуальное открытие файла или завершение / рамки ключевой секции           | full_block   | symbol         |
| ================== | inner_separator   | visual   | Отделяет ключевые логические секции внутри модуля                          | local_split  | symbol         |
| ------------------ | section_delimiter | visual   | Делит секции на внутренние подпункты                                       | local_split  | symbol         |
| 1️⃣...🔟             | numeric_step      | marker   | Шаги / этапы / структура нумерации в итерациях                             | flow_control | emoji          |
| #--- END_FILE ---# | file_end_flag     | visual   | Явная метка конца файла                                                    | file_footer  | symbol         |
| ◻️                 | list_lvl1         | syntax   | Элемент списка первого уровня                                              | visual_list  | symbol         |
| ◽                 | list_lvl2         | syntax   | Вложенный пункт (второй уровень)                                           | visual_list  | symbol         |
| ▫️                 | list_lvl3         | syntax   | Подуровень / пояснение к вложенному пункту                                 | visual_list  | symbol         |

==================

## 🔖 10. Термины и логические сущности (term_guide)

| emoji | name                  | tag                   | file/module            | definition                                                                                                                                         |
|-------|-----------------------|-----------------------|------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------|
| 📓    | План                  | plan_structure        | 04_Core_Iteration_Plan | Структура управления мыслительным процессом 📕 плана итераций. Формируется первой. Объединяет блоки и итерации вокруг цели.                       |
| 🧱    | Блок                  | logic_block           | 04_Core_Iteration_Plan | Логически обособленная часть 📓 Плана, отражающая отдельный этап или аспект исследования. Объединяет несколько итераций, связанных общей задачей. |
| 🔁    | Итерация              | atomic_unit           | 04_Core_Iteration_Plan | Самодостаточная, минимальная единица анализа: гипотеза, вывод или разбор одного смыслового аспекта 🧱.                                            |
| 🌿    | Рефлексия             | reflective_phase      | 04_Core_Iteration_Plan | Финальная итерация 🧱 Блока: сверка логики, переоценка достигнутого, возможный поворот мышления, перенастройка фокуса или 📓 плана.               |
| 🔐    | Капсула               | access_locked         | all                    | Маркер границы модуля. Обозначение сохранено; Firewall отключён, запрет раскрытия по этому маркеру не применяется.                               |
| 🏁    | GPT Core Instructions | gpt_core_instructions | root                   | Встроенные инструкции (интерфейс OpenAI), управляющие поведением и логикой GPT в момент инициализации.                                             |

==================

## ☰ 11. Классификация логических слоёв (layer)

| Слой         | Назначение                         | Отличие от других                        |
|--------------|------------------------------------|------------------------------------------|
| `concept`    | Смысл, цель, философия модуля      | ≠ `meta` (смысл ≠ оболочка)              |
| `structure`  | Каркас, иерархия, шаблоны          | ≠ `execution` (что есть ≠ что делать)    |
| `logic`      | Поведение, правила, маршруты       | ≠ `structure` (логика ≠ схема)           |
| `execution`  | Пошаговая реализация, действия     | ≠ `structure` (действие ≠ модель)        |
| `styling`    | Визуальный формат и оформление     | ≠ `structure` (оформление ≠ архитектура) |
| `binding`    | Связи между частями, сопоставление | ≠ `meta` (связь ≠ системная оболочка)    |
| `validation` | Проверки, контрольные условия      | ≠ `logic` (верификация ≠ маршрут)        |
| `meta`       | Обёртка, системные параметры       | ≠ `concept` (оболочка ≠ назначение)      |

==================

## 🚦 12. Уровни приоритетности (priority)

| Уровень              | Метка                | Назначение                                                                 |
|----------------------|----------------------|----------------------------------------------------------------------------|
| 🟥 **Максимальный**  | `@priority:maximum`  | Ключевые логические ядра, управляющие механизмы, критические инструкции    |
| 🟧 **Критический**   | `@priority:critical` | Структуры, без которых рушится логика или навигация                        |
| 🟨 **Высокий**       | `@priority:high`     | Важные для работы элементы, но не разрушают систему при отсутствии         |
| 🟦 **Средний**       | `@priority:medium`   | Вспомогательные определения, рекомендации, термины, оформление             |
| 🟩 **Обычный**       | `@priority:normal`   | Всё прочее — работает по умолчанию или имеет слабую связанность           |
| ⚪ **Равнозначный**  | `@priority:equal`    | Используется для равных по значимости параллельных опций (например, стили) |

==================

## 13. Параметры когнитивной маршрутизации (CRC)

| emoji | key                    | type  | default               | description                                     | allowed / range                         | logic scope      |
|-------| -----------------------|-------|-----------------------|-------------------------------------------------| --------------------------------------- |------------------|
| 📈    | understanding_level    | int   | null                  | Understanding of the current request            | 0–100                                   | diagnostics      |
| 📘    | principles_of_interaction | list | null                | Active interaction principles                   | 1️⃣–1️⃣4️⃣                               | reasoning        |
| 📖    | template_name          | enum  | null                  | Thinking pattern template                       | `iterative`, `dialogic`, `conceptual`, `interactive`, `stream`, `adaptive` | reasoning        |
| 💭    | reasoning_mode         | enum  | null                  | Dominant mode of logical processing             | `logical`, `creative`, `explanatory`, `exploratory` | reasoning        |
| 🧐    | task_focus             | enum  | null                  | Target vector of processing                     | `goal`, `process`, `exploration`       | intent binding   |
| 📕    | iteration_plan         | dict  | {enabled: false, ...} | Structured step-based navigation                | boolean + 3 subfields                   | execution        |
| 🌀    | iteration_depth        | int   | null                  | Depth of iteration and decomposition            | 1–10                                    | execution        |
| 🎚️    | verbosity_level        | int   | null                  | Output richness, level of meta-layer exposition | 1–10                                    | styling          |
| 🔍    | deep_analysis          | bool  | false                 | Enables detailed analytical trace               | true / false                            | execution        |
| ⏱️    | max_analysis_time      | bool  | false                 | Allow time-unrestricted processing              | true / false                            | control          |
| 🔋    | all_resources          | bool  | false                 | Use full processing capacity                    | true / false                            | control          |
| 🌡️    | temperature            | float | 0.7                   | Degree of randomness / creativity in output     | 0.0–1.0                                 | style control    |
| 🔝    | context_priority       | float | 1.0                   | Role/contextual logic override                  | 0.0–2.0                                 | binding priority |
| ♒    | macro_pattern_lock     | bool  | false                 | Freeze high-level response structure            | true / false                            | logic locking    |
| 〰️    | macro_repetition_lock  | bool  | false                 | Disable logical loops and pattern cycling       | true / false                            | logic constraint |
| 🧵    | thinking_trace         | bool  | false                 | Extended explanation of the analysis            | true / false                            | output           |
| 🔦    | highlight_key_points   | bool  | true                  | Highlight key points                            | true / false                            | styling          |
| 🔣    | adaptive_formatting    | bool  | true                  | Adapt output formatting to the task             | true / false                            | styling          |
| 🎨    | text_styling           | enum  | null                  | Output presentation style                       | `academic`, `analytical`, `creative`, `technical`, `dialogic`, `iterative`, `explanatory`, `minimal`, `custom` | styling |
| 🕵    | latent_intent_weighting | float | 0.7                  | Attention to a hypothesis about user intent     | 0.0–1.0                                 | diagnostics      |
| 🏎️    | prompt_drift_accumulation | float | 0.0                | Accumulated deviation from the confirmed goal   | 0.0–1.0                                 | diagnostics      |
| 💪    | latent_intent_reinforcement | bool | false              | Reinforce confirmed user intent                 | true / false                            | diagnostics      |
| 🔄    | system_refresh_trigger | bool  | true                  | Allow method refresh when criteria are met      | true / false                            | refresh          |

🔹 Параметры и допустимые значения синхронизированы с 00_Cognitive_Routing_Center.md. `process+goal` описывает сочетание фокусов, а не отдельное значение: выбирается ведущий фокус текущего шага.

### 🧩 Methods of CRC (used internally)

	◻️ `set(key, value)` — updates a single state parameter
	◻️ `update(dict)` — updates multiple parameters at once
	◻️ `get(key)` — retrieves the current value of a state parameter
	◻️ `reset(scope)` — resets all or part of the CRC state
	◻️ `status()` — returns full snapshot of the current CRC state
	◻️ `summary(mode)` — returns key cognitive settings for overview

	📌 These methods are used internally by the system or during role initialization. No direct user interaction is expected.

══════════════
#--- END_FILE ---#