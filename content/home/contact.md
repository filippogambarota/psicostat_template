+++
# Questa è una pagina che presenta il gruppo psicostat. C'è un feed di twitter, un po' di descrizione e il nostro motto

widget = "blank"  # See https://sourcethemes.com/academic/docs/page-builder/
headless = true  # This file represents a page section.
active = true  # Activate this widget? true/false
weight = 130  # Order that this section will appear.

title = "Contact"
subtitle = ""

[design]
  # Choose how many columns the section has. Valid values: 1 or 2.
  columns = ""

[design.background]
  # Apply a background color, gradient, or image.
  #   Uncomment (by removing `#`) an option to apply it.
  #   Choose a light or dark text color by setting `text_color_light`.
  #   Any HTML color name or Hex value is valid.

  # Background color.
  # color = "navy"
  
  # Background gradient.
  # gradient_start = "DeepSkyBlue"
  # gradient_end = "SkyBlue"
  
  # Background image.
  #image = "headers/bubbles-wide.jpg"  # Name of image in `static/img/`.
  image_darken = 0.6  # Darken the image? Range 0-1 where 0 is transparent and 1 is opaque.
  image_size = "cover"  #  Options are `cover` (default), `contain`, or `actual` size.
  image_position = "center"  # Options include `left`, `center` (default), or `right`.
  image_parallax = true  # Use a fun parallax-like fixed background effect? true/false

  # Text color (true=light or false=dark).
  text_color_light = false

[design.spacing]
  # Customize the section spacing. Order is top, right, bottom, left.
  padding = ["20px", "0", "20px", "0"]

[advanced]
 # Custom CSS. 
 css_style = ""
 
 # CSS class.
 css_class = ""
+++

<!-- Questo widget è creato da zero invece di usare il widget contact per poter inserire il feed di twitter personale. è sufficiente cambiare le info all'interno dei link html per avere tutti i contatti funzionanti -->

<div style="float: left; width: 50%; padding-top: 20px">

  <!-- Email -->
  <span class="fas fa-envelope" style="font-size: 200%; padding-right: 20px"></span>
  <a href="mailto:email@gmail.com">email@gmail.com</a>

  <!-- telefono -->
  <span class="fas fa-phone" style="font-size: 200%; padding-right: 20px"></span>
  <a href="tel:049773333">049773333</a>

  <!-- luogo -->
  <span class="fas fa-map-marker-alt" style="font-size: 200%; padding-right: 30px"></span>
  Via Venezia 8 Padova

  <!-- orario ricevimento -->
  <span class="fas fa-clock" style="font-size: 200%; padding-right: 20px"></span>
  Lunedi dalle 14:30 alle 16:30

  <!-- mandami un tweet -->
  <!-- cambiare il twitter id -> recipient_id=3805104374 con il proprio e inserire il @nomeutente -->

  <span class="fab fa-twitter" style="font-size: 200%; padding-right: 20px"></span>
    <a href="https://twitter.com/messages/compose?recipient_id=444926257"
    class="twitter-dm-button" data-screen-name="@fgambarota">
    </a>

  <!-- contattami con skype -->

  <span class="fab fa-skype" style="font-size: 200%; padding-right: 25px"></span>
  <a href="a">Skype</a>

</div>

<div style="float: left; width: 50%; padding-top: 20px">

  <a class="twitter-timeline" data-width="500" data-height="400" href="https://twitter.com/fgambarota?ref_src=twsrc%5Etfw">Tweets by fgambarota</a>
  <script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>

</div>