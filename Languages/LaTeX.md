### Setup
Install MacTex
```
brew cask install mactex
```

MacTex is a package of a handful of LaTeX utilities.
These are
- TeXShop
- Tex Live 2020, the actual TeX distribution, [Guide](https://www.tug.org/texlive/doc/texlive-en/texlive-en.html#x1-90002.1)
	- Includes original TeX itself as `tex` but also several extended TeX engines,
	- e-TeX -- `etex`
	- pdfTeX -- `pdftex`
	- LuaTeX -- `luatex`
	- XeTeX -- `xetex`
	- Aleph -- `aleph`

Since macOS requires applications to be notarized by Apple, a few packages that would normally come with MacTex have not been updated since the requirement change and now have to be downloaded separately,
- TeX Live Utility -- A GUI for the Text Live packager manager, `tlmgr`.
- BibDesk -- A utility for managing bibliographic information.
- cocoAspell -- A utility for spell checking.

### Packages

Install Package
- The preferred way is to download the TeX Live GUI Utility.
```
tlmgr install <package>
```

