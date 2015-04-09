
**phon_rule** is a user-friendly LaTeX environment for typsetting phonological rules.

### Table of Contents

1\.  [Introduction](#introduction)  
2\.  [Using the `phon_rule` Environment](#usingthe`phon_rule`environment)
3\.  [The `center` Option](#the`center`option)
4\.  [Examples](#examples)  

<a name="introduction"></a>

### 1\. Introduction

I couldn't find a good LaTeX environment for phonological rules, so I wrote my own. The
phon_rule environment aims to be as simple to use as possible, while still being flexible
in the types of rules it can draw.

To use this environment, place the `phon_rule.sty` file either in your LaTeX packages directory or in the same directory as the
document you're going to use the environment in. 

Most of the LaTeX in this readme was automatically rendered using [markdown-pp](https://github.com/AlexNisnevich/markdown-pp)
by way of [QuickLaTeX](http://www.holoborodko.com/pavel/quicklatex/). Because QuickLaTeX does not yet support the `tipa` package, 
any IPA symbols in this readme are approximations using the closest available LaTeX symbol.

<a name="usingthe`phon_rule`environment"></a>

### 2\. Using the `phon_rule` Environment

The basic format of a phonological rule is:

	\begin{phon_rule}
		A \> B \/ C \_ D
	\end{phon_rule}

which produces

![{\Large \textrm{A}} {\ {\Large \to}\ } {\Large \textrm{B}} {\Huge \ /\ } {\Large \textrm{C}} {\ \rule{2em}{0.5pt}\ } {\Large \textrm{D}}](readme-images/abcd.png)


Each element of the rule can be composed of the following:

- `\cv{V}`: a CV-tier or tonal-tier element

	- ![{\Large \textrm{V}}](readme-images/v.png)


- `\phoneme{S}`: an IPA phoneme, using the `tipa` library

	- ![/\int/](readme-images/sh-phoneme.png)


- `\phone{S}`: as above, but displayed with phonetic brackets

	- ![[\int]](readme-images/sh-phone.png)


- `\features{\f{+}{stop} \f{+}{alv.}}`, a feature matrix, where each `\f{+/-}{name}` is a feature

	- ![](readme-images/features.png)

- `\cvfeatures{C}{\f{\alpha}{place}}`: as above, but with a CV-tier element above the feature matrix

	- ![](readme-images/cfeatures.png)

- `\oneof{\# \\ \cv{C}}`, a set of possible environments

	- ![\begin{cases} {\Large \textrm{\#}} \\ {\Large \textrm{C}} \end{cases}](readme-images/oneof.png)


- `\#`: a word-boundary marker

	- ![{\Large \textrm{\#}}](readme-images/word-boundary.png)


- `\null`: a null symbol

	- ![{\Large \emptyset}](readme-images/null.png)

<a name="the`center`option"></a>

### 3\. The `center` Option

Invoking the `center` option when using the package wraps the rules (the `phon_rule` environment) in a `center` environment, centering them. 

<a name="examples"></a>

### 4\. Examples

Examples of phonological rules are found in the body of `phon_rule.tex`, and their output can be seen in `phon_rule.pdf`.
