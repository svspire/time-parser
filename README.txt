This is time-parser, a Common Lisp utility for parsing
times in various formats, as well as printing them out.

This code was originally called "CYBERTIGGYR-TIME" and
was written by Gene Michael Stover, but I have improved
it in several ways:

* It's now less buggy and parses formats properly that it
failed on before, like %Y%m%d.

* It parses many more formats than originally, including
RFC-1123, UUCP messages, CIA world factbook indep_date,
and times in PDF info records.

* It's much, much faster than it was before because it tries
to eliminate redundant computation and cache recognizers.