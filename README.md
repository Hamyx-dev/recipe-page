# Sobolo Recipe Page

This is what I built for the assignment to create a recipe page using only HTML and CSS, no JavaScript and no AI generated code. I picked sobolo, which is a Ghanaian hibiscus drink, as my recipe.

## What I Built

I built a recipe page with an image and title at the top, a preparation time section, an ingredients list, step by step instructions and a nutrition table. I used semantic HTML tags for each section instead of just divs, and I used Flexbox for the preparation time row and Grid for the ingredients list, since the assignment specifically asked for both.

## The HTML Structure

I wrapped the whole page in an article and a main tag, then used a separate section for each part of the recipe, hero section, preparation time, ingredients, instructions and nutrition. I used ul for the ingredients list and ol for the instructions, since the assignment said to use the correct tag for the type of content, ul for things with no order and ol for steps that have to happen in a specific order.

For the nutrition section I used an actual table element with th for the labels and td for the values, instead of just styling a list to look like a table.

## The CSS

### Flexbox on preparation time

I put display flex on the ul inside recipe-info so Total, Preparation and Cooking sit in a row instead of stacking. I learnt that the flex property has to go on the parent, the ul, not on each li, because display flex tells an element how to arrange its own children, not how it relates to its siblings.

### Grid on ingredients

I used display grid with grid-template-columns repeat(2, 1fr) on the ingredients ul, which means 2 equal columns. I learnt repeat(2, 1fr) is shorthand for writing 1fr 1fr, it just saves typing when you want several equal columns.

### Custom numbered badges on instructions

This was my first time using counter-reset, counter-increment and content together, so I left comments directly in my CSS at the exact lines where I used them. In short, counter-reset sets up a counter starting at 0 on the ol, counter-increment adds 1 to it every time the browser reaches a new li, and content inside the ::before pulls in whatever number the counter is currently at, so I get my own numbered circle badges instead of the plain browser numbering.

### Typography

I used Playfair Display, a serif font, for my headings, and Lato, a sans serif font, for body text, paragraphs, list items and table cells. I applied this with plain element selectors like h1, h2 and p, li, td, th instead of repeating the font-family on every single section, since those selectors already apply to every matching tag on the page.

### Colors

Since the page is about a hibiscus drink, I moved away from a plain earthy brown and used a deep red, close to the actual color of brewed hibiscus, as my accent color across headings, the ingredient bullets, the instruction badges and the nutrition values. For the preparation time section I used a vibrant pink to orange gradient instead of a flat pale color, since I wanted that section to feel more catchy.

### Image handling

I used object-fit cover on the hero image so it fills its box completely without stretching or distorting, no matter the original photo's proportions. I learnt object-fit only works on things like img or video, it does nothing if you put it on a section or div by mistake, which is a mistake I made at first.

### Hover effects

I added a hover effect on the hero image that scales it up slightly, contained inside the recipe-top section with overflow hidden so the zoomed image does not spill past its rounded corners. I added a hover effect on each ingredient that gives it a soft background tint and a small left padding nudge, so it feels like it lights up as you scan down the list. I also added a hover effect on the whole main card that lifts it up slightly with a deeper shadow, instead of scaling it bigger like I did on my other card project, so it would not feel like the exact same effect repeated. I added one more hover effect on the preparation time section itself, it lifts up slightly with translateY and switches from the pink to orange gradient to a flat soft pink, giving it its own little reaction when you hover over it.

### Entrance animation

I added a slide in animation on the main card using keyframes, but I made it different from the fade and slide up animation I used on my 3 column card project. This one slides in from the left using translateX instead of translateY, so the card enters sideways instead of rising from below.

## Mistakes I Made and Fixed

1. I tried to put object-fit on the recipe-top section instead of on the actual img tag, which did nothing since object-fit only works on elements like img or video.
2. I mixed display grid and flex-direction together on the same rule by mistake, which does not work because flex-direction is a flexbox only property and has no effect inside a grid container.
3. I put my flexbox display property on the li elements instead of on the parent ul, which meant each ingredient was trying to arrange its own children instead of all the items arranging themselves in a row.
4. My container did not have a real height, which meant align-items center had nothing to actually center against, so I had to switch to min-height 100vh.
5. I left the deprecated border="1" attribute on my table instead of styling the borders properly with CSS.
6. I pasted my Google Fonts link tags twice by accident while moving code around.

## What I Learnt

This project taught me the real difference between Flexbox and Grid, Flexbox is for laying things out in one direction, a row or a column, and Grid is for laying things out in two directions at once, rows and columns together, which is why it made sense for the ingredients list specifically. I also learnt that counters in CSS are a way to track and display your own numbering system separately from whatever HTML tag you are using, which gave me more control over how my instruction steps actually look instead of being stuck with the browser's default numbered list style.