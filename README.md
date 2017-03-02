Bioconductor and R compatibility
================================

There is a table of Bioconductor and R compatibility [here](http://www.bioconductor.org/about/release-announcements/#release-announcements)
but it is flawed in an easily fixable way. It doesn't list the versions beyond the first two numbers.
And so I installed R version 3.3.2, thinking it would work with the latest Bioconductor release v 3.4 but it doesn't as evidenced by `DESeq2`, which is "a Bioconductor package"(Source:[here](http://seqanswers.com/forums/showthread.php?t=42183)) not being able to be installed. When I look on the other pages , I see

> "Bioconductor is version 3.4; it works with R version 3.3.1."

(Source: [Using Bioconductor](http://www.bioconductor.org/install/))





Resources
---------

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
[Bioinformatics Software Compatibility](COMING SOON)
