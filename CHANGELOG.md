
<a name="0.2.7"></a>
# 0.2.7 (2017-11-14)

* **SemVer compatibility:** Copy of `0.2.3` to avoid breaking semantic versionning (I screwed up with `0.2.5` & `0.2.6` which needed angular5). Apps having `"angular-split": "^0.2.2"` inside their `package.json` shoudn't break anymore.


<a name="1.0.0-beta.4"></a>
# 1.0.0-beta.4 (2017-11-13)

* **Bug:** Code rewrite to calculate new `flex-basis` values to avoid unwanted size flickering on areas not linked to dragged gutter.
* **Comment:** Add an explanation comment on `split.component.ts` top.


<a name="1.0.0-beta.3"></a>
# 1.0.0-beta.3 (2017-11-12)

* **Feature:** Accept number & boolean params as string to allow template syntax like `<split gutterSize="12" disabled="true">...</split>` or `<split-area order="4" size="40" visible="true">...</split-area>`.
* **Feature:** Add a `gutterClick` event for usecases like toggling area between 0% & X%. Now all drag events and gutterSize return `{gutterNum: number, sizes: Array<number>}`. 


<a name="1.0.0-beta.2"></a>
# 1.0.0-beta.2 (2017-11-11)

* **Bug:** Fix bug when dragging gutter with previous area with `[visible]="false"` (bug there since the `[visible]` feature was added.. :( ).
* **Component access from JS/TS class:** You can now access `SplitComponent` and `SplitAreaDirective` as `ViewChild`/`ViewChildren` directly from your class to interact with.


<a name="1.0.0-beta.1"></a>
# 1.0.0-beta.1 (2017-11-10)

### Complete refactor, more robust, will be used as new base to add frequently asked features like `[minSize]` (pixel or percent) and custom style.

* **Allow area size init or drag to zero:** Refactor way to calcul area size `flex-basis: calc( X% - Ypx );` (seems easy at first sight but a bit painfull to implement). For example, you can now have 4 areas (with `[visible]="true"`), so 3 gutters, with sizes [0,0,0,100]. This was impossible before (size couldn't go down to 5%).
* **No more css `/deep/` use:** Could have used `::ng-deep` but I prefer to avoid it too.
* **Renderer2:** Use `Renderer2` instead of `Renderer` which is deprecated.


<a name="0.2.6"></a>
# 0.2.6 (2017-11-07)

* **UMD module fix:** Rollup config file wasn't correct.


<a name="0.2.5"></a>
# 0.2.5 (2017-11-06)

### Warning: Angular 5.0.0 minimum.

* **New files organisation:** Complete reorganisation of the github repository and files published on npm forked from this [library starter](https://github.com/robisim74/angular-library-starter).
* **New bundles generation:** Now you have umd bundles, flat ES module, and ES2015 flat ESM format.
* **Add tests:** This is what motivated me to change organisation, I will add others one soon `npm test`.


<a name="0.2.3"></a>
# 0.2.3 (2017-11-02)

* **Update package.json:** Moves dependencies to peerDependencies to be compatible with  angular 5.x [pr59](https://github.com/bertrandg/angular-split/pull/59).


<a name="0.2.2"></a>
# 0.2.2 (2017-08-04)

* **UMD bundle:** Add UMD bundle export thanks to [BenjaminDobler](https://github.com/BenjaminDobler).


<a name="0.2.1"></a>
# 0.2.1 (2017-07-18)

* **license:** Add an Apache license.
* **dependancies:** Update `rxjs` version inside `package.json`.


<a name="0.2.0"></a>
# 0.2.0 (2017-03-30)

* **ng upgrade:** upgrade to angular `^4.0.0`, replace `<template>` by `<ng-template>` and rebuild dist folder.


<a name="0.1.20"></a>
# 0.1.20 (2017-03-11)

* **wording:** add mention about CSS flexbox layout use, so `angular-split` is not compatible on browser not supporting it (like ios8).

### Feature

* **visibility toggle transition:** add transition (optionnal: `<split [visibleTransition]="true">`) when toggling visibility and `visibleTransitionEnd` event ` [pr11](https://github.com/bertrandg/angular-split/pull/11).


<a name="0.1.19"></a>
# 0.1.19 (2017-02-09)

### Bug fix

* **gutter height on Safari:** fix a weird bug about anormal gutter height when direction is 'vertical' on Safari only [issue5](https://github.com/bertrandg/angular-split/issues/5). Note that `angular-split` isn't working on browser without flexbox support, so not working on ios older than 9.


<a name="0.1.18"></a>
# 0.1.18 (2017-02-04)

### Bug fix

* **visibility toggle:** fix a bug I introduced in 0.1.17 while merging [pr10](https://github.com/bertrandg/angular-split/pull/10).


<a name="0.1.17"></a>
# 0.1.17 (2017-02-03)

### Feature

* **visibility toggle:** add possibility to show/hide areas using `<split-area [visible]="boolean">` without removing them from the DOM, useful for specific case [like with router](https://github.com/jitsmaster/angular-split/commit/c7c92b9a1d1c00623660aeb7bc048509255e763b). Thanks to [jitsmaster](https://github.com/jitsmaster) ([pr8](https://github.com/bertrandg/angular-split/pull/8) / [pr10](https://github.com/bertrandg/angular-split/pull/10))