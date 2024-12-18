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
> Please follow the [setup instructions](/setup.html) before getting started.
{: .prereq}

# brilcalc

`brilcalc` is the official tool for querying CMS luminosity information.
It currently has three subcommands: `lumi`, `beam`, and `trg`.
The official brilcalc documentation can be found here: [https://cmslumi.web.cern.ch/](https://cmslumi.web.cern.ch/).

## brilcalc lumi

This lesson will focus on the `brilcalc lumi` subcommand, which can query the delivered and recorded CMS luminosity.
Let's try a few examples:

> ## Glossary
> If you are unfamiliar with "fills", "runs", "lumisections", etc., you can find their definitions in the [Glossary](/reference.html#glossary)
{: .callout}

> ## Run brilcalc for [fill 9666](https://cmsoms.cern.ch/cms/fills/report?cms_fill=9666)
> ```bash
> brilcalc lumi -f 9666
> ```
> {: .source}
> > ## Output
> > ```
> > #Data tag : 24v1 , Norm tag: onlineresult
> > +-------------+-------------------+-----+------+---------------------+---------------------+
> > | run:fill    | time              | nls | ncms | delivered(/ub)      | recorded(/ub)       |
> > +-------------+-------------------+-----+------+---------------------+---------------------+
> > | 381143:9666 | 05/24/24 11:04:03 | 12  | 0    | 14.181185411        | 0                   |
> > | 381147:9666 | 05/24/24 11:08:23 | 231 | 223  | 91256126.248753428  | 77027107.891959071  |
> > | 381148:9666 | 05/24/24 12:38:03 | 292 | 283  | 144805628.612147063 | 127957935.748760328 |
> > | 381149:9666 | 05/24/24 14:31:14 | 140 | 133  | 69235351.710984617  | 61366554.087962441  |
> > | 381150:9666 | 05/24/24 15:25:36 | 51  | 41   | 24489229.453756947  | 18476291.350573931  |
> > | 381151:9666 | 05/24/24 15:45:17 | 860 | 852  | 324855104.257013619 | 307000908.806938708 |
> > | 381152:9666 | 05/24/24 21:19:14 | 194 | 194  | 55802570.516791143  | 54069059.298041537  |
> > +-------------+-------------------+-----+------+---------------------+---------------------+
> > #Summary:
> > +-------+------+------+------+---------------------+---------------------+
> > | nfill | nrun | nls  | ncms | totdelivered(/ub)   | totrecorded(/ub)    |
> > +-------+------+------+------+---------------------+---------------------+
> > | 1     | 7    | 1780 | 1726 | 710444024.980632067 | 645897857.184236050 |
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
> * `-b <beam status>` ["STABLE BEAMS", "FLAT TOP", "ADJUST", "SQUEEZE"]
> * `--amodetag <machine mode>` ["PROTPHYS", "IONPHYS", "PAPHYS"]
> * `--beamenergy <beam energy>` (in GeV)
> 
> Output/Display
> : output file, table/csv/html output format, utc/local time, etc.
> 
> * `-o <output file>` (csv format)
> * `--output-style <output format>` ["tab", "csv", "html"] (ignored if `-o` is provided)
> * `-n <scalefactor>` (scale output by 1/scalefactor)
> * `--cerntime` (display times in CERN local time)
> * `--tssec` (display times as UNIX timestamps)
> 
> Database connection
> : connect to a database, such as a web cache
>
> * `-c <connection>` ["offline", "online", "onlinew", "dev"]
{: .callout}

> ## Example `brilcalc lumi` options
> `--byls`
> : Show luminosity and average pileup by lumi section
>
> `-u <unit>`
> : Show luminosity in the specified unit and scale the output value accordingly 
> : ["/kb", "/b", "/mb", "/ub", "/nb", "/pb", "/fb", "/ab"]
> : ["1e21/cm2", "1e24/cm2", "1e27/cm2", "1e30/cm2", "1e33/cm2", "1e36/cm2", "1e39/cm2", "1e42/cm2"]
> 
> `--type <luminometer>`
> : Show results from the selected luminometer
> : ["hfoc", "hfet", "bcm1f", "bcm1fsi", "bcm1futca", "pltzero", "pltslink", "dt", "pxl", "ramses", "radmon"]
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


> ## 2.1 Query luminosity info for fill corresponding to run 370000
> Using brilcalc, determine the fill that run 370000 corresponds to.
> What is the total recorded luminosity for this fill in inverse picobarns?
{: .challenge}
