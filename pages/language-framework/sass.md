<img src="https://sass-lang.com/assets/img/styleguide/color-1c4aab2b.png" style="width: 200px; margin: auto;">



# SaSS Standards

> V1.0.0 ~ Alex Wiley



Syntactically Awesome Stying Sheet (SaSS) was created in 2006 as a new and alternative approach to standard CSS.  Natively SaSS is not compatible with the browser at run time however with the use of pre-compilers can compile down to CSS, it is supported by all versions of CSS. SaSS makes the approach to writing CSS quicker, more flexible and most importantly scalable.



## Usage

At Destructive Digital, SaSS is used in the majority of web projects due to the development time it can save to the company. SaSS should be Utilized wherever possible to make development quicker. A standard SaSS setup will be outlined in the [deployment pipline guide](/pages/pipelines/main). SaSS has a variety of different features and applications that can be best learnt about using the official [SaSS documentation](https://sass-lang.com/guide).



## Accepted Guides

The following guides have been accepted by Destructive Digital as valid and compatible guides for using SaSS in projects.

| Source                 | Company | Link                               |
| ---------------------- | ------- | ---------------------------------- |
| Sass Guide             | Sass    | https://sass-lang.com/guide        |
| Css Guide Lines        | N/A     | https://cssguidelin.es             |
| airbnb Sass Guidelines | AirBnb  | https://github.com/airbnb/css#sass |
|                        |         |                                    |



## Important Rules

We've picked out some of the most important take aways from the above accepted guides. These are rules that are essential for a base understanding of our practices at Destructive Digital.

The following are standard rules that should always be followed, as referenced in [Css Tricks](https://css-tricks.com/sass-style-guide/):

* Be consistent with indentation (see below)
* Be consistent with spacing



### Syntax and Formatting

At a high level, SaSS should follow the following rules:

* Tab indented (2 spaces)
* Multi-line SaSS
* Meaningful use of whitespace

See [Airbnb's Sass style guide](https://github.com/airbnb/css#sass) as a good reference for how code should be styled.



### Multiple Files

SaSS should utilize the ```@import``` functionality provided by the sass framework to split styling into multiple, meaningful files. For example,  for example; components, pages, modules etc should each have their own ```.scss``` file which is imported into a main file.

#### Example

**An example file structure**:

```
+-- components
|   +-- component-a
|	|   +-- component-a.html
|	|   +-- _component-a.scss
+-- main.scss
```

**Inside ```main.scss```**

```scss
//...

//Import Component Styling
@import "./components/component-a/component-a"

//...
```



### @include and @extend

There are various different standard that dictate different standard for where to use and include ```@include``` and ```@extend``` inside styling blocks. We will be following [css-tricks standard](https://css-tricks.com/sass-style-guide/) of having ```@extend``` followed by ```@include``` followed by any additional styling at the top of a styling block, like so:

```scss
.weather {
  @extend %module;
  @include transition(all 0.3s ease-out);
  background: LightCyan;
  &:hover {
    background: DarkCyan;
  }
  &::before {
    content: "";
    display: block;
  }
  ...
}
```



## Naming Conventions

There are a large variety of naming conventions on the market, all of which come with their advantages and disadvantages. To name two of the most popular conventions:

* BEM ~ [Block Element Modifier](http://getbem.com/naming/)
* [Modular CSS](http://thesassway.com/modular-css)

Reviewing the most poplar conventions, BEM stands out as the industry standard and most widely adopted and supported convention on the market. Using a BEM convention also ties in with the rule that SaSS indention should always try and stick below 4 indents.

The following are good and comprehensive sources for learning about the BEM naming convention and how it is used:

* [Block Element Modifier](http://getbem.com/naming/)
* [CSS-Tricks](https://css-tricks.com/bem-101/)
* [Free Code Camp](https://medium.freecodecamp.org/css-naming-conventions-that-will-save-you-hours-of-debugging-35cea737d849) - great example
* [Toptal](https://www.toptal.com/css/introduction-to-bem-methodology)





