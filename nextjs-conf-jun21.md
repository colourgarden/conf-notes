# Next.js Conf 2021

<img src="https://upload.wikimedia.org/wikipedia/commons/thumb/8/8e/Nextjs-logo.svg/207px-Nextjs-logo.svg.png" alt="Next.js logo" width="207">

- Date: 15th June 2021
- [Website](https://nextjs.org/conf)

## Speakers

- [Guillermo Rauch](https://twitter.com/rauchg), CEO @ Vercel
- [Shubhie Panicker](https://twitter.com/shubhie), Engineer @ Google
- [Houssein Djirdeh](https://twitter.com/hdjirdeh), Engineer @ Google
- [Lydia Hallie](https://twitter.com/lydiahallie), Freelancer Engineer
- [Tim Neutkens](https://twitter.com/timneutkens), Next.js Lead @ Vercel
- [Alex Castle](https://twitter.com/atcastle), Engineer @ Google

## Keynote remarks

- :tada: [Next.js 11 launched](https://nextjs.org/blog/next-11)
- 1600 community developers in 5 years
- Last six months, 50% increase in downloads to 6.2m

## Topics

### Next.js Live

- Key goal for Next.js is balancing UX and DX which leads to...
- [Next.js Live](https://nextjs.org/live) - realtime coding and collaboration tool
- Next.js app published to a public URL with VSCode in the browser allowing edits to be pushed out automatically to collaborators
- Adds minimal changes on top of browser APIs (Service Workers, WebAssembly etc)

### `<Image>` component

- Image component (introduced in October 2020) now supports blurred placeholder images to aid perceived loading performance. Simply add `placeholder="blur"` and `blurDataUrl`
- Main goal is to help with LCP
- Will also automatically add `width` and `height` attributes to static images imported to your app which helps to reduce CLS

### `<Script>` component

- New `<Script>` component to define loading strategy of third-party scripts
  - `beforeInteractive` for critical things like security, webfonts
  - `afterInteractive` for tag managers, analytics
  - `lazyOnload` for things that can be loaded async at any time

### Conformance

- Google announced [Aurora project](https://web.dev/introducing-aurora/) - a collaboration between Chrome and open-source web frameworks and tools
  -  "We discovered how frameworks can play a crucial role in predictable app quality by providing strong defaults and opinionated tooling."
- Next 11 complies with the new [Google "Conformance" ecosystem](https://web.dev/conformance/)
  - Sensible defaults to help with "optimal loading and Core Web Vitals"
  - Google has published a Next.js ESLint preset plugin (used in Next 11) plus tooling for TypeScript, webpack and CSS
  - Other frameworks will be supported soon

## Remarks from Q&A

- Goal of Google Aurora is to collaborate and learn from open-source frameworks to then feed sensible defaults back to those same frameworks to establish good standards for web performance
- Shubhie - (paraphrasing) "it's not possible change every web app to load fonts optimally but if we (Google) can contribute good defaults then developers don't have to think about those problems"
- Next.js works a lot with other frameworks which means compatiblility
- Regular Next.js Conf will take place later in the year
- New `create-react-app` migration script via `npx @next/codemod cra-to-next`
  - Will automatically convert certain aspects of your project to implement Next.js best practices (including performance)
- Tim: Performance measuring in progress (can't say more but will integrate with third-party analytics tools like Datadog)
- Hussein: Google Conformance is mainly focussed on web performance (now a big part of Google ranking through Core Web Vitals) but will also provide hints if, for example, you use a `<Title>` component incorrectly
- Inlining critical CSS (called Optimize CSS by Google) is behind an experimental flag in Next 11 (good example of Google Conformance gaining and returning feedback on community standards)
- Incremental Static Regeneration (hybrid of SSG and SSR) is under development and looking for feedback from community on how they handle caching
- Guillermo: > Improving routing is being actively worked on. More soon

## Closing statements 

- Guillermo: There's a lot of improvements coming. Please give us feedback!
- Hussein: Shout out to Vercel team and allowing us to test. Shout out to Alex, Ralf, Gerald on Google side
- Shuhbie: We feel like we've landed on something good here in collaborating with frameworks and it is the way to go. Please send us feedback!
- Lydia: Thanks to Vercel for allowing representation of the community at their conference
- Alex: Excited about the collaboration between Google and Next.js (and frameworks in general) and how it's going to make developers' lives easier by allowing them to concentrate on the fun stuff
- Tim: These topics aren't actually new - Next.js has been working with Google for nearly two years. Thanks. If you're new to Next.js then head to nextjs.org/learn
