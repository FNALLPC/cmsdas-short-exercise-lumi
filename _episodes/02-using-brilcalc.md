---
title: "Using brilcalc"
teaching: 20
exercises: 10
questions:
- "What tools are available to query the delivered and recorded luminosity?"
objectives:
- "Learn how to use `brilcalc` to query luminosity information."
keypoints:
- "`brilcalc` is a command-line tool provided by the CMS BRIL group for querying luminosity information."
---

> ## Important
> **This exercise is meant to be run from lxplus.cern.ch.**
>
> Please follow the [setup instructions](/cmsdas-short-exercise-lumi/setup.html) before getting started.
{: .prereq}

# brilcalc

`brilcalc` is the official tool for querying CMS luminosity information.
It currently has three subcommands: `lumi`, `beam`, and `trg`.
The official brilcalc documentation can be found here: [https://cmslumi.web.cern.ch/](https://cmslumi.web.cern.ch/).

## brilcalc lumi

This lesson will focus on the `brilcalc lumi` subcommand, which can query the delivered and recorded CMS luminosity.
Let's try a few examples:

> ## Glossary
> If you are unfamiliar with "fills", "runs", "lumisections", etc., you can find their definitions in the [Glossary](/cmsdas-short-exercise-lumi/reference.html#glossary)
{: .callout}

> ## Run brilcalc for [fill 10666](https://cmsoms.cern.ch/cms/fills/report?cms_fill=10666)
> ```bash
> brilcalc lumi -f 10666
> ```
> {: .source}
> > ## Output
> > ```
> > #Data tag : 24v2 , Norm tag: onlineresult
> > +--------------+-------------------+------+------+---------------------+---------------------+
> > | run:fill     | time              | nls  | ncms | delivered(/ub)      | recorded(/ub)       |
> > +--------------+-------------------+------+------+---------------------+---------------------+
> > | 392538:10666 | 05/25/25 12:13:34 | 595  | 586  | 264365847.218701780 | 247877075.633063853 |
> > | 392540:10666 | 05/25/25 16:04:20 | 28   | 18   | 13756312.142429797  | 5966128.696881626   |
> > | 392541:10666 | 05/25/25 16:14:54 | 14   | 7    | 6795693.079543251   | 1514552.601936024   |
> > | 392542:10666 | 05/25/25 16:20:06 | 1902 | 1902 | 711711390.989558220 | 683596996.380376101 |
> > +--------------+-------------------+------+------+---------------------+---------------------+
> > #Summary:
> > +-------+------+------+------+---------------------+---------------------+
> > | nfill | nrun | nls  | ncms | totdelivered(/ub)   | totrecorded(/ub)    |
> > +-------+------+------+------+---------------------+---------------------+
> > | 1     | 4    | 2539 | 2513 | 996629243.430233002 | 938954753.312257528 |
> > +-------+------+------+------+---------------------+---------------------+
> > ```
> > {: .output}
> {: .solution}
{: .challenge}

> ## Run brilcalc for [run 370000](https://cmsoms.cern.ch/cms/runs/report?cms_run=370000)
> ```bash
> brilcalc lumi -r 370000
> ```
> {: .source}
> > ## Output
> > ```
> > #Data tag : 24v1 , Norm tag: onlineresult
> > +-------------+-------------------+-----+------+--------------------+--------------------+
> > | run:fill    | time              | nls | ncms | delivered(/ub)     | recorded(/ub)      |
> > +-------------+-------------------+-----+------+--------------------+--------------------+
> > | 370000:9023 | 07/03/23 02:01:15 | 224 | 224  | 65453850.326108657 | 63313828.920737430 |
> > +-------------+-------------------+-----+------+--------------------+--------------------+
> > #Summary:
> > +-------+------+-----+------+--------------------+--------------------+
> > | nfill | nrun | nls | ncms | totdelivered(/ub)  | totrecorded(/ub)   |
> > +-------+------+-----+------+--------------------+--------------------+
> > | 1     | 1    | 224 | 224  | 65453850.326108657 | 63313828.920737430 |
> > +-------+------+-----+------+--------------------+--------------------+  
> > ```
> > {: .output}
> {: .solution}
{: .challenge}

### `brilcalc` options

`brilcalc` provides a generous number of command line options.
You can get a summary by running `brilcalc lumi --help`.
But the [official documentation](https://cmslumi.web.cern.ch/#brilcalc) is much more comprehensive.

> ## Example `brilcalc` common command options
> Selections
> : period to query
> 
> * `-f <fill>`
> * `-r <run>`
> * `--begin <fill>`
> * `--begin <run>`
> * `--begin <MM/DD/YY HH:MM:SS>` (UTC)
> * `--end <fill>`
> * `--end <run>`
> * `--end <MM/DD/YY HH:MM:SS>` (UTC)
> 
> Filters
> : conditions to query
> 
> * `-b <beam status>`
>     * `["STABLE BEAMS", "FLAT TOP", "ADJUST", "SQUEEZE"]`
> * `--amodetag <machine mode>`
>     * `["PROTPHYS", "IONPHYS", "PAPHYS"]`
> * `--beamenergy <beam energy>` (in GeV)
> 
> Output/Display
> : output file, table/csv/html output format, utc/local time, etc.
> 
> * `-o <output file>` (csv format)
> * `--output-style <output format>` (ignored if `-o` is provided)
>     * `["tab", "csv", "html"]`
> * `--tssec` (display times as UNIX timestamps)
{: .callout}

> ## Example `brilcalc lumi` options
> `--byls`
> : Show luminosity and average pileup by lumi section
>
> `-u <unit>`
> : Show luminosity in the specified unit and scale the output value accordingly 
> : `["/kb", "/b", "/mb", "/ub", "/nb", "/pb", "/fb", "/ab"]`
> : `["1e21/cm2", "1e24/cm2", "1e27/cm2", "1e30/cm2", "1e33/cm2", "1e36/cm2", "1e39/cm2", "1e42/cm2"]`
> 
> `--type <luminometer>`
> : Show results from the selected luminometer
> : `["hfoc", "hfet", "bcm1f", "bcm1fsi", "bcm1futca", "pltzero", "pltslink", "dt", "pxl", "ramses", "radmon"]`
{: .callout}


> ## `brilcalc --output-style`
> The stdout (display output) of `brilcalc` can be specified with the `--output-style` flag.
> Note that this in a "common" or "global" option, meaning that it is also available for the `brilcalc beam` and `brilcalc trg` subcommands.
> Let's reproduce the above output in csv format:
> ```bash
> brilcalc lumi -r 370000 --output-style csv
> ```
> {: .source}
> > ## Output
> > ```
> > #Data tag : 24v1 , Norm tag: None
> > #run:fill,time,nls,ncms,delivered(/ub),recorded(/ub)
> > 370000:9023,07/03/23 02:01:15,224,224,65453850.326108657,63313828.920737430
> > #Summary:
> > #nfill,nrun,nls,ncms,totdelivered(/ub),totrecorded(/ub)
> > #1,1,224,224,65453850.326108657,63313828.920737430  
> > ```
> > {: .output}
> {: .solution}
{: .challenge}


> ## 2.1 Query luminosity info for *fill* corresponding to run 381151
> Using brilcalc, determine the *fill* that run 381151 corresponds to and query the luminosity for that fill.
> What is the total recorded luminosity for this fill in inverse picobarns?
{: .challenge}
<!--
/poll "What is the total recorded luminosity for this fill (in inverse picobarns) for the fill corresponding to run 381151?" "307" "646" "710"
fill=$(brilcalc beam -r 381151 --output-style csv | tail -1 | cut -f 1 -d ,)
brilcalc lumi -f "${fill}" -u /pb --output-style csv | tail -1 | cut -d, -f6
-->
