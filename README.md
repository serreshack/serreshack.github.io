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

### Α. Γενικά (5pt)
| No | Ερώτηση | Απάντηση |
|-----| ------- | -------- |
| 1 | Πόσο ήταν συνολικά το traffic που δέχτηκε ο server; (1pt) | 3708 MB |
| 2 | Πόσα requests προκάλεσαν 5xx server error; (1pt) | 4729 |
| 3 | Πόσες είναι οι ξεχωριστές IP που επισκέφτηκαν τον server; (3pt) | 20 |

### Β. Data Mining (15pt)
| No | Ερώτηση | Απάντηση |
|-----| ------- | -------- |
| 4 | Ποιο ποσοστό των requests θεωρείτε ότι αποτελούν server attacks; (3pt) | 63929 of 86400 = 74 % |
| 5 | Πόσα SQL Injections, XSS, και "Local File Inclusion (lfi)" attacks αναγνωρίσατε συνολικά; (5pt) | sql (2618) + xss (12728) + lfi (13316) = 28662 |
| 6 | Ποιες 5 σελίδες δέχονται τις περισσότερες επιθέσεις; (2pt) | `/, /index.php, /login.php, /api/v1/login, /core/files/js/editor.js` |
| 7 | Από ποια χώρα έρχονται οι περισσότερες επιθέσεις; (3pt) | China |
| 8 | Ποια ώρα της ημέρας έγιναν οι περισσότερες επιθέσεις; (2pt) | 20:00 - 21:00 GMT+2 |

### Γ. UI - Visualisation (18pt)
| No | Ερώτηση | Απάντηση |
|-----| ------- | -------- |
| 9 | Οπτικοποιήστε τον αριθμό των server requests ανά 1 hr σε γράφημα (Requests per Hour) (2pt) | |
| 10 | Οπτικοποιήστε το σύνολο των server requests ανά χώρα σε γράφημα τύπου πίτα (Total Requests per Country) (5pt) | |
| 11 | Αποτυπώστε την προέλευση των attack requests ανά ώρα σε ένα παγκόσμιο χάρτη (8pt) | |

### Δ. Bonus (10pt)
| No | Ερώτηση | Απάντηση |
|-----| ------- | -------- |
| 12 | Ποια IP κατά την γνώμη σας είναι η πιο επικίνδυνη για τον server; Για ποιο λόγο; (10pt) | 62.109.16.162 |

### Ε. Extra Bonus (10pt)
Εάν έχετε στην υλοποίηση σας **Clustering** παίρνετε επιπλέον bonus 10pt.

## Log files
| Download here: [Server logs for whole day of May 19 2019](https://github.com/serrestech/hackathon/raw/topic/daily-logs.zip)

## Παράρτημα
- Apache2, Common Log Format: https://httpd.apache.org/docs/2.4/logs.html
- Λέξεις κλειδιά: logging, monitoring, log filtering, log visualization, GeoIP, server http attacks, data aggregation, mapping, regex patterns, GNU zip (gzip), log rotate
- Most common HTTP request codes: https://en.wikipedia.org/wiki/List_of_HTTP_status_codes
- List of UserAgentStrings: http://www.useragentstring.com/pages/useragentstring.php
- Server attack types & patterns (DDOS, Bruteforcing, XSS, SQL Injection, XSRF, Remote File Inclusion)
- Server hack types (Url misinterpretation, directory browsing, get “non-web” files, reverse proxying, java decompilation, source code disclosure, input validation, SQL query poisoning, Session Hijacking, Buffer overflows)
