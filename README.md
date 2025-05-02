# Настраиваем VSCode

- `extensions.txt`  устанавливаем плагины
- `keybindings.json` биндим хоткеи
- `settings.json` настраиваем vscode

## Ставим все плагины разом

Копируем в терминал:

```bash
cat extensions.txt | xargs -L 1 code --install-extension
```

## меняю плагин
```js
function ne(e, r = !1)
```

```js
function ne(e, r = !1) {
	let t = x.window.activeTextEditor
	if (!t) return

	let n
	t.selection.isEmpty
		? (n = new x.Range(t.document.positionAt(0), t.document.positionAt(t.document.getText().length)))
		: (n = new x.Range(t.selection.start, t.selection.end))

	let s = t.document.getText(n)
	let { convertedText: p, convertedLanguage: O, success: v } = e(s)

	if (v) {
		if (r) {
			x.env.clipboard.writeText(p)
			x.window.showInformationMessage('The converted text has been copied to the clipboard.')
			return
		}

		// Заменяем выделенный текст на результат
		t.edit((editBuilder) => {
			editBuilder.replace(n, p)
		}).then(() => {
			x.window.showInformationMessage('Converted successfully!')
		})
	}
}
```

