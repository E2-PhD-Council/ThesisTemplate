# Thesis template
Thesis template(s) for Chalmers E2 PhD students

Contact: [phd-council.e2@chalmers.se](mailto:phd-council.e2@chalmers.se)

## Disclaimer

The intention of the template is to provide an open-source basis for Chalmers PhD students to collaborate on the mundande task of structuring a thesis.
We strive for compliance with Chalmers official guide lines, but this is not an official Chalmers document and we give no guarantees of compliance.

The guidelines are available here:

- [Licentiate guidelines](https://intranet.chalmers.se/en/tools-support/doctoral-studies-support/licentiate/layout-and-printing-of-licentiate-thesis/)
- [PhD thesis guidelines](https://intranet.chalmers.se/en/tools-support/doctoral-studies-support/doctoral-thesis-defence/thesis-layout/)

They are currently under revision but will be posted in full here.
Our ambition is to stay up to speed with them but if you see any discrepancies please let us know, see [below](#Contribute).


## Current status

The template has been released to the public but it is in a beta-phase and needs to be tested thoroughly.
Found a problem or bug? See [below](#Contribute)

## Usage

### Get the template

1. Using git

You can either _fork_ this repository to your own github account, see [this guide](https://help.github.com/en/github/getting-started-with-github/fork-a-repo),
or you can _clone_ it to a local computer. The command

```bash
git clone git@github.com:E2-PhD-Council/ThesisTemplate.git ThesisTemplate
```
will create a local copy of the template repository in `<current-directory>/ThesisTemplate`.

2. Just getting the files

In the [releases](https://github.com/E2-PhD-Council/ThesisTemplate/releases) tab, you can access all released versions of the template.

3. Overleaf template

The template is available with the name "Chalmers University of Technology E2 Thesis Template".

Whenever there is a release in the github repo, we will update the overleaf template.

### Template structure

The only files that should be changed are contained within the folder `YourThesis`.

When creating a new thesis, start with `YourThesis/Config.tex` to set up all the general information.

The main file of the thesis is `Thesis.tex`, which initiates the template files.
No changes should be made to this file, it is just for easy access.

### Mock-up cover

The print service will scrape info like name, title et c. and produce a new cover.
The template will still generate a mock-up of the cover for you to get a notion of the layout,
but note that this is will not be used in the print.

### Title page

This actual page will be used by the print service. We are trying to have them generate this title page as well
but until then you need to make sure to replace the watermarked logo yourself.
Logotypes are found [here](https://www.chalmers.se/en/about-chalmers/profile-and-identity/Pages/logotype.aspx)

### Referencing

To avoid name clashes for labels in the appended papers the `\includepaper` command automatically prepends a
prefix with the paper name to all labels in the appended paper. For instance, if the appended paper `DummyPaper`
is appended with the command `\includepaper{DummyPaper}`, then all labels in that paper gets the prefix
`DummyPaper:`. So `\label{sec:introduction}` in DummyPaper will get the label `DummyPaper:sec:introduction`.
Within the appended paper, this prefix should not be used because `\ref` has been redefined to take this prefix
into account. This works for references to sections, figures, tables, equations and with hyperref. If you use a
package that does not seem to play nicely with the prefix, add a bug report.

To refer to a label within an appended paper, as said, just use the name of the label. If you want to refer to the label
from the Kappa, then just prepend the paper name to all references. For instance, the section `\label{sec:introduction}`
in the paper `DummyPaper` can be referred to from the Kappa by `\ref{DummyPaper:sec:introduction}`.

To refer to a paper with its letter from the Kappa, simply type `\ref{sec:DummyPaper}` if the paper is added with
`\includepaper{DummyPaper}`. If `DummyPaper` is the first paper to be added, then writing `Paper~\ref{sec:DummyPaper}`
in the Kappa produces `Paper A`.


## Versioning

We will strive to follow a [semver](https://semver.org/)
policy by changing major versions whenever breaking changes occur.

However, as long as we are in a 0.x.y version this is not guaranteed.


## Contribute
If you find any bugs or inconsistencies, please open an issue [here](https://github.com/E2-PhD-Council/ThesisTemplate/issues).
That way we can continue to improve the template and help future colleagues.

If you also have a solution, please open a pull request and we'll review it as soon as possible.
Before you do though, please read the [`CONTRIBUTOR_GUIDELINES.md`](https://github.com/E2-PhD-Council/ThesisTemplate/blob/master/CONTRIBUTOR_GUIDELINES.md).

Want to contribute on a more regular basis? E-mail a maintainer and they'll give you developer priviliges.
