<img src="https://2019.cssconf.eu/immutable/391be65c204237507388b841cd3b3f0321417571/svg/intro.svg" alt="CSSconfEU 2019" width="300">

- Date: 31st May 2019
- Location: Arena Berlin, Berlin :de:
- [Website](https://2019.cssconf.eu/)

## General remarks

- Diversity. It was heart-warming to be in a space where diversity of all kinds was safely promoted, accepted and celebrated. Small things like "Sit/stand" toilet signs and preferred pronouns on lanyards require no additional overhead to implement but are a hard-and-fast sign of an active effort by the organisers to include all. The large number of female and minority attendees proved that the effort was worth it. Thank you
- [Firefox Grid Inspector](https://developer.mozilla.org/en-US/docs/Tools/Page_Inspector/How_to/Examine_grid_layouts) is :fire:
- Sketchnotes from [@clairikine](https://twitter.com/clairikine), [@SarahOnDaCloud](https://twitter.com/SarahOnDaCloud), [@lisi_linhart](https://twitter.com/lisi_linhart) and [@wilfredspringer](https://twitter.com/wilfredspringer) :heart:
- Printed exhibition of the [A Computer Of One's Own](https://medium.com/a-computer-of-ones-own) series was incredible. [Video](https://twitter.com/cramforce/status/1134482967349383170)
- Breakfast, lunch, afternoon cake, dinner, frozen yoghurt, coffee, beer, wine, cocktails, gummy bears. I had to remind myself I was at a web development conference and not a food convention. Delicious!

## Talks

### [Why do we call HTML tags "tags"?](https://2019.cssconf.eu/speakers/andres-cuervo/) by [Andrés Cuervo](https://twitter.com/acwervo)

- [Slides](https://slides.cwervo.com/mdx-slides/css-conf-eu-2019)
- 'Tag' in first HTML draft (by Tim Berners-Lee in 1995) took its name from SGML which took its name from GML (general markup language) created by Charles Goldfarb of IBM in 1960s
- First use of 'tag' in computing by Emil Leon Post (suggested to him by B.P. Gill) in 1943 where his computational system appended information from the previous string onto the next. Passing on like children's game of tag
- Game of 'tag' exists back to 1700s

### [Hello subgrid!](https://2019.cssconf.eu/speakers/rachel-andrew/) by [Rachel Andrew](https://twitter.com/rachelandrew)

- [Slides](https://noti.st/rachelandrew/i6gUcF/hello-subgrid)
- `display` property doesn't cascade. Only direct children become `flex`/`grid` items
- `grid` siblings are not aware of each other. Used [example of card layout](https://noti.st/rachelandrew/i6gUcF/hello-subgrid#sPzaaQr) with flexible header, content, footer. One card may have a bigger footer but siblings don't know this
- `display: contents` 'removes' parent from layout meaning children flow together. Not useful where multiple children envolved (like above example). Currently breaks accessibility
- `grid-template-columns: subgrid` creates a grid on a child element using parent's `grid` tracks (rows, cols or both)
- Subgrid numbering resets to 1 on child grid, doesn't use parents (if offset from left, for example)
- Good practice to name grid rows/cols. Already available with `grid` but not widely used as unnecessary
- `gap`s inherited from parent but can also be adjusted on children if wanting to close/increase a `gap`
- Currently no production browser support. Firefox Nightly has support
- > If you wait until a spec is done and implemented to look at it and say it's rubbish, it's too late
- With fewer rendering engines, it's important that devs (us in the room!) get involved with defining and giving feedback on the specs
- [Chromium issue for subgrid](https://bugs.chromium.org/p/chromium/issues/detail?id=618969)
- Give feedback to the [CSS Working Group](https://github.com/w3c/csswg-drafts/issues)

### [Using DevTools to understand modern CSS layouts](https://2019.cssconf.eu/speakers/chen-hui-jing/) by [Chen Hui Jing](https://twitter.com/hj_chen)

- [Sketchnotes](https://twitter.com/hj_chen/status/1134701662470361093)
- Browsers are very good at sizing boxes based on their content. Use this!
- `width: min-content` and `width: max-content` set intrinsic widths on boxes. The browser won't break words
- > Flexbox - where nobody knows the exact size of anything!
- Learn `flex-basis` properly
- Use Firefox Dev Tools Flex and Grid Inspector
- Distribution of free space is important
- `fr` unit takes up available free space
- `auto` holds its width whilst free space is allocated elsewhere
- `auto` will give up/allow `minmax()` free space
- Use a mixture of units on `flex`/`grid` items to achieve flexible responsive sizing :fire:
- Use `flex` auto-margins to push content to one side (`margin-right: auto`) or to center items (`margin: auto`). Use on siblings to center based on equally split parent box

### [Modern Typographic Systems with Variable Fonts](https://2019.cssconf.eu/speakers/jason-pamental/) by [Jason Pamental](https://twitter.com/jpamental)

- [Slides](https://noti.st/jpamental/2gsS6v)
- > Type is the voice of our words. It's how we 'hear' what we read
- We don't want the same type scale across responsive screen sizes. Use a scale and CSS Custom Properties to finely adjust properties as needed
- > A variable font is a single font file that acts like multiple font files
- Variable fonts have embedded propeties such as `font-weight`, `font-stretch` and `font-style` where we can define a degree-based slant
- ['CSS Locks' by Tim Brown](https://blog.typekit.com/2016/08/17/flexible-typography-with-css-locks/) defines a formula for scaling `font-size` between a defined min and max setting
- Be careful with setting based purely on viewport width as page can no longer be zoomed. Bad for accessibility
- > The role of the typographer has changed. We no longer decide; we make suggestions
- Users have control over their own experience via device size, dark mode, text size, zoom, accessibility features etc
- OS dark-mode (`@media (prefers-color-scheme: dark)`) can be used to adjust for better reading experience for visually impaired
- Reading cognition for people with certain forms of dyslexia can improve by 50% with increased line spacingw
- > Put these controls in the hands of the users
- For example, an accessibility panel on your website. CSS Custom Properties means nearly zero overhead/cost to implement
- IBM Plex Sans recently released as variable font. Previously 16 files @ 960Kb, now two files @ 233Kb!
- Firefox Font panel allows you to adjust variable font properties like `font-weight` using a slider. Non-tech designer could adjust in browser then send dev the results in the Changes panel :fire:
- Watch out for: "Progressive Font Enrichment" in next 2-3 years. Browser reads page content and then serves only glyphs actually used
- Example of first book of Homer's Odyssey: only 25-33% of Latin character set actually used! Potentially massive performance gains for Asian languages with 10,000s available characters

### [Don’t Believe the Rumors: Writing Tests for CSS is Possible](https://2019.cssconf.eu/speakers/gil-tayar/) by [Gil Tayar](https://twitter.com/giltayar)

- Egoprogrammophobia: The fear of one's own code
- Testing abolishes fear!
- Back-end devs and JS devs can easily write tests. Input -> Test algorithm -> Expected result
- Front-end testing is visual. Machines are not good enough to test column widths, responsiveness, layout, design, behaviour
- Visual regression testing to the rescue!:
  1. Take screenshot
  2. Compare with baseline screenshot
  3. Dev decides whether to accept diff of not
- BUT. Elephants in the room :elephant:
  1. *Taking screenshots is hard.* Many different screen widths, browsers, OS for each page. Use a tool like [Cypress](https://www.cypress.io/) to automate
  2. *Comparing screenshots is hard.* Pixel-by-pixel comparison can still turn up differences due to graphic drivers on different machines or other unknown reasons. Some tools (such as [Applitools](https://applitools.com/features#visual-ai) use machine learning to determine insignificant diffs
  3. *Managing comparisons is hard.* Again, Cypress provides a good interface for accepting/rejecting diffs
  4. *You need to run tests multiple times.* Cloud solutions allow you to parallelise your tests :thumbs-up:
- > Fear is the mindkiller. Where fear has gone, there will be nothing. Only my CSS tests will remain! :muscle:


### [Let’s web dev like it’s 1999!](https://2019.cssconf.eu/speakers/ben-ilegbodu/#talk) by [Ben Ilegbodu](https://twitter.com/benmvp)

- [Slides]()
- > It's right after lunch so let's all do ten squats to get the blood pumping and stop us from falling asleep :joy: :muscle:
- Nostalgic journey rather than learning new stuff
- Remember when we used to write in ALL CAPS!
- "This website is best viewed at 800x600px in AOL. If you're using Internet Explorer or Netscape Navigator then you should also be ok" :joy:
- `<FRAMESET>` magic, `<FONT>` all the things, hit counters, polls, Comic Sans, uploading directly to live with FTP!
- Mainly used CSS for adding hover styles to links :heart-eyes:
- Spacer gifs, non-breaking spaces and sliding doors technique for rounded corners :heart-eyes:
- And then along came Firebug and it was never the same again. Truly revolutionary. I can see what my code is doing!
- Imposter syndrome. Everyone gets it. But even if you started yesterday, some day you could be an integral part of the community. We all have to start somewhere. YOU GOT THIS!


### [Improving Website Performance with CSS Containment](https://2019.cssconf.eu/speakers/manuel-rego/#talk) by [Manuel Rego](https://twitter.com/regocas)

- [Slides](https://noti.st/rego)
- Works by isolating subtrees so changes in that subtree don't get propagated outside
- > `contain` property doesn't block things going into the subtree, it blocks things leaking out
- `contain` property has values of `layout`, `paint` and `size`. Currently also `style` for text although this will likely be dropped due to only obscure use cases
- `layout`: internal layout is isolated from the rest of the page. Containing block of `position: absolute` items, creates a new stacking context, overflow is treated as 'ink overflow' (still shown but isolated)
- `paint`: children aren't shown outside the bounds of the parent (similar to `overflow: hidden`). Appears to allow for masking in CSS :fire:
- `size`: treated as having no contents
- `style`: counters and quotes can be nested with original parent context kept
- Aliases for `content` (`layout`, `paint` ~`style`~) and `strict` (`layout`, `paint`, `size`, ~`style`~)
- Browser knows it doesn't have to re-paint potentially effected elements so can drastically reduce browser repaints. With 10,000s nodes, this could mean up to over 1s just in paint savings from one property
- Implemented in Chrome for three years but few performance improvement implementations so far. Both Chrome and Firefox working on it


### [CSS Logical Properties](https://2019.cssconf.eu/speakers/estefany-aguilar/#talk) by [Estefany Aguilar](https://twitter.com/teffcode)

- CSS properties are currently 'physical' and arranged around western languages and constructs (from top-right reading left-to-right). For eastern languages, this leads to confusion. Arabic is right-to-left. Mandarin is top-to-bottom. Property naming isn't fit for purpose in these languages
- Also when using different orientation such as `writing-mode`. Properties no longer act as expected
- CSS Logical Properties introduce alternative naming conventions for `-top`, `-right`, `-bottom` and `-left`
- Vertical orientation is named `block` after `display: block` (top-to-bottom).  Horizontal orientation is named `inline` after `display: inline` (left-to-right)
- Direction is indicated by `start` and `end`
- Therefore, `padding-left` becomes `padding-inline-start`, `margin-bottom` becomes `margin-block-end`, `border-right` becomes `border-inline-end`...
- [CSS Logical Properties @ Can I Use](https://caniuse.com/#feat=css-logical-props)
- CSSconf Colombia is the newest member of the CSSconf family :tada:


### [Class Clash](https://2019.cssconf.eu/speakers/alex-tait/#talk) by [Alex Tait](https://twitter.com/AT_Fresh_Dev)

- Functional CSS. Each class has one purpose
- Properties of functional CSS:
  - Immutability
  - Single purpose
  - Reusability
  - Composition
  - No side effects
- The haters say:
  - "My HTML is ugly!"
  - No separation of concerns
  - Not DRY
  - Not semantic
- To love:
  - Small bundle
  - Increased productivity
  - Reusability
  - Thinking in design systems
- What problems can it solve:
  - Performance and CSS bloat
  - Scalability
  - Decoupling styles and structure
  - Minimising context switching between browser and editor
- Comparison with functional programming:
  - `function` = markup
  - input = classes
  - output = what's rendered
- Try [Tachyons](http://tachyons.io/) (tacky-ons)


### [A Working Theory Of Components](https://2019.cssconf.eu/speakers/elyse-holladay/#talk) by [Elyse Holladay](https://twitter.com/elyseholladay)

- [Slides](http://www.elyseholladay.com/theory/)
- > The tools we have today didn't even exists ten years ago!
- In 1846, French astronomer [Urbain Le Verrier](https://en.wikipedia.org/wiki/Urbain_Le_Verrier) correctly predicted the existence of the planet Neptune based only on the orbit of Neptune and the mathematical work of Isaac Newton
- Conversely, the orbit of Mercury didn't fit the existing models and Le Verrier was convinced that a planet (which he named Vulcan) had to be situated between the Sun and Mercury. This was eventually disproved by [Einstein's General relativity](https://en.wikipedia.org/wiki/General_relativity)
- Science is constant iteration. So is software development
- Theory over tools
- When we find gaps in our knowlegde, it doesn't mean the theory is wrong
- Elyse's proposed working theory. A component must be:
  - Easy to reason about
    - Not too easy but not too complex
    - The right amount of flexibility
  - Context agnostic
    - The component doesn't need to know where it is to look and behave properly (accessible and cross-browser)
    - Should be reusable
  - Independent and isolated
    - Looks correct no matter the environment
    - Sensible defaults
    - Imports own dependencies
    - Can be tested with confidence
- > As we work together today and tomorrow and in the months and years to come, keep thinking beyond today’s understanding of the world, and on to tomorrow’s


### [Design System Magic with CSS Houdini](https://2019.cssconf.eu/speakers/samuel-richard/#talk) by [Samuel Richard](https://twitter.com/Snugug)

- [Slides](https://css-houdini.web.app/talks/design-systems/#/0)
- [CSS Houdini](https://css-houdini.web.app/talks/design-systems/#/24)
- Can it be used? Nope!
- Extending CSS with JS
- 'Worklets' are extension points for rendering engines
- Typed OM makes it possible to register properties ([such as CSS Custom Properties](https://css-houdini.web.app/talks/design-systems/#/57)) making them more predictable and performant
- We can tack additional pieces of functionality onto CSS which is then modifiable...with CSS
- Some of the more advanced examples Sam showed with the [Paint API](https://css-houdini.web.app/talks/design-systems/#/67) and [Layout API](https://css-houdini.web.app/talks/design-systems/#/85) were a little over my head so I'd suggest checking out his slides for more details
- Dino shirt :dinosaur:


### [Closing Keynote](https://2019.cssconf.eu/speakers/sareh-heidari/#talk) by [Sareh Heidari](https://twitter.com/Sareh88)

- Sareh stepped in at very short notice to present the keynote after Nicole Sullivan had to pull out for health reasons and she presented a very emotional and heartfelt tribute to CSSconfEU as the last ever speaker on the stage at the final event :cry:
- She highlighted the [CSS Classes event](https://cssclass.es/), [diversity scholarship program](https://2019.cssconf.eu/scholarships/), [The Community Lounge](https://2019.cssconf.eu/community-lounge/), [Ramadan quiet space and prayer room](https://2019.cssconf.eu/ramadan/) and the open call for proposals as important values, initiatives and goals of the CSSconf organisation
- We were also encouraged to share our skills and experiences and "pay it forward" to people just getting into the industry. A message that echoed what many speakers had emphasised throughout the day
- Build communities where you can. They may start small but can eventually grow into something big
- Be inclusive and respectful

:heart:

<a href="https://twitter.com/CSSconfeu/status/1134506915755712512" target="_blank"><img src="https://pbs.twimg.com/media/D76UBamXkAAPlqp.jpg" alt="Family photo" width="500"></a>
