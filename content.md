<!-- .slide: data-background="media/img/aframe.jpg" -->

<div class="talk-title">
  <h1>A-Frame</h1>
  <p>A web framework for building VR experiences</p>
  <p class="talk-info">
    @andgokevin | Mozilla VR | **aframe.io**
  </p>
</div>

<!-- NOTES -->
- Onboard web developers into the 3D and VR world with easy-to-use tools
- Prototype WebVR experiences faster

------

## Friction of VR Ecosystems

<div class="captioned-image-row">
  <div>
    <img data-src="media/img/gatekeeper.png">
    <i>Gatekeepers</i>
  </div>
  <div>
    <img data-src="media/img/downloads-installs.png">
    <i>Installs</i>
  </div>
  <div>
    <img data-src="media/img/closed-door.png">
    <i>Closed</i>
  </div>
</div>

<!-- NOTES -->
- App stores and corporations control distribution: can take down or block content
- Downloads / installs are a barrier to consumption: small business pages
- Closed ecosystem: proprietary engines, steep learning curves, siloed experiences, fragmentation
- We want VR to be successful, so we want a platform without these points of friction. The answer is WebVR...

------

# WebVR

An open virtual reality platform with the advantages of **the Web**

<div class="captioned-image-row">
  <div>
    <img data-src="media/img/web-is-open.png">
    <i>Open</i>
  </div>
  <div>
    <img data-src="media/img/web-is-connected.png">
    <i>Connected</i>
  </div>
  <div>
    <img data-src="media/img/web-is-instant.png">
    <i>Instant</i>
  </div>
</div>

<!-- NOTES -->
WebVR is...virtual reality in the browser, powered by the Internet

Open:
- Anyone can publish
- Open source culture with open standards

Connected:
- Traverse worlds

Instant:
- Click a link on Twitter or Weibo, immediate VR experiences
- No installs
- Imagine for long tail experiences: shopping & personal spaces
- Great for long tail bite-sized experiences

Transition:
- Web has advantages that make it the best platform for the people
- Need to act to make it reality, can't wait for VR to bake and crystallize
- Get involved

------

<img class="stretch" data-src="media/img/webvr.png">

Browser APIs that enable WebGL rendering to headsets and access to VR
sensors

https://w3c.github.io/webvr/

<!-- NOTES -->
API:
- Optimized rendering path to headsets
- Access position and rotation (pose) data

History:
- Initial WebVR API by Mozilla
- Working W3C community group
- Mozilla, Google, Samsung, Microsoft, community currently iterating WebVR 1.0 API

Not just a specification, it's implemented...

------

<div class="captioned-image-row">
  <div>
    <img data-src="media/img/firefox-nightly.png">
    <i>Firefox Nightly</i>
  </div>
  <div>
    <img data-src="media/img/chromium.png">
    <i>Chromium (Experimental)</i>
  </div>
  <div>
    <img data-src="media/img/samsung-browser.png">
    <i>Samsung Internet</i>
  </div>
  <div>
    <img data-src="media/img/google-cardboard.png">
    <i>Mobile Polyfill</i>
  </div>
</div>

<!-- NOTES -->
- Firefox + Chrome WebVR 1.0 hits release channels by early 2017
- Currently behind Nightly, custom builds, and flags
- Mobile Polyfill: use device motion / orientation sensors to polyfill on smartphones
- With all the browsers behind it...

------

<!-- .slide: data-background-video="media/video/boilerplate.mp4" data-state="state--bg-dark" -->

<div class="slide__boilerplate">
  <p>Import WebVR polyfill</p>
  <p>Set up camera</p>
  <p>Set up lights</p>
  <p>Initialize scene</p>
  <p>Declare and pass canvas</p>
  <p>Listen to window resize</p>
  <p>Install VREffect</p>
  <p>Instantiate renderer</p>
  <p>Create render loop</p>
  <p>Preload assets</p>
  <p>Figure out responsiveness</p>
  <p>Deal with metatags and mobile</p>
</div>

<!-- NOTES -->
- It's still too difficult to create WebVR experiences
- Huge obstacle if doing small prototypes and experiments
- Boilerplate needs updating with new versions of WebVR, three.js, and browser quirks
- Encapsulate all of that into one line...

------

## Hello World

<!-- .slide: data-background="media/img/aframe.png" data-transition="slide-in none" -->

```html
<html>
  <script src="https://aframe.io/releases/0.3.2/aframe.min.js"></script>
  <a-scene>





  </a-scene>
</html>
```
<!-- .element: class="stretch" -->

<!-- NOTES -->
- Just HTML
- Drop a script tag, no build steps
- Using Custom HTML Elements
- One line of HTML `<a-scene>` handles
  - canvas, camera, renderer, lights, controls, render loop, WebVR polyfill, VREffect
- Put stuff inside our scene...

------

## Hello World

<!-- .slide: data-background="media/img/aframe.png" data-transition="fade-in slide-out" -->

