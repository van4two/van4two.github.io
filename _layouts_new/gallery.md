<!doctype html>
<html lang="{{ site.lang | default: "en-US" }}">
  <head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1">

    {% seo %}
    <link rel="stylesheet" href="{{ "/assets/css/style.css?v=" | append: site.github.build_revision | relative_url }}">
    <!--[if lt IE 9]>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/html5shiv/3.7.3/html5shiv.min.js"></script>
    <![endif]-->

    <link rel="stylesheet" type="text/css" href="/assets/css/gallery.css" />

  </head>

  <body>

    <div class="container">

        {{ content }}

        <!-- heading text -->
        <ul class="image-gallery">
            
        </ul>
    </div>

    
    <script>
        let gallery = document.getElementsByClassName("image-gallery")[0];
        for(var i in googlePhotos.urls) {
            let tile = document.createElement('li');

            let picture = document.createElement('img');
            picture.setAttribute("src", googlePhotos.urls[i] + '=w200');
            picture.setAttribute("alt", "");
            
            // <div class="overlay"><span>Image title</span></div>
            let overlay = document.createElement('div');
            overlay.className = "overlay";
            overlay.innerHTML = "<span>" + (Number(i)+1) + "</span>";

            tile.appendChild(picture);
            tile.appendChild(overlay);

            gallery.appendChild(tile);
        }

    </script>

  </body>

</html>
