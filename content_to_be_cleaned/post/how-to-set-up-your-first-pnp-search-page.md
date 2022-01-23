# How to set up your first PnP Search Page

After [deploying PnP Modern Search to your
tenant](https://searchexplained.com/deploy-pnp-modern-search-web-parts-sharepoint-online/),
it's time to create the first PnP search page.
> PnP search pages can be added to any modern site, so it's your
> decision where to do this. My recommendation is always try this out on
> a "playground" site first, before deploying to production.

## 1 -- Create an empty page 

The first step is to create an empty page, where you'll add the PnP web
parts. Go to any of your modern sites, and create a new page:
![pnp-modern-search-page-01-new-page-1024x412](https://techcommunity.microsoft.com/t5/image/serverpage/image-id/298687iF74A57C4A3372019/image-size/large?v=v2&px=999 "pnp-modern-search-page-01-new-page-1024x412")
 

## 2 -- Add the PnP web parts 

The next step is to add the PnP web parts to your page. The package,
that you've deployed, adds the following web parts available on your
modern pages:
![pnp-modern-search-page-02-web-parts](https://techcommunity.microsoft.com/t5/image/serverpage/image-id/298688iA6AAE54F025A1AD5/image-size/medium?v=v2&px=400 "pnp-modern-search-page-02-web-parts")

You can get to these web parts when search for "PnP" or "search" in the
web part gallery:

1.  PnP Search Box
2.  PnP Search Results
3.  PnP Search Filters
4.  PnP Search Verticals
![pnp-modern-search-page-03-web-parts-example-1024x686](https://techcommunity.microsoft.com/t5/image/serverpage/image-id/298689i03C4AF25769623B8/image-size/large?v=v2&px=999 "pnp-modern-search-page-03-web-parts-example-1024x686")
On a very simple search page, we have at least two web parts: a search
box and a search results web part.

### Search Box Web Part 

You simply add a Search Box to the page by choosing "PnP Search Box" web
part. At this point, you don't have to do any further configuration.
![pnp-modern-search-page-04-search-box-web-part](https://techcommunity.microsoft.com/t5/image/serverpage/image-id/298690i40190059668FD435/image-size/large?v=v2&px=999 "pnp-modern-search-page-04-search-box-web-part")

### Search Results Web Part 

The next step is to add a "PnP Search Results" web part to the page.

Once the web part is added to the page, you have to connect it to the
Search Box web part, to receive the query from there. You can do this by
following these steps:

1.  Edit the page.
2.  Edit the properties of the Search Results web part.
3.  Switch to page "3 of 4" on the web part properties.
4.  Turn on "Use input query text".
5.  Select "Dynamic value" in the radio button list.
6.  Select "PnP -- Search Box" in the "Connect to source" dropdown.
7.  Select "Search query" in the "PnP -- Search Box's properties"
    dropdown.
![pnp-modern-search-page-05-search-results-web-part-properties](https://techcommunity.microsoft.com/t5/image/serverpage/image-id/298691i7F33281C0C5ECFE3/image-size/medium?v=v2&px=400 "pnp-modern-search-page-05-search-results-web-part-properties")

Once done, save the page and enjoy your very first search page!
![pnp-modern-search-page-06-search-page-101](https://techcommunity.microsoft.com/t5/image/serverpage/image-id/298692i21BB76583CD75EEE/image-size/large?v=v2&px=999 "pnp-modern-search-page-06-search-page-101")

*This article was originally posted on [Search Explained
Blog](https://searchexplained.com/deploy-pnp-modern-search-web-parts-sharepoint-online/).*
