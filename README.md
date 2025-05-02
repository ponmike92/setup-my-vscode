# Настраиваем VSCode

- `extensions.txt`  устанавливаем плагины
- `keybindings.json` биндим хоткеи
- `settings.json` настраиваем vscode

## Ставим все плагины разом

Копируем в терминал:

```bash
cat extensions.txt | xargs -L 1 code --install-extension
```

## меняю json2csv
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


## меняю snipped

ВАЖНО!
БАГ!
ОДИН РАЗ РАБОТАЕТ - ПОСЛЕДУЮЩИЕ НАДО ПЕРЕЗАКРЫВАТЬ VSCODE  =)
(возможно с показываемым уведомлением все работает многократно)

- добавляю в extension.js

```js
if (type === "copied") {
		vscode.window.showInformationMessage("Snipped copied");
		setTimeout(() => panel.dispose(), 1000);
}
```



- меняю в app.css


```css
.footer { display: none; }
.dot { display: none; }
.title { height: 5px; /* height: 15px; */ }
#lines { display: none; /* display: flex; */ }

.content {
  padding: 20px 20px 5px 20px; /* padding: 30px; */
  background: #1B1B1B; /* background: #c9d6ff; */
}

.container {
  min-width: 50px; /* min-width: 100px; */
	border: 0.5px solid rgba(255, 255, 255, 0.08); 
}

.wrapper {
  min-width: 50px; /* min-width: 250px; */
  min-height: 75px; /* min-height: 150px; */
}
```

- меняю в .js