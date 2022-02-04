## Auden-Musulin Papers Digital Edition website review
Sean Quigley  
Feb. 3, 2022

### Main takeaways
- The images should be foregrounded better
- Need to rethink presentation of text transcriptions
- Make navigation easier by reducing number of clicks

### Homepage
- The most prominent "call to action" on the homepage is to "read more," which takes you to the [Project Description](https://auden-musulin-papers.github.io/amp-app/description.html). That's fine, but the page is a dead end - there should be a link or a prompt to go explore the archive at the end of the project description page. 

### Table of contents (papers -> Auden-Musulin correspondance)
- Generally: need more information about what is actually in each of the letters. Scrolling up and down this [table of contents](https://auden-musulin-papers.github.io/amp-app/toc.html) page, I see very little to distinguish the letters from each other - no indication of what's in them or what makes them special
- The current design foregrounds only the front of the envelope - not always the most interesting part! Suggestions:
    - When a user mouses over an image on the table of contents page, display all available images in a kind of [carousel](https://www.nngroup.com/articles/designing-effective-carousels/)
	- Or, select the "most interesting" image and set it as the "cover" 
- I think there should be a way to view the content from all five of the "papers" categories at once, and sort and filter it according to date, category, etc. 
- Not sure how the items are sorted now - it should probably default to chronological order. 

### Navigation
- When I click on a letter from the table of contents, I am usually taken to a page showing me the "diplomatic view" of a front of the corresponding envelope. To read the letter, I often have to navigate to the third page. In my opinion this is too much clicking - I feel all pages of the item should be visible after one click from the homepage. 
	- This could be as simple as removing the 1,2,3,4 buttons and just displaying all content in a series of panes as the user scrolls down. 
	- At the very least I think in "reading mode" all the available text should be displayed on a single page. 

### Letter presentation 
- **There should be a view mode that displays only images**. The idea here would to simulate flipping through the actual letters, as if you had a stack of them in your hand. The transcriptions are great but the current display options don't give you a good way to look at the images by themselves. We have these beautiful high-res images; we should let them be part of the show. 
    - The "diplomatic view" can feel cumbersome because the image viewer only gets half of the real estate. 
	- dragging the "change size" button to increase the size of the photo viewing area works ok but is not intuitive - many users will expect to be able to click and drag the middle bar.
	- It might be good to consider expanding the site's maximum width. When I  [maximize](wide-screen.PNG) the page on my monitor, there is a lot of wasted space. Currently, it feels hard to get a good look at the actual images - the image viewer is small and doesn't zoom in very much. I'd just like a way to really look at these images in detail without having to go full-screen. 
- Flipping between letters with the left and right arrows works great, but ideally your view mode should be saved as you switch to a new letter. If I'm in "reading view" and I switch over to the next letter it should stay in reading view. (Currently every letter page defaults to diplomatic view no matter what). 
- Switching between diplomatic, commentary, and reading view can be wonky - sometimes, switching views can cause a different page (of the same letter) to come up. 

**"diplomatic view"** and design language  
The diplomatic view is always front-and-center, but I think it needs to be rethought a little bit.     
First of all, as we discussed, a monospace font would work better for typewritten letters than what we have now because it would better represent how the typed letter looks on the page. But we can go even further and think about how best to represent other aspects of the actual letters in plain text. That way, there is less detail "lost" in the transcription. 
 
From what I can tell, there are at least three main kinds of text in the images:
1. Typewritten
2. Handwritten
3. Pre-printed words on the paper (i.e. heading on Auden's stationery)

It would be great if the diplomatic view could preseve the difference between these kinds of text in a visual way. I noticed that there is actually a way to encode text styling information in the TEI standard. Using the [rendition element](https://tei-c.org/release/doc/tei-p5-doc/en/html/HD.html#HD57-1) in the header, you can specify rules for displaying different kinds of text with CSS. So we could create display rules for each category of text (could be way more than 3!) and then add tags to each text element in the XML files. 

I think subtle differences in typeface and color (black for important stuff, gray for things in the background like letter headings, etc) could help readability. For instance, on page three of [this](https://auden-musulin-papers.github.io/amp-app/amp-transcript__0014.html) letter, having the first three lines centered and in a different typeface (maybe also in a slightly lighter color, a dark gray or something) would help make clear - at first glace of the diplomatic view - that these characters are "part of the background" and not part of the actual text. 

Another benefit to all of this is that it will simply make the transcriptions *look* more attractive. This stuff is special, and displaying it in a normal default browser font just like the one on some news website is no good. 

There are a lot of ways to approach this - you could even attempt to position the plain text on a "page" to mimic where it appears in the image with [flex boxes](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Flexible_Box_Layout/Aligning_Items_in_a_Flex_Container) or something, but that seems like a formatting nightmare and would probably not be worth the effort. 

### Biographies section
The timeline view is cool, but it would look better if there were small thumbnail-sized images of the items in the column on the right side. In [1968](timeline.PNG), for instance, we have a bunch of identical records in a row with no way to distinguish them. 

I think the embedded maps on the left side of the timeline are a great idea. One way to take this concept further would be to use "[story maps](https://storymaps.arcgis.com/stories/9a500acb526f4be8b0a3c66ffa8e53fa)." The industry standard for story maps is a product called [ArcGIS online](https://www.arcgis.com/index.html), but a license costs about $1500. 
There are two free alternatives that could be viable:
- [StoryMap](https://storymap.knightlab.com/#examples) ([here](https://www.georgiahumanities.org/southern-literary-trail-story-map/) is an example of StoryMap in action)	
- [MapStore](https://mapstore.readthedocs.io/en/latest/user-guide/exploring-stories/)

To be clear, a story map would be a separate "feature" than the embedded maps on the timeline. But it's a great way to display any kind of content that has a location attachted to it. 

### Mobile version
Need to work on keeping design elements centered in mobile views. [Here](mobile-screenshot.PNG), for instance, the view-changing buttons look wonky. Maybe the elements should shrink as little bit when the viewport gets below a certain width, so that they can all fit on one line. 

### Stray observations
- When it is implemented I think the index will be a great way to get people into the letters. You might consider adding another category, which could go on the table of contents, that has some sort of curation. "Our favorite letters," "letters where Auden makes a joke," "letters containing poem drafts,"  or whatever (I don't know what the actual categories would be). The idea is to get people hooked if they stumble onto the page, so tantalize them with the juicy bits up front. 
- In terms of monospace typefaces: there are [several](https://docstips.com/google-docs-typewriter-fonts/) fonts available (free) through Google Fonts that are based on specific typewriter typefaces. If we know what kind of typewriter Auden and Musulin were using, it could be a cool touch to pick a typeface that approximates how the actual typed letters look. Regardless, I think "[courier prime](https://fonts.google.com/specimen/Courier+Prime?category=Monospace&query=courier+prime)" or "[cutive mono](https://fonts.google.com/specimen/Cutive+Mono?category=Monospace&query=cutive+mono)" would be good choices. 
- I think it might be helpful to have a small "vital statistics" table for each letter, with information like author, date, type of content, etc. With [this](https://auden-musulin-papers.github.io/amp-app/amp-transcript__0046.html) item, for example, it is hard to tell at a glance who is writing here and what this actually is.
- For the letter dated [1968-10-04](https://auden-musulin-papers.github.io/amp-app/amp-transcript__0042.html), it seems like the line breaks in the transcription of "August 1968" got lost somewhere.