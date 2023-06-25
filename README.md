# [SSCCE](sscce.org) of Quarto issue with hot reloading

When editing a page that is part of listing, `quarto preview` will hot reload.

In Quarto `1.3.361`, the edited page was correctly displayed after the hot reload.

In Quarto `1.3.427`, the listing page is displayed instead.


## Reproduction

* `quarto create-project --type website`
* `mkdir listing`
* Create `listing/index.md` with barebones `listing` front-matter.
* Edit `_quarto.yml` to add a link to `listing/index.md`.
* Create `listing/foo.md` with barebones content.

Try the following steps with different versions of Quarto

* `quarto preview`
* Edit `listing/foo.md`, and write.
* The browser will refresh automatically. Is the test post displayed, or is the listing
  page displayed?
    * In Quarto `1.3.427`, the latter is the case, which is unintuitive to me. In
      previous versions, the former is the case. I expect the page I edited to be
      displayed!
