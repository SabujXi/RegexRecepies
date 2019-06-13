# Replace Raw HTML URLs/Links with asset() function automatically
It is a pain in the ass to manually replace all those raw asset links with asset function, writing `{{ asset('') }}` and copying the link.
To make your life easier, here is my Regular Expression recipe to cook your raw html into blade. Use editor that support regular expression. I used PhpStorm, you can use Notepad++, Sublime should also work and most of other modern editors, IDEs have regular expression replacement facility. Also, remember that this recipe will keep your external links ad hash links untouched.

In the Find field.
```
(href|src)(\s*=)("|')(?!http)([^"'#]+)\3
```

In the replacement field.
```
$1$2$3{{ asset('$4') }}$3
```
I tested it on PhpStorm and it will also work in other IntelliJ IDEs, let me know if it does not work in your editor. Also, contribution is welcome.

**For development work, training, content writing, consultation contact me: md.sabuj.sarker@gmail.com**
