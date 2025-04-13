## ✅ Passo 1: Instalar a extensão Custom CSS and JS Loader
- Abra o VSCode.

- Vá para a aba de Extensões (ícone de quadrado no menu lateral ou aperte: `(Ctrl + Shift + X`) ).

- Pesquise por: <b>Custom CSS and JS Loader</b> (autor: <b>be5invis</b>).

<b>Instale a extensão.</b>



## ✅ Passo 2: Criar um arquivo .css com as modificações
Em qualquer pasta do seu computador, crie um arquivo chamado, por exemplo: <b>vs-custom-style.css</b>

Adicione o seguinte CSS para alterar a fonte da barra lateral (pastas e arquivos):

```
/* Muda a fonte da sidebar (explorer) */
.monaco-workbench .part.sidebar .content .monaco-list .monaco-list-row {
  font-family: "Fira Code", "Courier New", monospace !important;
  font-size: 14px !important; 
  color: #f8ffcf;
}
```

## ✅ Passo 3: Linkar o CSS no VSCode
Abra o Command Palette apertando: `(Ctrl + Shift + P)`.

Digite: <b>Custom CSS and JS: Enable Custom CSS and JS.</b>

`(Ele pode pedir o caminho do seu arquivo .css criado no passo anterior. Selecione corretamente. Se não pedir o caminho, o VsCode apenas pedirá pra ser reiniciado)`

Reinicie o VSCode.

## ✅ Passo 4: Habilitar a flag de inicialização
O VSCode, por segurança, bloqueia CSS customizado. Então você precisa iniciar o VSCode com a flag:

```
--enable-features=EnableCustomCSS.
```

### 🔍 Onde adicionar?
Se estiver no Windows:
Clique com o botão direito no atalho do VSCode → <b>Propriedades</b>.


Em <b>"Destino"</b>, adicione no final:

```
--enable-features=EnableCustomCSS.
```

<b>Exemplo:</b>

`
"C:\Users\SeuUser\AppData\Local\Programs\Microsoft VS Code\Code.exe" --enable-features=EnableCustomCSS
`

## ✅ Passo 5: Verifique se o caminho do CSS está configurado corretamente no VsCode
Abra o arquivo: <b>settings.json do seu VSCode</b>:

Aperte
`(Ctrl + Shift + P)` e selecione no Command Palette -> <b>Preferences: Open Settings (JSON)</b>


Verifique se existe algo assim:
```
"vscode_custom_css.imports": [
  "file:///C:/caminho/para/seu/arquivo/custom-style.css"
]
```

## 🔍 Como adicionar o arquivo CSS corretamente?

Caso o trecho acima não exista no seu JSON, vá para o arquivo <b>settings.json</b> como demonstrado acima.
 
Depois, no meio das outras configurações `ou no final do arquivo, logo antes da última chave }`, adicione:

```
"vscode_custom_css.imports": [
  "file:///C:/caminho/para/seu/arquivo/custom-style.css"
]
```

#### ⚠️ Certifique-se que o caminho esteja correto! Se estiver errado ou vazio, o CSS não será aplicado.

- Use três barras `///` após file: O caminho deve apontar para o arquivo .css.
- <b>É importante usar `/` ao invés de `\` no caminho do arquivo!</b>

## ✅ Agora com tudo configurado, você pode testar novamente:


Abra o Command Palette `(Ctrl + Shift + P)`


Digite: <b>Custom CSS and JS: Enable Custom CSS and JS</b>


- Após selecionar a opção, o VsCode pedirá para ser reiniciado. Após reiniciar, a fonte da barra lateral deve estar alterada.
