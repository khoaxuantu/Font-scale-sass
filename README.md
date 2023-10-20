# Font scale sass

You want to customize your [Sass](https://sass-lang.com/) typographic scale but get tired of finding out how to have a
great design scale? Then this module's gonna help you a lot ~

It provides a preset font size for your footnote, endnote, caption, body, blockquote, and headings (from h6 to h1).

## Acknowledgement

The module refers to the following great articles and projects. For a better understanding of how the typography works
(typically what's behind this module), you can try spending time reading them as a small research:
- [layoutgridcalculator.com](https://www.layoutgridcalculator.com/type-scale/) by Ti'kuto Design Studio, for the
typographic scale calculating system.
- [Typographic Scale](http://spencermortensen.com/articles/typographic-scale/) by Simonsen Spencer, for the
typographic scale formula.

> The result given by the module has a deviation with the layoutgridcalculator ones in around **0.01 - 0.02 (em)**

## Quick start

### Install
<!-- You can install the module by one of the following way:
- NPM
```bash
npm install fontscale-sass --save-dev
``` -->
*Update later...*

### Deal with the folder

After installing successfully, go to the directory where the module located:
- For npm, you can find the folder named `fontscale-sass` in `node_modules` folder.

Go to this folder and pick up the `font-scale` folder which have the below file structure:
```
font-scale
  |
  |-- utils
  |     |-- _common.scss
  |     |-- _constant.scss
  |     |-- _index.scss
  |
  |-- _index.scss
```
You can choose how to deal with the folders by one of the following ways:
- Place the folder at your project's root stylesheet directory
- Use `--load-path` for dart sass compiling command
```bash
sass --load-path=path/to/font-scale style.scss style.css
```

### Import the module

```scss
@use 'font-scale';

or

@use 'font-scale' as *;
```

## Usage

The `font-scale` module provides only one API to you:

```scss
@mixin createTypoScale($unit: 'em', $ratio: 'classical', $steps: 'pentatonic', $composition: 'fibonacci')
```

#### Parameters
- `$unit`: Represent the css font-size unit that will be rendered. ***Default:*** *'em'*

  | Unit    | Value |
  |---------|-------|
  | 'pica'  | 1em   |
  | 'em'    | 1em   |
  | 'rem'   | 1rem  |
  | 'px'    | 16px  |
  | 'pixel' | 16px  |

- `$ratio`: The ratio in a typographic scale. ***Default:*** *'classical'*

  | Ratio       | Value |
  |-------------|-------|
  | 'classical' | 2     |
  | 'golden'    | 1.618 |

- `$steps`: The number of steps for each interval. An interval in the classical typography is defined as
  6->12, 12->24, etc... ***Default:*** *'pentatonic'*

  | Step          | Value |
  |---------------|-------|
  | 'monotonic'   | 1     |
  | 'ditonic'     | 2     |
  | 'tritonic'    | 3     |
  | 'tetratonic'  | 4     |
  | 'pentatonic'  | 5     |
  | 'hexatonic'   | 6     |
  | 'heptatonic'  | 7     |
  | 'octatonic'   | 8     |
  | 'chromatic'   | 12    |

- `$composition`: Type of the composition number series. ***Default:*** *'fibonacci'*

  | Composition         |
  |---------------------|
  | 'fibonacci'         |
  | 'lucas'             |
  | 'pentagonal'        |
  | 'triangular number' |

#### Return

By default, the following css elements will be rendered

```css
.footnote {
  font-size: 0.66em;
}

.endnote {
  font-size: 0.758em;
}

.caption {
  font-size: 0.758em;
}

body {
  font-size: 1em;
}

blockquote {
  font-size: 1em;
}

h6 {
  font-size: 1em;
}

h5 {
  font-size: 1.149em;
}

h4 {
  font-size: 1.32em;
}

h3 {
  font-size: 1.741em;
}

h2 {
  font-size: 2.639em;
}

h1 {
  font-size: 5.278em;
}
```
