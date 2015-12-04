
## Useful regular expression for fixing exported markdown from html

Replace regular html hyper link `<a href=""></a>` to `[]()` of markdown

```
<a href="([^>"]+)"[^>]*>([^<]+)</a>
[$2]($1)
```

Clean

```
<[^>]+>

```

`'`
```
&#8217;
'
```

`-`
```
&#8211;
-
```

### my markdown style

h2

```
\*\*(.+)\*\*
## $1
```

li

```
^  \*
-
```
