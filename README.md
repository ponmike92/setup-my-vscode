# Настраиваем VSCode

- `extensions.txt`  устанавливаем плагины
- `keybindings.json` биндим хоткеи
- `settings.json` настраиваем vscode

## Ставим все плагины разом

Копируем в терминал:

  ```bash
  cat extensions.txt | xargs -L 1 code --install-extension
  ```

