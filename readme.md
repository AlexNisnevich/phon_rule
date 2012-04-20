
**phon_rule** is a user-friendly LaTeX environment for typsetting phonological rules.

### Table of Contents

1\.  [Introduction](#introduction)  
2\.  [Using the `phon_rule` Environment](#usingthe`phon_rule`environment)  
3\.  [Examples](#examples)  

<a name="introduction"></a>

### 1\. Introduction

I couldn't find a good LaTeX environment for phonological rules, so I wrote my own. The
phon_rule environment aims to be as simple to use as possible, while still being flexible
in the types of rules it can draw.

To use this environment, simple copy the preamble of `phon_rule.tex` into your own LaTeX 
file. If this proves to be popular enough, I'll try to make it into a package, but I have 
no experience with LaTeX's packaging system.

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

![{\Large \textrm{A}} {\ {\Large \to}\ } {\Large \textrm{B}} {\Huge \ /\ } {\Large \textrm{C}} {\ \rule{2em}{0.5pt}\ } {\Large \textrm{D}}](http://quicklatex.com/cache3/ql_c8dde09feb023e85d6abad6504b53d9b_l3.png)


Each element of the rule can be composed of the following:

- `\cv{V}`: a CV-tier or tonal-tier element

	- ![{\Large \textrm{V}}](http://quicklatex.com/cache3/ql_0dfc1ddf048901945d295e06e88a26ef_l3.png)


- `\phoneme{S}`: an IPA phoneme, using the `tipa` library

	- ![/\int/](http://quicklatex.com/cache3/ql_2ecc5c868bc6307b81f4a7d69a5f933d_l3.png)


- `\phone{S}`: as above, but displayed with phonetic brackets

	- ![[\int]](http://quicklatex.com/cache3/ql_14ee1ffd62a4cdfb4203323a89790e8c_l3.png)


- `\features{\f{+}{stop} \f{+}{alv.}}`, a feature matrix, where each `\f{+/-}{name}` is a feature

	- ![](http://quicklatex.com/cache3/ql_99daf3ac81513b700e089296a4bcbe14_l3.png)

- `\cvfeatures{C}{\f{\alpha}{place}}`: as above, but with a CV-tier element above the feature matrix

	- ![](http://quicklatex.com/cache3/ql_a92d92e8bad5303ca0d5719ae9896a91_l3.png)

- `\oneof{\# \\ \cv{C}}`, a set of possible environments

	- ![\begin{cases} {\Large \textrm{\#}} \\ {\Large \textrm{C}} \end{cases}](http://quicklatex.com/cache3/ql_27ca034adc56156429392c64e8d5f112_l3.png)


- `\#`: a word-boundary marker

	- ![{\Large \textrm{\#}}](http://quicklatex.com/cache3/ql_116e63d849b0cb126a9a65cd051ed4d9_l3.png)


- `\null`: a null symbol

	- ![{\Large \emptyset}](http://quicklatex.com/cache3/ql_d1f8e8fee9c57339e81b7add9c81380f_l3.png)


<a name="examples"></a>

### 3\. Examples

Examples of phonological rules are found in the body of `phon_rule.tex`, and their output can be seen in `phon_rule.pdf`.