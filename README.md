# Serres Hackathon 4.0 - Topic

## Επίθεση σε webserver Apache2 - Ανάλυση αρχείων καταγραφής (log files)

### Περιγραφή
Μία ΜΚΟ με έδρα την Ελλάδα διατηρεί ένα PHP website με βάση δεδομένων MySQL που
περιλαμβάνει εκτός των άλλων σύνδεση χρηστών, online πληρωμές (eshop) και ένα
REST API για την διασύνδεση με άλλες υπηρεσίες και εφαρμογές.

Λόγω αμέλειας ο server δέχεται ανεξέλεγκτα επιθέσεις από διάφορα μέρη του πλανήτη.
Όλα τα apache access (και error) log requests διατηρούνται στο σύστημα σε αρχεία κατά σειρά,
συμπιεσμένα σε μορφή gz και με βάση το “Common Log Format, CLF” (βλ. παρακάτω).
Οι επιθέσεις προκαλούν διάφορα ανεπιθύμητα συμβάντα όπως την διακοπή των υπηρεσιών,
την καθυστέρηση της απόκρισης των υπηρεσιών καθώς και την προσπάθεια υποκλοπής δεδομένων και κωδικών σύνδεσης.

## Ζητούμενα
Με βάση τα παραπάνω δεδομένα απαντήστε στις παρακάτω ερωτήσεις ή ολοκληρώστε τις παρακάτω εργασίες:

1. Από ποια χώρα έρχονται οι περισσότερες επιθέσεις;
2. Ποιο ποσοστό των requests θεωρείτε ότι αποτελούν server attacks;
3. Ποιο είδος server attack είναι τα πιο συνηθισμένο;
4. Πόσο ήταν συνολικά το traffic που δέχτηκε ο server;
5. Ποιες 5 σελίδες δέχονται τις περισσότερες επιθέσεις;
6. Ποιες ώρες της μέρας έγιναν οι περισσότερες επιθέσεις;
7. Ποια IP κατά την γνώμη σας είναι η πιο επικίνδυνη για τον server;
8. Οπτικοποιήστε όλα τα server requests σε γεωγραφικό χάρτη (επιθέσεις ανά τοποθεσία IP)
9. Οπτικοποιήστε όλα τα server requests σε γραφήματα σε σχέση με τον χρόνο. (Time VS Parameter)

Current server logs (gz files):

## Παράρτημα
- Apache2, Common Log Format: https://httpd.apache.org/docs/2.4/logs.html
- Λέξεις κλειδιά: logging, monitoring, log filtering, log visualization, GeoIP, server http attacks, data aggregation, mapping, regex patterns, GNU zip (gzip), log rotate
- Most common HTTP request codes: https://en.wikipedia.org/wiki/List_of_HTTP_status_codes
- List of UserAgentStrings: http://www.useragentstring.com/pages/useragentstring.php
- Server attack types & patterns (DDOS, Bruteforcing, XSS, SQL Injection, XSRF, Remote File Inclusion)
- Server hack types (Url misinterpretation, directory browsing, get “non-web” files, reverse proxying, java decompilation, source code disclosure, input validation, SQL query poisoning, Session Hijacking, Buffer overflows)


## Επιπλέον tasks (?)
Με βάση τα παραπάνω η ΜΚΟ σας ζητάει να υλοποιήσετε 1 ειδικό λογισμικό ελέγχου, ανάγνωσης, ομαδοποίησης, ταξινόμησης και οπτικοποίησης των server logs. Οι διαχειριστές του λογισμικού αυτού θα είναι σε θέση να εκτελούν τις εξής εργασίες:

- Να προβάλλουν όσο πιο γρήγορα γίνεται (realtime) ποιες σελίδες ακριβώς δέχονται επίθεση.
- Να μπορούν να αποκρύπτουν από τα logs αυτά που δεν θεωρούνται επιθέσεις.
- Να μπορούν να φιλτράρουν (πχ regex patterns) τα server logs με βάση την γεωγραφική τοποθεσία της επίθεσης, τον χρόνο έναρξης και λήξης, το είδος της επίθεσης, την IP, τα συγκεκριμένα URL που δέχτηκαν την επίθεση, την θύρα εισόδου, το HTTP response status, την μέθοδο της επίθεσης, το OS του browser, τον browser.
- Να μπορούν να αποθηκεύουν aggregated data των επιθέσεων σε βάση δεδομένων.
- Να μπορούν να βλέπουν οπτικοποιημένες τις επιθέσεις σε γεωγραφικό χάρτη.
- Να μπορούν να βλέπουν οπτικοποιημένες τις επιθέσεις σε γραφήματα, διαγράμματα και πίνακες.
- Να θέτουν συγκεκριμένα κριτήρια με βάση τα φίλτρα παραπάνω ώστε όταν πληρούνται να αποστέλλεται άμεσα ένα email στους διαχειριστές με το είδος της επίθεσης και άλλες τεχνικές λεπτομέρειες.
- Να μπορούν να δημιουργήσουν απλές αναφορές για τις επιθέσεις που θα είναι κατανοητές από μη ειδικούς.
