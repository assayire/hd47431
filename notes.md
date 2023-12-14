# Notes

## layouts/index.html

```html
{{ define "main" }}
<h1>{{ .Title }}</h1>

<h1>The Landing Page</h1>

{{ $dateMachine := .Date | time.Format "2006-01-02T15:04:05-07:00" }}
{{ $dateHuman := .Date | time.Format ":date_long" }}
<time datetime="{{ $dateMachine }}">{{ $dateHuman }}</time>

{{ .Content }}
{{ partial "terms.html" (dict "taxonomy" "tags" "page" .) }}
{{ end }}
```

```html
<div class="home-content">
  <div id="title">Acme Knowledge Base</div>
  <!-- <div id="links">
    <a href="/posts">blog</a>
    <a href="https://github.com/johndoe">github</a>
    <a rel="me" href="https://mastodon.social/@johndoe">mastodon</a>
    <a href="/about/">about</a>
  </div> -->

  <header>
    <!--  {{ partial "header.html" . }} -->
  </header>

  <nav class="hz-chain">
    <ul>
      {{ $mainMenu := .Site.Menus.main }}
      {{ range $mainMenu }}
      <li class="highlight">
        <a href="{{ .URL }}">{{ .Name }}</a>
      </li>
      {{ end }}
    </ul>
  </nav>
</div>
```
