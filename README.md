# My Website
Work in progress.......(like me irl)...

www.notdavid.me
http://darvid7.github.io/

Built using hugo & HTML5up.

## Hugo notes
I've customized the starta theme a bit.

don't have an index.md, it breaks everything :( or it might be when you don't have a title.

Not sure why but `index.md` won't render, this is good because I'll chuck it into the templating but idk maybe work it out some time.


```
<!-- Not entirly sure what happened here but index.md gets rendered for '/' because it's title is "Home". Only can render 1 .md page by the looks of it.
-->
{{ range where .Data.Pages "Title" "Home" }}
    <article>
        <!-- Title, as defined in the front-matter  of /content/index.md -->
        <h1 class="pagetitle">{{ .Title }}</h1>
        <div class="content">
            <!-- Content. is the actual content of '/content/index.md' -->
            {{ .Content }}
        </div>
    </article>
{{ end }}
```