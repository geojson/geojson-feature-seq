
## Generating Docs

### Dependencies

 * [`xml2rfc`](https://pypi.python.org/pypi/xml2rfc/), a Python module
 * [`pandoc2rfc`](https://raw.github.com/miekg/pandoc2rfc/master/pandoc2rfc)
 * pandoc

### Transform Markdown to XML etc.

Inside the working copy of the repo perform (current practice):

```bash
bash ./build
```

which does the following:

```bash
bash pandoc2rfc -R -t template.xml -x transform.xsl back.mkd middle.mkd && mv draft.txt draft-unpaginated.txt && for i in H N T X; do bash pandoc2rfc -$i -t template.xml -x transform.xsl back.mkd middle.mkd; done
```
