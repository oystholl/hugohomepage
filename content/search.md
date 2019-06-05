+++
title = "ResInsight Search"
published = true
+++

<section>
  <div class="grid">
    <div class="whole">
      <article>
        <h1>Search for: <span id="search-title"></span></h1>
        <div id="search-results">
        </div>
      </article>
    </div>
  </div>
  <div class="clear"></div>
</section>

<script src="https://ajax.googleapis.com/ajax/libs/jquery/3.2.1/jquery.min.js"></script>
<script src="../js/lunr.min.js"></script>
<script>

/*window.store : [
    "{{ $.Site.Home.Ref }}": {
        "title": "{{ .Title }}",
        "content": "{{ .Plain}}",
        "html": "{{ .Content }}",
        "url": "{{ .Ref }}",
    }
]*/

window.store = {[
    {{ .Range $.Site.Allpages }}
        {
            {{ .Ref }}: {
                title: "{{ .Title }}",
                content: "{{ .Plain}}",
                html: "{{ .Content }}",
                url: "{{ .Ref }}",
        },
    {{ end }}
]};

console.log(window.store);

window.baseurl = "{{ site.baseurl }}";
</script>
<script src="../js/search.js"></script>

