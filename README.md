# html_copy_text

```html
<html>

    <body>
        <button id="button1" onclick="CopyToClipboard('div1')">Click to copy</button>
        <br />
        <br />
        <div id="div1">Text To Copy </div>
        <br />
        <textarea placeholder="Press ctrl+v to Paste the copied text" rows="5" cols="20"></textarea>

        <script>
            function CopyToClipboard(containerid) {
                if (document.selection) {
                    var range = document.body.createTextRange();
                    range.moveToElementText(document.getElementById(containerid));
                    range.select().createTextRange();
                    document.execCommand("copy");
                } else if (window.getSelection) {
                    var range = document.createRange();
                    range.selectNode(document.getElementById(containerid));
                    window.getSelection().addRange(range);
                    document.execCommand("copy");
                    alert("Text has been copied, now paste in the text-area")
                }
            }
        </script>
    </body>

</html>
```

---

```
Copyright 2022 M. Fadli Zein
```