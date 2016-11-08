# CSS Conventions

## Principles

**Make it modular**

The design system is modular in every way, which very much applies to the way CSS is written. There should be clear separation between components.

**Legibility is key**

Developers should be able to understand CSS code at a glance and understand the purpose of any given selector.

**Clarity trumps succinctness**

The design system may sometimes seem verbose, but it delivers clarity and reslience in exchange. Keeping CSS legible and scalable means sacrificing a shorter syntax.

**Keep things flat**

Long selector strings should be avoided wherever possible in order to keep CSS as DOM-independent and modular as possible.

**Avoid conflicts**

Since components will be deployed to many different applications, it’s critical to ensure that the design system’s CSS doesn’t conflict with other libraries and systems. This is accomplished by the system’s namespacing of class names, described in more detail below.

## Rules

### Global Namespace

All classes associated with the design system are prefixed with a global namespace, which is the Company Name followed by a hyphen:

```css
.cn- {}
```

In the case of **laruche**, the global namespace is:

```css
.lio- {}
```

> If you’re working on a CSS architecture that is only meant to be served to a single site or if you have a lot of control over your environment, this rule is not mandatory.

### Class Prefixes

In addition to a global namespace, we add prefixes to each class to make it more apparent what job that class is doing:

-   **c-** for UI components, such as `.lio-c-card` or `.lio-c-header`
-   **l-** for layout-related styles, such as `.lio-l-grid__item` or `.lio-l--two-column`
-   **u-** for utilities, such as `.lio-u-margin-bottom-double`.
-   **is-** and **has-** for specific states, such as `.lio-is-active` or `.lio-is-disabled`.
-   **js-** for targeting JavaScript-specific functionality, such as `.js-modal-trigger`. No styles are bound to these classes; they’re reserved for behavior only. For most cases, these js- classes would toggle state-based classes to an element.

> More on the [article](http://csswizardry.com/2015/03/more-transparent-ui-code-with-namespaces/) by Harry Roberts

### BEM Syntax

We use the [BEM](http://getbem.com/) syntax (Block, Element, Modifier).

## Inspirations

A lot of these conventions are largely inspired by:

-   [Harry Roberts - More Transparent UI Code with Namespaces](http://csswizardry.com/2015/03/more-transparent-ui-code-with-namespaces/)
-   [Harry Roberts - MindBEMding – getting your head ’round BEM syntax] (http://csswizardry.com/2013/01/mindbemding-getting-your-head-round-bem-syntax/)
-   [Brad Frost - CSS Architecture For Design Systems](http://bradfrost.com/blog/post/css-architecture-for-design-systems/)
