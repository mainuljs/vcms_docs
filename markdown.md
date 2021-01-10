# Markdown Cheatsheet

## Headers
**Syntax**
```markdown
# h1
## h2
### h3
#### h4
##### h5
###### h6

Alternatively, for H1 and H2, an underline-ish style:
h1
===
h2
---
```

## Emphasis
**Syntax**
```markdown
Emphasis, italics, with *asterisks* or _underscores_.

Strong emphasis, bold, with **asterisks** or __underscores__.

Combined emphasis with **asterisks and _underscores_**.

Strikethrough uses two tildes. ~~Scratch this.~~
```

**Output**

Emphasis, italics, with *asterisks* or _underscores_.

Strong emphasis,bold, with **asterisks** or __underscores__.

Combined emphasis with **asterisks and _underscores_**.

Strikethrough uses two tildes. ~~Scratch this.~~


## Lists
**Syntax**
```markdown
1. First ordered list item
2. Another item

* First unordered list item
- Or use minuses
+ Or use pluses
```

**Output**
1. First ordered list item
2. Another item

* First unordered list item
- Or minuses
+ Or pluses


## Links
**Syntax**
```markdown
[I'm an inline-style link](https://www.google.com) 

[I'm an inline-style link with title](https://www.google.com "Google's Homepage")

[I'm a relative reference to a repository file](../blob/master/LICENSE)

URLs and URLs in angle brackets will automatically get turned into links. 
http://www.example.com or <http://www.example.com>
```

**Output**

[I'm an inline-style link](https://www.google.com) 

[I'm an inline-style link with title](https://www.google.com "Google's Homepage")

[I'm a relative reference to a repository file](../blob/master/LICENSE)

URLs and URLs in angle brackets will automatically get turned into links. 
http://www.example.com or <http://www.example.com>


## Images
**Syntax**
```markdown
Here's our logo (hover to see the title text):
Inline-style: 
![alt text](_media/icon.png "Logo Title Text 1")

Reference-style: 
![alt text][logo2]
[logo2]: _media/icon.png "Logo Title Text 2"
```

**Output**

Here's our logo (hover to see the title text):

Inline-style: 
![alt text](_media/icon.png "Logo Title Text 1")

Reference-style: 
![alt text][logo2]

[logo2]: _media/icon.png "Logo Title Text 2"

## Highlighting
**Syntax 1**
```markdown
Inline `code` has `back-ticks around` it.
```

**Output**

Inline `code` has `back-ticks around` it.


<br>

**Syntax 2**
```markdown
	```javascript
	var s = "JavaScript syntax highlighting";
	alert(s);
	```

	```python
	s = "Python syntax highlighting"
	print s
	```
	 
	```
	No language indicated, so no syntax highlighting. 
	But let's throw in a <b>tag</b>.
	```
```

**Output**
```javascript
var s = "JavaScript syntax highlighting";
alert(s);
```

```python
s = "Python syntax highlighting"
print s
```
 
```
No language indicated, so no syntax highlighting. 
But let's throw in a <b>tag</b>.
```


## Table
```markdown
Colons can be used to align columns.

| Tables        | Are           | Cool  |
| ------------- |:-------------:| -----:|
| col 3 is      | right-aligned | $1600 |
| col 2 is      | centered      |   $12 |
| zebra stripes | are neat      |    $1 |

There must be at least 3 dashes separating each header cell.
The outer pipes (|) are optional, and you don't need to make the 
raw Markdown line up prettily. You can also use inline Markdown.

Markdown | Less | Pretty
--- | --- | ---
*Still* | `renders` | **nicely**
1 | 2 | 3
```

**Output**

Colons can be used to align columns.

| Tables        | Are           | Cool  |
| ------------- |:-------------:| -----:|
| col 3 is      | right-aligned | $1600 |
| col 2 is      | centered      |   $12 |
| zebra stripes | are neat      |    $1 |

There must be at least 3 dashes separating each header cell.
The outer pipes (|) are optional, and you don't need to make the 
raw Markdown line up prettily. You can also use inline Markdown.

Markdown | Less | Pretty
--- | --- | ---
*Still* | `renders` | **nicely**
1 | 2 | 3



## Blockquotes
**Syntax**
```markdown
> Blockquotes are very handy in email to emulate reply text.
> This line is part of the same quote.

Quote break.

> This is a very long line that will still be quoted properly when it wraps. Oh boy let's keep writing to make sure this is long enough to actually wrap for everyone. Oh, you can *put* **Markdown** into a blockquote.
```

**Output**
> Blockquotes are very handy in email to emulate reply text.
> This line is part of the same quote.

Quote break.

> This is a very long line that will still be quoted properly when it wraps. Oh boy let's keep writing to make sure this is long enough to actually wrap for everyone. Oh, you can *put* **Markdown** into a blockquote.


## Inline HTML
**Syntax**
```markdown
<dl>
  <dt>Definition list</dt>
  <dd>Is something people use sometimes.</dd>

  <dt>Markdown in HTML</dt>
  <dd>Does *not* work **very** well. Use HTML <em>tags</em>.</dd>
</dl>
```

**Output**

<dl>
  <dt>Definition list</dt>
  <dd>Is something people use sometimes.</dd>

  <dt>Markdown in HTML</dt>
  <dd>Does *not* work **very** well. Use HTML <em>tags</em>.</dd>
</dl>


## Horizontal Rule
**Syntax**
```markdown
Three or more...
---
Hyphens

***
Asterisks
___
Underscores
```

**Output**

Three or more...

---
Hyphens

***
Asterisks
___
Underscores


## Line Breaks
**Syntax**
```markdown
Here's a line for us to start with.

This line is separated from the one above by two newlines, so it will be a *separate paragraph*.

This line is also a separate paragraph, but...
This line is only separated by a single newline, so it's a separate line in the *same paragraph*.
```

**Output**

Here's a line for us to start with.

This line is separated from the one above by two newlines, so it will be a *separate paragraph*.

This line is also a separate paragraph, but...
This line is only separated by a single newline, so it's a separate line in the *same paragraph*.

`(Technical note: Markdown Here uses GFM line breaks, so there's no need to use MD's two-space line breaks.)`


## Youtubde Videos

> They can't be added directly but you can add an image with a link to the video like this:

**Syntax**
```markdown
<a href="http://www.youtube.com/watch?feature=player_embedded&v=YOUTUBE_VIDEO_ID_HERE
" target="_blank"><img src="http://img.youtube.com/vi/YOUTUBE_VIDEO_ID_HERE/0.jpg" 
alt="IMAGE ALT TEXT HERE" width="240" height="180" border="10" /></a>
```

**Output**

<a href="http://www.youtube.com/watch?feature=player_embedded&v=YOUTUBE_VIDEO_ID_HERE
" target="_blank"><img src="http://img.youtube.com/vi/YOUTUBE_VIDEO_ID_HERE/0.jpg" 
alt="IMAGE ALT TEXT HERE" width="240" height="180" border="10" /></a>

> Or, in pure Markdown, but losing the image sizing and border:

**Syntax**
```markdown
[![IMAGE ALT TEXT HERE](http://img.youtube.com/vi/YOUTUBE_VIDEO_ID_HERE/0.jpg)](http://www.youtube.com/watch?v=YOUTUBE_VIDEO_ID_HERE)
```

**Output**

[![IMAGE ALT TEXT HERE](http://img.youtube.com/vi/YOUTUBE_VIDEO_ID_HERE/0.jpg)](http://www.youtube.com/watch?v=YOUTUBE_VIDEO_ID_HERE)



