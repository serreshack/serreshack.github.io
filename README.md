# Serres Hackathon 4.0 - Topic

## Επίθεση σε webserver Apache2 - Ανάλυση αρχείων καταγραφής (log files)

### Περιγραφή
Μία ΜΚΟ με έδρα την Ελλάδα διατηρεί ένα PHP website με βάση δεδομένων MySQL που περιλαμβάνει εκτός των άλλων σύνδεση χρηστών, online πληρωμές (eshop) και ένα REST API για την διασύνδεση με άλλες υπηρεσίες και εφαρμογές.

Λόγω αμέλειας ο server δέχεται ανεξέλεγκτα επιθέσεις από διάφορα μέρη του πλανήτη. Όλα τα apache access (και error) log requests διατηρούνται στο σύστημα σε αρχεία κατά σειρά με βάση το "Common Log Format, CLF" (βλ. παρακάτω) και με μέγιστο αριθμό 9.000 γραμμών.

Οι επιθέσεις προκαλούν διάφορα ανεπιθύμητα συμβάντα όπως την διακοπή των υπηρεσιών, την καθυστέρηση της απόκρισης των υπηρεσιών καθώς και την προσπάθεια υποκλοπής δεδομένων και κωδικών σύνδεσης.

## Ζητούμενα
Με βάση τα παραπάνω δεδομένα απαντήστε στις παρακάτω ερωτήσεις ή ολοκληρώστε τις παρακάτω εργασίες:

### Γενικά (5pt)
1. Πόσο ήταν συνολικά το traffic που δέχτηκε ο server; (1pt)
2. Πόσα requests προκάλεσαν 5xx server error; (1pt)
3. Πόσες είναι οι ξεχωριστές IP που επισκέφτηκαν τον server; (3pt)

### Data Mining (15pt)
4. Ποιο ποσοστό των requests θεωρείτε ότι αποτελούν server attacks; (3pt)
5. Πόσα **SQL Injections**, **XSS**, και **"Object Reference"** attacks αναγνωρίσατε; (5pt)
6. Ποιες 5 σελίδες δέχονται τις περισσότερες επιθέσεις; (2pt)
7. Από ποια χώρα έρχονται οι περισσότερες επιθέσεις; (3pt)
8. Ποια ώρα της ημέρας έγιναν οι περισσότερες επιθέσεις; (2pt)

### UI - Visualisation (10pt)
9. Οπτικοποιήστε τον αριθμό των server requests ανά 1 hr σε γράφημα (Requests per Hour) (5pt)
10. Οπτικοποιήστε το σύνολο των server requests ανά χώρα σε γράφημα τύπου πίτα (Total Requests per Country) (5pt)

### Bonus (10pt)
11. Ποια IP κατά την γνώμη σας είναι η πιο επικίνδυνη για τον server; Για ποιο λόγο; (10pt)

Δίνονται τα αρχεία καταγραφής: [daily-logs.zip](https://github.com/serrestech/hackathon/raw/topic/daily-logs.zip)


## Παράρτημα
- Keywords: logging, monitoring, log filtering, log visualization, GeoIP, server http attacks, data aggregation, mapping, regex patterns, data mining, owasp.
- [Apache2, Common Log Format](https://httpd.apache.org/docs/2.4/logs.html)
- Top 10 Most Critical Web Application Security Risks: [1](https://www.owasp.org/index.php/Category:OWASP_Top_Ten_Project), [2](https://blog.sucuri.net/2019/01/owasp-top-10-security-risks-part-v.html)
- [Most common HTTP request codes](https://en.wikipedia.org/wiki/List_of_HTTP_status_codes)
- [List of Attack vectors](http://www.tecapi.com/public/relative-vulnerability-rating-gui.jsp)
