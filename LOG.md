# Debug log

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



### CC-03: "The menu is wider than my phone"

**Reproduced:** I opened the Canteen Menu on a mobile screen having width below 360px and that's why the menu is not fully visible and the add to cart option.

**Cause:** The dish name buttons were set to width: max-content and the menu-card images were set to min-width:100% which let 
to less visibility of menu cards.

**Fix:** Changed the width:100% and object-fit : cover to make the img fit in dish-card img and menu-grid width:100% in the max-width : 760px and 480px.

**Checked:** Checked the Website after changing the code of dish card and menu.

**Time:** took 15 minutes, mainly understanding the code of max-width : 760px and max-width : 480px.



### CC-05: "The category bar scrolls away on my phone"

**What I tried:** I changed the position of cat-tabs to sticky and top:62px so that it
stops scrolling under the header as it is 62px.

**Where I got to:** I don't see any change in website for the phone after making
the position of cat-tabs sticky(but it makes the search suggestion hide so i am reverting it).

**What I would try next:** I would check the other child blocks to check the problem.



### CC-06: "I ordered more than they had"

**Reproduced:** When i ordered something i can order more than the stock they had.
 Product can be ordered more than the they can serve.

**Cause:** The Validation.js file didn't have the logic for the items ordered > the item left ,
due to which we were able to order more than the items available.

**Fix:** added a logic for the order if quantity > Number of dish in stock then it shows a 
error: Invalid order and at the end shows Invalid Order: Only (quantity) left of (Dish name).

**Checked:** Checked the Website after changing the code of validation.js and it now shows the error 
and we can't order now more than they had.

**Time:** took 20 minutes, mainly understanding the code of validation.js and changing the code.



### CC-08: "An old coupon still works"

**Reproduced:** When i ordered something with the coupon `FRESHERS24` , it worked and i got a discount
from a coupon which expired years ago.

**Cause:** The pricing.js didn't have the logic for the coupon expiry date exists and
it is less than current Date and time, which would show coupon expired.

**Fix:** added a logic for the coupon if Coupon.expiresAt and expiry-date < current date ,
then it should show `Coupon Expired`.

**Checked:** Checked the Website after changing the code of pricing.js and it now shows the error Coupon Expired.

**Time:** took 25 minutes, mainly understanding the code of pricing.js , coupons.routes.js and coupons.json
and changing the code.
