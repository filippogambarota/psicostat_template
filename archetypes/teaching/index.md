---
# Documentation: https://sourcethemes.com/academic/docs/managing-content/

# Questa pagina crea un nuovo corso nella sezione teaching. Per far funzionare il filtro impostato nel widget (home/teaching.md)
# inserire il tag: "current" o "past"

title: "{{ replace .Name "-" " " | title }}"
summary: ""
type: "teaching"
authors: [admin]
tags: [] # qui si può aggiungere l'anno (senza virgolette)
categories: []
date: {{ .Date }}

# Optional external URL for project (replaces project detail page).
external_link: ""

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder.
# Focal points: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight.
image:
  caption: ""
  focal_point: ""
  preview_only: false

# Custom links (optional).
#   Uncomment and edit lines below to show custom links.
# links:
# - name: Follow
#   url: https://twitter.com
#   icon_pack: fab
#   icon: twitter

# questo è un link custom per il sito unipd dell'insegnamento

links:
  - icon_pack: fab
    icon: university
    name: Moodle
    url: 'www.unipd.it' # qui mettere il link del corso

url_code: ""
url_pdf: ""
url_slides: ""
url_video: ""

# Slides (optional).
#   Associate this project with Markdown slides.
#   Simply enter your slide deck's filename without extension.
#   E.g. `slides = "example-slides"` references `content/slides/example-slides.md`.
#   Otherwise, set `slides = ""`.
slides: ""
---
