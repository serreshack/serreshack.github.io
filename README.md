# Serres Hackathon 4.0 - Topic

## Επίθεση σε webserver Apache2 - Ανάλυση αρχείων καταγραφής (log files)

### Περιγραφή
Μία ΜΚΟ με έδρα την Ελλάδα διατηρεί ένα PHP website με βάση δεδομένων MySQL που
περιλαμβάνει εκτός των άλλων σύνδεση χρηστών, online πληρωμές (eshop) και ένα
REST API για την διασύνδεση με άλλες υπηρεσίες και εφαρμογές.

Λόγω αμέλειας ο server δέχεται ανεξέλεγκτα επιθέσεις από διάφορα μέρη του πλανήτη. Όλα τα apache access (και error) log requests διατηρούνται στο σύστημα σε αρχεία κατά σειρά με βάση το “Common Log Format, CLF” (βλ. παρακάτω) και με μέγιστο αριθμό 9.000 γραμμών.

Οι επιθέσεις προκαλούν διάφορα ανεπιθύμητα συμβάντα όπως την διακοπή των υπηρεσιών, την καθυστέρηση της απόκρισης των υπηρεσιών καθώς και την προσπάθεια υποκλοπής δεδομένων και κωδικών σύνδεσης.

## Ζητούμενα
Με βάση τα παραπάνω δεδομένα απαντήστε στις παρακάτω ερωτήσεις ή ολοκληρώστε τις παρακάτω εργασίες:

1. Από ποια χώρα έρχονται οι περισσότερες επιθέσεις; (2pt)
2. Ποιες 5 σελίδες δέχονται τις περισσότερες επιθέσεις; (2pt)
3. Πόσο ήταν συνολικά το traffic που δέχτηκε ο server; (2pt)
4. Ποια ώρα της ημέρας έγιναν οι περισσότερες επιθέσεις; (3pt)
5. Ποιο είδος server attack είναι τα πιο συνηθισμένο; (3pt)
6. Ποιο ποσοστό των requests θεωρείτε ότι αποτελούν server attacks; (3pt)
7. Ποια IP κατά την γνώμη σας είναι η πιο επικίνδυνη για τον server; (5pt)
8. Οπτικοποιήστε όλα τα server requests σε γεωγραφικό χάρτη (επιθέσεις ανά χώρα) (5pt)
9. Οπτικοποιήστε όλα τα server requests σε γραφήματα σε σχέση με τον χρόνο. (Time VS Parameter) (5pt)

| Download here: [Server logs for whole day of May 19 2019](https://github.com/serrestech/hackathon/raw/topic/daily-logs.zip)

## Παράρτημα
- Apache2, Common Log Format: https://httpd.apache.org/docs/2.4/logs.html
- Λέξεις κλειδιά: logging, monitoring, log filtering, log visualization, GeoIP, server http attacks, data aggregation, mapping, regex patterns, GNU zip (gzip), log rotate
- Most common HTTP request codes: https://en.wikipedia.org/wiki/List_of_HTTP_status_codes
- List of UserAgentStrings: http://www.useragentstring.com/pages/useragentstring.php
- Server attack types & patterns (DDOS, Bruteforcing, XSS, SQL Injection, XSRF, Remote File Inclusion)
- Server hack types (Url misinterpretation, directory browsing, get “non-web” files, reverse proxying, java decompilation, source code disclosure, input validation, SQL query poisoning, Session Hijacking, Buffer overflows)
