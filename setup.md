---
title: Setup
---


# Installation of [BRIL Work Suite](https://cmslumi.web.cern.ch/#prerequisite) (brilws)

> ## Important
> **This setup is meant to be run from lxplus.cern.ch.**
{: .callout}

## Install `brilws`
Specifying `pip`'s `--user` flag will install `brilws` binaries to `"${HOME}/.local/bin/"` and libraries to `"${HOME}/.local/lib/"`
> ## Important!
> It's always a good idea to include the `--upgrade` flag.\
> **If your `brilcalc` installation stops working, running the command below will fix it in 99% of cases.**
{: .checklist}

```bash
/cvmfs/cms-bril.cern.ch/brilconda310/bin/python3 -m pip install --user --upgrade brilws
```
{: .source}
```
Collecting brilws
  Using cached brilws-3.8.2-py3-none-any.whl
Installing collected packages: brilws
Successfully installed brilws-3.8.2
```
{: .output}

### Verify `brilws` pip info
```bash
/cvmfs/cms-bril.cern.ch/brilconda310/bin/python3 -m pip show brilws
```
{: .source}
```
Name: brilws
Version: 3.8.2
Summary: bril worksuite
Home-page: https://github.com/xiezhen/brilws
Author: Zhen Xie
Author-email:
License: MIT
Location: $HOME/.local/lib/python3.10/site-packages
Requires:
Required-by:
```
{: .output}

### Check `brilcalc` installation location
```bash
command -v brilcalc
```
{: .source}
```
$HOME/.local/bin/brilcalc
```
{: .output}

### Check `brilcalc` version
```bash
brilcalc --version
```
{: .source}
```
3.8.2
```
{: .output}

> ## Troubleshooting `brilws` and `brilcalc`
> In case of trouble, `brilws` can be uninstalled and reinstalled:
> ```bash
> /cvmfs/cms-bril.cern.ch/brilconda310/bin/python3 -m pip uninstall -y brilws
> /cvmfs/cms-bril.cern.ch/brilconda310/bin/python3 -m pip install --user --upgrade brilws
> brilcalc --version
> ```
> {: .source}
> If this doesn't work, the `"${HOME}/.local/"` area may need to be cleaned up by hand:
> ```bash
> rm -iv "${HOME}/.local/bin/bril"*
> rm -rv "${HOME}/.local/lib/python3"*"/site-packages/brilws"*
> /cvmfs/cms-bril.cern.ch/brilconda310/bin/python3 -m pip install --user --upgrade brilws
> brilcalc --version
> ```
> {: .source}
{: .solution}

> ## Set Up `brilcalc` from Container Image in `lxplus`
> On `lxplus`, a container image is provided to give a simple access to the `brilcalc` software for all users.
> It should work without issues (in some cases, it will print warnings regarding the use of outdated python functions which can be ignored).
> In case of problems or inconsistent results, `brilcalc` should be set up as described above.
> Feedback about the container image is welcome, and can be sent to the LUM POG conveners (<cms-pog-conveners-lum@cern.ch>).
> ```bash
> source /cvmfs/cms-bril.cern.ch/cms-lumi-pog/brilws-docker/brilws-env
> ```
> {: .source}
> The first time the command is run on a node, it can take a bit longer because the files have to be downloaded first in cvmfs.
{: .solution}

{% include links.md %}
