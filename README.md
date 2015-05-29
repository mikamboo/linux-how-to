# Linux Snipets

Linux snippets book (for debian based distributions). 

![](Linux-Logo.jpg)

[Lecture sur Gitbook](http://mikamboo.gitbooks.io/linux-snipets-book/content/)

___

__AUTHOR__ : @_mikamboo

* [Fork book](https://github.com/mikamboo) 
* [Follow me](https://twitter.com/_mikamboo)

__TOOLS__

* [Bash videos](https://asciinema.org/)

{% exercise %}
Define a variable `x` equal to 10.
{% initial %}
var x =
{% solution %}
var x = 10;
{% validation %}
assert(x == 10);
{% context %}
// This is context code available everywhere
// The user will be able to call magicFunc in his code
function magicFunc() {
    return 3;
}
{% endexercise %}