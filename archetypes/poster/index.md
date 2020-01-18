---
# Documentation: https://sourcethemes.com/academic/docs/managing-content/

title: "{{ replace .Name "-" " " | title }}"
event:
event_url:
location:
address:
  street:
  city:
  region:
  postcode:
  country:
summary:
abstract:

# Talk start and end times.
#   End time can optionally be hidden by prefixing the line with `#`.
date: {{ .Date }}
date_end: {{ .Date }}
all_day: false

# Schedule page publish date (NOT talk date).
publishDate: {{ .Date }}

authors: []

# Select one tag between Talk and Poster
tags: [Poster]

# Talk or Poster type.
# Legend: 0 = Uncategorized; 1 = Talk; 2 = Poster
talk_poster_types:
- "2"

# Is this a featured talk? (true/false)
featured: false

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

links:
  - icon_pack: fab
    icon: github
    name: Github Repository
    url: '' # qui mettere il link alla repository

# Optional filename of your slides within your talk's folder or a URL.
url_slides:
url_poster:
url_code:
url_pdf:
url_video:

# Markdown Slides (optional).
#   Associate this talk with Markdown slides.
#   Simply enter your slide deck's filename without extension.
#   E.g. `slides = "example-slides"` references `content/slides/example-slides.md`.
#   Otherwise, set `slides = ""`.
slides: ""

# Projects (optional).
#   Associate this post with one or more of your projects.
#   Simply enter your project's folder or file name without extension.
#   E.g. `projects = ["internal-project"]` references `content/project/deep-learning/index.md`.
#   Otherwise, set `projects = []`.
projects: []
---
