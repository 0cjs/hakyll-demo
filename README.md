hakyll-demo
===========

This is a demo of the [Hakyll] static site build system. It was set up
according to the [tutorials].

### Preparation

Installing [Stack] and [installing Hakyll] will take some time, so
you'll probably want to kick this off first:

    curl -sSL https://get.haskellstack.org/ | sh
    stack upgrade   # Perhaps not necessary
    stack install hakyll

### Sample Website Creation

Once that's all installed, the next steps in creating this repo were

    hakyll-init .   # Create a sample web site
    stack init      # Create stack.yaml based on hakyll-demo.cabal

It's not clear at this time why `hakyll-init` would be creating a
`.cabal` file and we'd be creating the `stack.yaml` from that; the
usual procedure for Stack users would be to use `stack new DIR
TEMPLATE`. (`stack templates` no longer lists the templates; perhaps
[commercialhaskell/stack-templates] seems to be the current list.)

`stack new DIR hakyll-template` (used to produce the `stack` branch in
this repo) produces a similar sample site to `hakyll-init DIR`, but:
- It's probably a slightly older version. (E.g., the image on the
  front page is missing.)
- A `stack.yaml` is included. This differs only in the `resolver`,
  which is `lts-12.26` instead of `lts-9.21`. In both cases, Stack had
  to search down from the latest LTS resolver, `lts-13.9`, to find a
  compatible set of packages.
- No `hakyll-demo.cabal` is included; this is generated during the
  course of `stack build`. Despite the textual diffs in the files, the
  core specifications are essentialy the same. The biggest difference
  is that the executable created from `site.hs` is `site` in the
  `hakyll-init` version (as used in the tutorials) but `hakyll-demo`
  in the `stack new` version.



<!-------------------------------------------------------------------->
[Hakyll]: https://jaspervdj.be/hakyll/
[Stack]: http://localhost:6419/lang/haskell/stack.md
[commercialhaskell/stack-templates]: https://github.com/commercialhaskell/stack-templates
[installing Hakyll]: https://jaspervdj.be/hakyll/tutorials/01-installation.html
[tutorials]: https://jaspervdj.be/hakyll/tutorials.html
