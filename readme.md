## (Angular) SCSS Foundation
### Purpose of this repository
This repository is meant to speed up the process of setting up new Angular-based project.

However, it is worth mentioning that this **scss foundation** may be used in other kind of projects as well. In order to avoid uneccessary elements please go to the _Usage in other projects_.

### Elements of the repository
1. `index.scss` - this is the main file (alternatively `main.scss`), it imports the main partial `lib/_main.scss`. Should be added in the `angular.json` file.
2. `lib/_main.scss` - this is the main partial, that is used to import all the partials from `lib` directory. This step is optional, but it adds another layer of aesthetics.
3. `lib/_reset.scss` - file containing browsers styles resets to ensure all of them are rendering HTML elements in the same manner.
4. `lib/_variables.scss` - it contains all of the scss variables used across the project. It will be also imported to many `*.component.scss` files, thus it also imports color palettes and mixins (and optionally media query mixins)
5. `lib/_palette.scss` - this is the file where color palettes are defined in. It is a part of _variables file_, but moved to a separate file for greater readability.
6. `lib/_mixins.scss` - source of all the mixins used in the project. It also includes "template mixins" (not to be used directly in project), prefixed with `__0`.
7. `lib/_media-queries.scss` - _not yet available._
8. `lib/_material-reset.scss` - this file includes custom style overrides for Angular Material Design components. Styles added here ought to be only _reset-like_ styles, so only **overriding** of existing styles.
9. `lib/_theming.scss` - this is where the Angular Material Design theme is defined, also component styles are enabled or disabled here.
10. `lib/_global.scss` - file containing global and general styles, that are not _reset-like_ styles.
11. `lib/_typography.scss` - a part of global styles that stores text styles, such as headings or anchors.
12. `lib/_common.scss` - part of global styles as well, this file imports partials from `lib/common` directory, for example `lib/common/_dialog.scss`. This adds more aestethics to the foundation, as all common styles are imported into single place.

### Usage in Angular projects
#### Foundation setup 
In order to use this resource inside an Angular project, it is necessary to add this file in the `angular.json`, in `projects > project-name > architect > build > options > styles`.

If not used in a Lib-based (such as Nrwl-based) project, a `lib` directory name is not required, otherwise it is recommended.

Example usage:
```
"styles": [
  "libs/project-name/shared/styles/src/index.scss"
],
```
It is also recommended to add preprocessor options (in the same place):
```
"stylePreprocessorOptions": {
  "includePaths": ["libs/project-name/shared/styles/src/lib"]
},
```
This will allow import of variables in the `*.component.scss` in such manner: `@import 'variables';`

#### Files setup
To be added...

### Usage in other projects
To be added...
