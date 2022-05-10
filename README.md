ezSyntax
=================
Hi, welcome to the ezSyntax page on GitHub. With ezSyntax, you can easily add syntax highlighting to your `<code>` blocks using one line of code.


Need help? [Join the Discord](https://willm.xyz/discord)!


Check out more info on [ezsyntax.willm.xyz](https://ezsyntax.willm.xyz) \ ゜o゜)ノ

If you find a bug or something not working right, **please** [submit an issue](https://github.com/whasonyt/ezsyntax/issues/new)!

-----------------------
## To-Do 
- [X] Allow users to change which programming language gets syntaxed (only HTML right now)
- [X] Instead of having to use `syntax('demo', 1)`, have an option to apply to all `<code>` blocks

> Submit a pull request if you'd like to contribute any of these features!




## Usage/Examples

### HTML
```html
<!DOCTYPE html>

<html>
<head>
<script src="https://starsign68.github.io/ezsyntax/user/script.js"></script>
<script>
class codeEscape extends HTMLElement {
    constructor() {
        super();

        const escapeHTML = (str) =>
            str.replace(/[&<>'"]/g, (tag) => ({ '&': '&amp;', '<': '&lt;', '>': '&gt;', "'": '&#39;', '"': '&quot;' }[tag] || tag));
        const shadow = this.attachShadow({ mode: 'closed' });
        this.style.whiteSpace = "pre";
        const res = `${escapeHTML(this.outerHTML)}`;
        var text = document.createElement('code');
        text.innerHTML = res;
        shadow.appendChild(text);
        setTimeout(function () {
            const cElms = document.getElementsByTagName("code-escape");
            [...cElms].map(element => syntax(element, "html"));
        }, 10)
    }
}

customElements.define('code-escape', codeEscape);
</script>

</head>
<html>
<body>
<div class="code" id="code" style="font-family: mono, arial, sans-serif;">
<code-escape class="test" style="white-space: pre;">&lt;!DOCTYPE html&gt;
&lt;html&gt;
&lt;body&gt;

&lt;p&gt;
This paragraph
contains a lot of lines
in the source code,
but the browser 
ignores it.
&lt;/p&gt;

&lt;p&gt;
This paragraph
contains      a lot of spaces
in the source     code,
but the    browser 
ignores it.
&lt;/p&gt;

&lt;p&gt;
The number of lines in a paragraph depends on the size of the browser window. If you resize the browser window, the number of lines in this paragraph will change.
&lt;/p&gt;

&lt;/body&gt;
&lt;/html&gt;
</code-escape>
</div>
</body>
</html>

```


## Contributors

- [@Starsign68](https://github.com/Starsign68)

-----------------------
Made with ❤ by [Will M](https://willm.xyz)


