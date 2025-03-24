# Настраиваем VSCode как у Миши

- `extensions.txt` — устанавливаем плагины.
- `keybindings.json` — биндим хоткеи.
- `settings.json` — настраиваем vscode.

## Установливаем плагины (автоматически)

1. Открываем терминал.
2. Вбиваем:

  ```bash
  cat extensions.txt | xargs -L 1 code --install-extension
  ```

