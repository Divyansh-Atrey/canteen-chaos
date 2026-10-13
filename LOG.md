# Debug log

Your notes. One entry per bug you fixed, using the template below.

This file is read as carefully as your code. A correct fix you cannot
explain counts for little; a bug you could not fix but investigated
honestly still counts for something.

Delete the example before you submit.






### CC-01 : "The search suggestions are behind everything"

**Reproduced:** I typed the dish in search bar ,but the above search 
contents were hidden behind the main page contents. I can't click the topmost element.

**Cause:** The search container `.search-wrap` had  `z-index: 1`, which 
resulted in showing whole list of suggestion box .

**Fix:** Changed the `z-index` of `.search-wrap` from `1` to `100`.

**Checked:** Now the whole search suggestions are showing and i am able
to click them.

**Time:** took 25 minutes, mainly understanding the code of the search box 
and changing the search wrap code.




### CC-02: "Can't read anything in dark mode"

**Reproduced:** I switched the site to dark mode but the dish names and it's prices
are almost invisible.

**Cause:** The `.dish-body` has a dark color due to which we were not able to see them 
properly when the theme switched to dark mode (dark text blended in dark background).

**Fix:** Changed the color from `#2b2118` to `var(--ink)` to provide better visibility in dark mode.

**Checked:** Turned on and off dark mode ,now the dish names ad prices are visible

**Time:** took 15 minutes, mainly understanding the code of light and dark themes
and changing the code for the dish body.


### CC-05: "The category bar scrolls away on my phone"

**What I tried:** I changed the position of cat-tabs to sticky and top:62px so that it
 stops scrolling under the header as it is 62px.

**Where I got to:** I don't see any change in website for the phone after making
 the position of cat-tabs sticky.

**What I would try next:** I would check the other child blocks to check the problem.




