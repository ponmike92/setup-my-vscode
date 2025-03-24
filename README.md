# Настраиваем VSCode

- `extensions.txt`
- `keybindings.json`
- `settings.json`

## Ставим все плагины разом

Копируем в терминал:

  ```bash
  cat extensions.txt | xargs -L 1 code --install-extension
  ```

