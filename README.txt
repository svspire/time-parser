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

EXAMPLES:

(tp:parse-time "2018-02-13T10:16:28 -7") ; -->
3727530988

(tp:format-time t tp:*format-time-iso8601-long* 3727530988) ; -->
2018-02-13T10:16:28 -7

(tp:parse-time "February 13, 2018") ; -->
3727537200

(tp:parse-time "2/13/2018") ; -->
3727537200

(tp:parse-time "13-Feb-2018") ; -->
3727537200

(tp:parse-time "Monday, February 13, 2018") ; -->
3727537200

(tp:parse-time "now") ; -->
3727531944

(tp:parse-time "today") ; -->
3727512000

(tp:format-time t tp:*format-time-iso8601-long* 3727512000) ; -->
2018-02-13T05:00:00 -7

(tp:format-time t tp:*format-time-rfc1123* 3727512000) ; -->
Tue, 13 Feb 2018 05:00:00 GMT