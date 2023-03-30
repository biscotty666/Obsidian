up:: [[Home]]
tags:: #map/view 

# The Inbox
This isn't a normal inbox. It's a cooling pad 🧊.

Thoughts come in hot 🌶. But after a few days, they cool down ❄️.

When cooler thoughts prevail, you can better prioritize. Cool? 

This view looks at the 20 newest notes in your **+ Encounters** folder. As you process each note, make connections, add details, move them to the best folder,  and delete everything that no longer sparks ✨. 

``` dataview
TABLE WITHOUT ID
 file.link as "Encounters and new notes",
 (date(today) - file.cday).day as "Days alive"

FROM "+ Encounters" and -#on/readme 

SORT file.cday asc

LIMIT 20
```


---

If you want to encounter some new things, check out: [🐦](https://www.twitter.com) or [📚](https://readwise.io/lyt/)          