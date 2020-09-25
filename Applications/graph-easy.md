### Setup

Install using cpanm, [[Perl]]
```
[sudo] cpanm install Graph::Easy
```

Install ditaa
- ditaa is a java app and requires java :( brew cask install java
```
brew install ditaa
```

### Usage

**graph-easy docs**
http://bloodgate.com/perl/graph/manual/syntax.html

[GitHub - ironcamel/Graph-Easy: Convert or render graphs (as ASCII, HTML, SVG or via Graphviz)](https://github.com/ironcamel/Graph-Easy)

[graph-easy - render/convert graphs in/from various formats - metacpan.org](https://metacpan.org/pod/release/TELS/Graph-Easy-0.64/bin/graph-easy)

**ditaa docs**
[ditaa](http://ditaa.sourceforge.net/#usage)

```
# simple graph output as png using ditaa
echo "[test] -> [test2]" | graph-easy > asciigraph.txt && ditaa asciigraph.txt asciigraph.png --overwrite --round-corners --no-shadows && rm asciigraph.txt

# as boxart
graph-easy input.txt output.txt --as=boxart

# as png
graph-easy input.txt output.txt --png
```

