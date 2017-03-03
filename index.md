Bioconductor and R compatibility
================================

There is a table of Bioconductor and R compatibility [here](http://www.bioconductor.org/about/release-announcements/#release-announcements)
but it is flawed in an easily fixable way. It doesn't list the versions beyond the first two numbers.
And so I installed R version 3.3.2, thinking it would work with the latest Bioconductor release v 3.4 but it doesn't as evidenced by `DESeq2`, which is "a Bioconductor package"(Source:[here](http://seqanswers.com/forums/showthread.php?t=42183)) not being able to be installed. When I look on the other pages , I see

> "Bioconductor is version 3.4; it works with R version 3.3.1."

(Source: [Bioconductor: Home: Install: Using Bioconductor](http://www.bioconductor.org/install/))






Additional Dependencies **OFTEN REQUIRED**
------------------------------------------

**BE AWARE**  
In the process of Dockerizing, I noted many needed dependencies that I only learned about by forensics on install messages and combing the web that were needed for installation of R itself and then for proper installation of Bioconductory packages, such as `DESeq`. This goes just beyond trying to get this working in Docker containers. Indeed, many others have stumbled on these uncommon (perhaps?), in-development depenencies as evidenced by [here](https://support.bioconductor.org/p/47170/), [here](https://support.bioconductor.org/p/54381/), [here](https://support.bioconductor.org/p/90750/), [here](https://stat.ethz.ch/pipermail/r-devel/2015-November/072073.html), and [here](https://groups.google.com/forum/#!topic/poedit/3NwGlp-QbfA), and [here](https://ubuntuforums.org/archive/index.php/t-23570.html) whose need is not clearly documented IMO in the [‘R Installation and Administration’ manual](https://cran.r-project.org/doc/manuals/r-release/R-admin.html) or the Installation instructions at [Bioconductor: Home: Install](http://www.bioconductor.org/install/). For example, cyrptic notes [here](https://www.r-statistics.com/2016/05/r-3-3-0-is-released/) about `PCRE` suggest consulting the [‘R Installation and Administration’ manual](https://cran.r-project.org/doc/manuals/r-release/R-admin.html) and talks about building `PCRE`, but no where at [Bioconductor: Home: Install](http://www.bioconductor.org/install/) is it mentioned or suggested to use a package manager to install `libpcre3-dev`.

As of early 2017, these were some of such dependencies I noted concerned `ICU`, `X`, `PCRE`, and `XML2`, and required the following:

* libicu-dev
* xorg-dev
* libpcre3-dev
* libxml2-dev

In fact I would say highly recommend just installing these before you begin the process of trying to install R to save youself many headaches.
See the 'Install R/Install R Packages 'section of this [Dockerfile](https://github.com/fomightez/rnaseq_wang/blob/master/Dockerfile) if you need additional guidance in how to install these. Leave off the leading, Docker-specfic `RUN ` when you run these commands on the command line.



Resources concerning Bioconductor and R compatibility
------------------------------------------------------

Answer [here](http://seqanswers.com/forums/showthread.php?t=42183) leads to [Release Schedule](http://www.bioconductor.org/developers/release-schedule/ )

The most recent one is 3.4, but the big issue I note is at the top it says
> "Bioconductor 3.4 Release Schedule
This release will use R-3.3.1 (Bug in Your Hair) unless 3.3.2 comes out in time (would need to be at least 1 week before release day though)."

Plus going to [here](http://www.bioconductor.org/install/) from that page above, I see
> "The current release of Bioconductor is version 3.4; it works with R version 3.3.1. Users of older R and Bioconductor users must update their installation to take advantage of new features and to access packages that have been added to Bioconductor since the last release."

I see on the side the have a link to [Release announcements](http://www.bioconductor.org/about/release-announcements/#release-announcements) and there is a table there if compatibility with preface
> "Each Bioconductor release is designed to work with a specific version of R. The following table summarizes the relationship, and links to packages designed to work with the corresponding R / Bioconductor version."

But that table is flawed in my view. See above.



Related
-------

[Bioinformatics Software Compatibility](http://bioinformatics-software-compatibility.readthedocs.io/en/latest/)