```html
<html>
  <script src="https://aframe.io/releases/0.3.2/aframe.min.js"></script>
  <a-scene>
    <a-box color="#4CC3D9" position="-1 0.5 -3" rotation="0 45 0"></a-box>
    <a-cylinder color="#FFC65D" position="1 0.75 -3" radius="0.5" height="1.5"></a-cylinder>
    <a-sphere color="#EF2D5E" position="0 1.25 -5" radius="1.25"></a-sphere>
    <a-plane color="#7BC8A4" position="0 0 -4" rotation="-90 0 0" width="4" height="4"></a-plane>
    <a-sky color="#ECECEC"></a-sky>
  </a-scene>
</html>
```
<!-- .element: class="stretch" -->

<!-- NOTES -->
- Basic 3D primitives with Custom Elements
- Readable: HTML arguably most accessible language in computing
- Encapsulated: copy-and-paste HTML anywhere else and still work, no state or variables
- Quickly look at a live example...

------

## Hello Metaverse

<i>by Ada Rose Edwards (@lady_ada_king)</i>

<!-- .slide: data-background="media/img/metaverse.png" -->

<div class="stretch" data-aframe-scene="scenes/80s.html"></div>

<!-- NOTES -->
- A-Frame scene by Ada Rose Edwards running from inside my HTML slides
- Works on desktop, Android, iOS, Samsung Gear VR, Oculus Rift, HTC Vive
- Could open up the DOM Inspector to change values live
- Since it's just HTML...

------

<!-- .slide: data-background="media/img/aframe.jpg" -->

## Works With Everything

<div class="captioned-image-row">
  <div>
    <img data-src="media/img/d3.png">
    <i>d3.js</i>
  </div>
  <div>
    <img data-src="media/img/vue.png">
    <i>Vue.js</i>
  </div>
  <div>
    <img data-src="media/img/react.png">
    <i>React</i>
  </div>
  <div>
    <img data-src="media/img/redux.png">
    <i>Redux</i>
  </div>
  <div>
    <img data-src="media/img/jquery.png">
    <i>jQuery</i>
  </div>
  <div>
    <img data-src="media/img/angular.png">
    <i>Angular</i>
  </div>
</div>

<!-- NOTES -->

- Based on HTML, compatible with all existing libraries/frameworks
- Good reason to have HTML as an intermediary layer between WebGL/three.js
- All tools were on top of the notion of HTML
- Under the hood, A-Frame is an extensible, declarative framework for three.js...

------

# Entity-Component-System

<!-- .slide: data-background="media/img/minecraft-blocks.png" -->

<!-- NOTES -->
- Is an entity-component framework
- Popular in game development, used by Unity
- All objects in scene are **entities** that inherently empty objects. Plug in
  **components** to attach appearance / behavior / functionality
- Not going to go into detail about the syntax for this
- 2D web where every element was fixed
- 3D/VR is different, objects of infinite types and complexities, need an easy way to build up different kinds of objects

------

<!-- .slide: data-background="media/img/standard-components.png" data-background-size="contain" -->

<!-- NOTES -->
- These are some components that ship with A-Frame
- A-Frame is fully extensible at its core so...

------

<!-- .slide: data-background="media/img/community-components.png" data-background-size="contain" -->

<!-- NOTES -->
- the community has filled the ecosystem with tons of components
- Components can do whatever they want, have full access to three.js and Web APIs
- The component ecosystem the lifeblood of A-Frame
- Physics, leap motion, particle systems, audio visualizations, oceans
- Drop these components as script tags and use them straight from HTML
- Advanced developers empowering other developers
- Working on collecting these components...

------

<div class="icon-title">
  <img data-src="media/img/registry.png" width="64">
  <h2>Registry</h2>
</div>

<!-- .slide: data-background="media/img/aframe-side.png" -->

Curated collection of A-Frame components/shaders.

<a class="stretch" href="https://aframe.io/aframe-registry">
  <video loop data-src="media/video/registrypreview.mp4" data-autoplay></video>
</a>

<!-- NOTES -->
- Collecting them into the A-Frame registry
- Like a store of components that we make sure work well
- People can browse and search for components or install them....

------

## Inspector

<!-- .slide: data-background="media/img/inspector.png" data-state="state--bg-dark" -->

Visual tool for A-Frame. Just `<ctrl>+<alt>+i`.

<div class="stretch" data-aframe-scene="scenes/80s.html"></div>

------

<!-- .slide: data-background-video="media/video/a-painter.mp4" data-background-video-muted="true" data-state="state--bg-dark" -->

## A-Painter

Paint in VR in the browser.

<!-- NOTES -->
- A-Frame is very powerful
- 90+fps room-scale TiltBrush experience in a few weeks with just A-Frame

------

# aframe.io

<div class="captioned-image-row">
  <div>
    <img data-src="media/img/github.png">
    <i>75 contributors 3500 Stargazers</i>
  </div>
  <div>
    <img data-src="media/img/slack.png">
    <i>1750 members on Slack</i>
  </div>
  <div>
    <img data-src="media/img/scene-collage-circle.png">
    <i>100s of featured projects</i>
  </div>
</div>

<!-- NOTES -->
- Open source and inclusive project
- Most work done on GitHub
- Active community on Slack to share projects, interact, hang out, seek help
- Featured projects on the `awesome-aframe` repository and *A Week of A-Frame* blog
