## Лаборатная работа №4 — план выполнения

---

### 1. Установка ПО

```bash
sudo dnf copr enable elegos/gitflow
sudo dnf install gitflow
```

```bash
sudo dnf install nodejs pnpm
```

```bash
pnpm setup
source ~/.bashrc
```

Напиши что я уже писал pnpm setup поэтому написано что уже сделано

```bash
pnpm add -g commitizen
pnpm add -g cz-conventional-changelog
pnpm add -g standard-changelog
```

📸 **СКРИН: вывод каждой установки**

---

### 2. Создание репозитория на GitHub

Зайди на **github.com** → **New repository** → назови `git-extended` → Public → **Create repository**

📸 **СКРИН: страница созданного репозитория на GitHub**

---

### 3. Локальная инициализация

```bash
mkdir ~/git-extended
cd ~/git-extended
git init
git commit --allow-empty -m "first commit"
git remote add origin git@github.com:ТВО_ЛОГИН/git-extended.git
git push -u origin master
```

📸 **СКРИН: вывод git push**

---

### 4. Настройка conventional commits

```bash
pnpm init
```

📸 **СКРИН: вывод pnpm init**

Отвечай на вопросы: `name` → `git-extended`, `license` → `CC-BY-4.0`, остальное Enter.

Открой `package.json` любым редактором и добавь блок `"config"` так чтобы файл выглядел так:

```json
{
  "name": "git-extended",
  "version": "1.0.0",
  "description": "Git repo for educational purposes",
  "main": "index.js",
  "repository": "git@github.com:ТВО_ЛОГИН/git-extended.git",
  "author": "Имя Фамилия <email@gmail.com>",
  "license": "CC-BY-4.0",
  "config": {
    "commitizen": {
      "path": "cz-conventional-changelog"
    }
  }
}
```

📸 **СКРИН: содержимое package.json**

```bash
git add .
git cz
```

В интерактивном меню: тип → `feat`, scope → пропусти Enter, description → `add package.json`, остальное Enter.

📸 **СКРИН: заполненный интерфейс git cz**

```bash
git push
```

📸 **СКРИН: вывод git push**

---

### 5. Инициализация git-flow

```bash
git flow init
```

На все вопросы жми Enter, только на `Version tag prefix` введи `v`.

📸 **СКРИН: вывод git flow init**

```bash
git branch
```

📸 **СКРИН: вывод git branch (должна быть активна develop)**

```bash
git push --all
git branch --set-upstream-to=origin/develop develop
```

📸 **СКРИН: git push --all и тд**

---

### 6. Релиз 1.0.0

```bash
git flow release start 1.0.0
```

📸 **СКРИН: вывод команды**

```bash
standard-changelog --first-release
git add CHANGELOG.md
git commit -am 'chore(site): add changelog'
```

📸 **СКРИН: вывод cat CHANGELOG.md**

```bash
git flow release finish 1.0.0
```

Откроется редактор для сообщения тега — просто сохрани и закрой (`Esc` → `:wq` → Enter если vim, `Ctrl+X` → `Y` → Enter если nano).

📸 **СКРИН: вывод git flow release finish**

```bash
git push --all
git push --tags
gh release create v1.0.0 -F CHANGELOG.md
```

📸 **СКРИН: вывод команд**

Открыть github и перейти в релизы
📸 **СКРИН: страница релизов на GitHub (вкладка Releases)**

---

### 7. Feature-ветка

```bash
git flow feature start feature_branch
```

📸 **СКРИН: вывод команды**

```bash
echo "# New feature" > feature.md
git add feature.md
git cz
```

Тип → `feat`, description → `add feature file`, остальное Enter.

📸 **СКРИН: git cz в процессе**

```bash
git flow feature finish feature_branch
```

📸 **СКРИН: вывод feature finish**

---

### 8. Релиз 1.2.3

```bash
git flow release start 1.2.3
```

📸 **СКРИН: вывод команды**

Открой `package.json` и измени `"version": "1.0.0"` на `"version": "1.2.3"`.

📸 **СКРИН: обновлённый package.json**

```bash
standard-changelog
git add CHANGELOG.md
git commit -am 'chore(site): update changelog'
```

📸 **СКРИН: вывод cat CHANGELOG.md**

```bash
git flow release finish 1.2.3
```

Снова сохрани редактор.

📸 **СКРИН: вывод release finish**

```bash
git push --all
git push --tags
gh release create v1.2.3 -F CHANGELOG.md
```

📸 **СКРИН: вывода этих команд**

Переход на github релизы

📸 **СКРИН: страница релизов на GitHub — должны быть оба релиза v1.0.0 и v1.2.3**
