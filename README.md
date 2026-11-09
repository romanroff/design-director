# Design Director для Codex

`design-director` ведёт проект от дизайн-брифа до проверки сайта в браузере. Для нового сайта Codex уточняет задачу, показывает визуальные референсы, сравнивает несколько концепций и согласует прототип перед реализацией. Для редизайна, отдельного компонента и визуального аудита предусмотрены сокращённые маршруты.

## Установка

Репозиторий приватный. Для клонирования войдите в GitHub под аккаунтом, у которого есть доступ. Если Git ещё не настроен для работы с GitHub, выполните `gh auth login` и `gh auth setup-git` с установленным GitHub CLI.

**Windows (PowerShell).** Чтобы установить навык для всех проектов, выполните:

```powershell
git clone https://github.com/romanroff/design-director.git
$skillsDir = Join-Path $HOME '.agents/skills'
New-Item -ItemType Directory -Force -Path $skillsDir | Out-Null
Copy-Item -Recurse -Path ./design-director/skills/design-director -Destination $skillsDir
```

**macOS и Linux.** Чтобы установить навык для всех проектов, выполните:

```bash
git clone https://github.com/romanroff/design-director.git
mkdir -p "$HOME/.agents/skills"
cp -R ./design-director/skills/design-director "$HOME/.agents/skills/"
```

Для установки в один проект скопируйте всю папку `skills/design-director` из клона в `.agents/skills/` в корне целевого проекта. Должен получиться путь `.agents/skills/design-director/SKILL.md`.

В новом чате Codex вызовите `$design-director`. Если навык не появился в списке, перезапустите Codex.

[Документация OpenAI по навыкам Codex](https://learn.chatgpt.com/docs/build-skills)

## Примеры запросов

```text
Используй $design-director. Хочу сайт для керамической мастерской. Начни с опроса и покажи визуальные референсы.

Используй $design-director. Переработай первый экран текущего лендинга. Сохрани бренд и основное действие. Дойди до макета.

Используй $design-director. Проведи визуальный аудит страницы каталога на desktop и mobile. Верни список проблем со скриншотами.

Используй $design-director. Собери лендинг по приложенному брифу. Выбери концепцию самостоятельно и доведи работу до проверенного сайта.
```

Codex предлагает варианты ответа через встроенный опрос, если текущий клиент его поддерживает, или прямо в чате. Для визуального сравнения он может собрать локальную HTML-галерею. Откройте её в браузере, выберите варианты и скачайте JSON. Прикрепите файл к сообщению или укажите Codex путь к нему. Можно ответить в чате номерами вариантов и своими комментариями.

Галерея работает без сервера и установки пакетов. Поиск, создание изображений, браузерная проверка и делегирование зависят от инструментов текущей сессии. При недоступности субагентов Codex проходит роли последовательно.

## Состав

- [SKILL.md](skills/design-director/SKILL.md) задаёт маршруты, роли и контрольные точки.
- [references](skills/design-director/references/) содержит протоколы опроса, проектирования, визуального ревью и передачи решений.
- [gallery.html](skills/design-director/assets/gallery.html) — шаблон интерактивного сравнения референсов и прототипов.
