# LaTeXML-Plugin-Cortex
A CorTeX worker for LaTeXML

By default connects to the KWARC dispatcher, generating e.g. the [arXMLiv corpus](http://cortex.mathweb.org/corpus/arXMLiv/tex_to_html)

# Installation under Debian

Strategy: fetch the dependencies via the package managers, then install the bleeding versions from git.

```bash
sudo apt-get install cpanminus libzmq3-dev &&
sudo apt-get build-dep latexml &&
cpanm git@github.com:brucemiller/LaTeXML.git &&
cpanm git@github.com:dginev/LaTeXML-Plugin-Cortex.git
```

# Runtime Reliability

It is recommended to setup all client machines that are accessing the main server via the open internet to have at least two separate DNS servers setup, as well as to have **only an IPv4 interface** enabled, with IPv6 explicitly enabled. It is a current limitation of the central CorTeX server that no robust IPv6 interface is exposed.

# Contribute to the arXMLiv build system

All you need to do to contribute is do the installation and then run:
```bash
latexml_harness
```

That's it! Feel free to start it as a background job on worker machines, e.g. via:
```bash
nohup latexml_harness 2>&1 > cortex.log &
```

Thanks for contributing!
