# Disclaimer

**THIS IS NOT THE [LIT-ELEMENT](https://github.com/Polymer/lit-element) YOU ARE LOOKING FOR!**

If you are looking for the [lit-element](https://github.com/Polymer/lit-element) project, you are in the wrong place buddy!

**[BAIL OUT NOW!](https://github.com/Polymer/lit-element)**

## What is this then?

This is a project based on the original [lit-element](https://github.com/Polymer/lit-element) package. This project is the result of (slightly) modifying the output from compiling the project.

I make no promise of maintaining.

## Reasoning for this project

This version aims to provide an entirely staticly hosted solution for [Web Components](https://webcomponents.org) using the lit-element interface, without the need for support from the Polymer cli tooling.

I beleive in the web being as static as possible.

The more compiling and tooling we need to create in order to deliver just adds more noise to projects, and raises the bar-for-entry to any new starters. It also creates more time spend, before value can be added.

I also believe the old browsers should die in a tragic, but maybe not so accidental, house fire, that completely obliterated all reference to their source-code. _\*\*cough\*\*_ _\*\*cough\*\*_ **Internet Explorer** _\*\*cough\*\*_ _\*\*cough\*\*_

It just so happens, we are moving into an age where the future of JavaScript is now, and even the Edge team are bailing on their hot mess.

We should go back to basics. Learn the standards, and drop the tooling!

<br>
<br>

# LitElement
A simple base class for creating fast, lightweight web components with [lit-html](https://lit-html.polymer-project.org/). **But this time, it's static!**

## Documentation

Full documentation is available at [lit-element.polymer-project.org](https://lit-element.polymer-project.org).

## Overview

LitElement uses [lit-html](https://lit-html.polymer-project.org/) to render into the
element's [Shadow DOM](https://developer.mozilla.org/en-US/docs/Web/Web_Components/Using_shadow_DOM)
and adds API to help manage element properties and attributes. LitElement reacts to changes in properties
and renders declaratively using `lit-html`. See the [lit-html guide](https://lit-html.polymer-project.org/guide)
for additional information on how to create templates for lit-element.

```ts
import {LitElement, html, css, customElement, property} from 'lit-element';

// This decorator defines the element.
@customElement('my-element')
export class MyElement extends LitElement {

  // This decorator creates a property accessor that triggers rendering and
  // an observed attribute.
  @property()
  mood = 'great';

  static styles = css`
    span {
      color: green;
    }`;

  // Render element DOM by returning a `lit-html` template.
  render() {
    return html`Web Components are <span>${this.mood}</span>!`;
  }

}
```

```html
    <my-element mood="awesome"></my-element>
```

Note, this example uses decorators to create properties. Decorators are a proposed
standard currently available in [TypeScript](https://www.typescriptlang.org/) or [Babel](https://babeljs.io/docs/en/babel-plugin-proposal-decorators). LitElement also supports a [vanilla JavaScript method](https://lit-element.polymer-project.org/guide/properties#declare) of declaring reactive properties.

## Examples

  * Runs in all [supported](#supported-browsers) browsers: [Glitch](https://glitch.com/edit/#!/hello-lit-element?path=index.html)

  * Runs in browsers with [JavaScript Modules](https://caniuse.com/#search=modules): [Stackblitz](https://stackblitz.com/edit/lit-element-demo?file=src%2Fmy-element.js), [JSFiddle](https://jsfiddle.net/sorvell1/801f9cdu/), [JSBin](http://jsbin.com/vecuyan/edit?html,output),
[CodePen](https://codepen.io/sorvell/pen/RYQyoe?editors=1000).

  * You can also copy [this HTML file](https://gist.githubusercontent.com/sorvell/48f4b7be35c8748e8f6db5c66d36ee29/raw/67346e4e8bc4c81d5a7968d18f0a6a8bc00d792e/index.html) into a local file and run it in any browser that supports [JavaScript Modules]((https://caniuse.com/#search=modules)).

## Installation

From inside your project folder, run:

```bash
$ npm install lit-element
```

To install the web components polyfills needed for older browsers:

```bash
$ npm i -D @webcomponents/webcomponentsjs
```

## Supported Browsers

The last 2 versions of all modern browsers are supported, including
Chrome, Safari, Opera, Firefox, Edge. In addition, Internet Explorer 11 is also supported.

Edge and Internet Explorer 11 require the web components polyfills.

## Contributing

Please see [CONTRIBUTING.md](./CONTRIBUTING.md).