# Markdown

* *text* Italic
* _text_
* **text** Bold
* __text__

## Code

Wrap code with ``` to create a code block.

\```

Get-childitem -filter *.txt

\```

```
Get-childitem -filter *.txt
```

Syntax highlight can also be added by including the language after the first ```

\```posh

Get-childitem -filter *.txt

\```

Four leading spaces also creates a code block.

    Get-childitem -filter *.txt

## Tables

```
Header1 | Header2
--------|--------
cell1 | cell2
another cell1 | another cell2
```

Header1 | Header2
--------|--------
cell1 | cell2
another cell1 | another cell2

## URLs

[here is Google](https://google.com)

```
[here is Google](https://google.com)
```