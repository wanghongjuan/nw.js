# Writing Documents for NW.js {: .doctitle}

[TOC]

## Read Before Writing New Document

Github provides nice representation of Markdown online with its own syntax GFM (Github Flavored Markdown). And many of the developers are reading documents directly on GitHub. To enable the best documentation of NW.js for any developers, **make sure the document is readable on GitHub before submitting your PR**.

The documentation site of NW.js is generated by [MkDocs](http://www.mkdocs.org/) which supports a slightly different Markdown syntax than GFM. So the page may be broken on GitHub while works under MkDocs, or vice versa.
A bad example is not having `.md` suffix in internal links, like `[Build NW.js](Build NW.js)`. On GitHub, the link is broken because the file `Build NW.js` without `.md` does not exist. Always add `.md` suffix to your internal links.

## View the Document Offline
To view the well-formatted documents on your own laptop, you need [Python](https://www.python.org/) and install following dependencies:
```bash
pip install mkdocs pygments pymdown-extensions
```
Run following commands in the root of NW.js repo:
```bash
mkdocs serve
```
Then open your browser and navigate to http://localhost:8000/ .

## Template for API Reference Page

Here is a minimal template for writing a page for NW.js API reference:
```markdown
# Module Name {: .doctitle}

---

[TOC]

Describe the usage and other details of the module here.

## Module.staticMethod(arg1, arg2)

* `arg1` `{String}` description of `arg1`
* `arg2` `{Object}` description of `arg2`
  * `isSet` `{Boolean}` description of the field
* Returns `{Type}` description of the return value

Details about the the method.

## inst.method(arg1, arg2)

## Event: eventName(arg1, arg2)
```

* **[MUST]** use `#` for page title and `##` or `###` headers for sections. **DO NOT** use `=======` or `-------`.
* **[MUST]** add `{: .doctitle}` right to the page title. This is the CSS class name for the document title.
* **[MUST]** add a horizontal ruler with `---` after the page title.
* **[MUST]** add a `[TOC]` after the ruler.
* **[MUST]** quote any code with a back tick (`` ` ``) in the document unless it's in the headers.
* **[MUST]** specify the language for the code blocks.
* Instance methods / properties in headers **[MUST]** use lower case instance name. Bad example: `Window.resizeTo(x,y)`; Good example: `win.resizeTo(x,y)`
* Events **[MUST]** in headers be written as **Event: eventName(args...)**
* **[MUST]** provide detailed list of arguments and return values for methods, including name, type wrapped with brackets ({TypeName}) and whether it's optional in italic (_Optional_).

## Checklist for Pull Request

* [ ] Comply with the [Template for API Reference Page](#template-for-api-reference-page) above
* [ ] Make sure the new page is added to `mkdocs.yml`
* [ ] Make sure the document is readable on GitHub
* [ ] Make sure the links are not broken
* [ ] Add your name and email to [Contributors of Documents.md](Contributors of Documents.md)

## Markdown Extensions
Currently the documentation site of NW.js enables following extensions for generating documents. See `mkdocs.yml` in the root for detailed configuration.

* markdown.extensions.toc
* markdown.extensions.admonition
* markdown.extensions.smarty
* markdown.extensions.nl2br
* markdown.extensions.codehilite
* pymdownx.extra
* pymdownx.inlinehilite
* pymdownx.magiclink
* pymdownx.tilde
* pymdownx.caret
* pymdownx.smartsymbols
* pymdownx.githubemoji
* pymdownx.tasklist
* pymdownx.progressbar
* pymdownx.headeranchor
* pymdownx.arithmatex
* pymdownx.mark
* pymdownx.critic


