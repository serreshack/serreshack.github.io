> Serres Hackathon 4.0 - Topic

# Επίθεση σε webserver Apache2 - Ανάλυση αρχείων καταγραφής (log files)

## Περιγραφή
Μία ΜΚΟ με έδρα την Ελλάδα διατηρεί ένα PHP website με βάση δεδομένων MySQL που περιλαμβάνει εκτός των άλλων σύνδεση χρηστών, online πληρωμές (eshop) και ένα REST API για την διασύνδεση με άλλες υπηρεσίες και εφαρμογές.

Λόγω αμέλειας ο server δέχεται ανεξέλεγκτα επιθέσεις από διάφορα μέρη του πλανήτη. Όλα τα apache access (και error) log requests διατηρούνται στο σύστημα σε αρχεία κατά σειρά με βάση το "Common Log Format, CLF" (βλ. παρακάτω) και με μέγιστο αριθμό 9.000 γραμμών αν αρχείο.

Οι επιθέσεις προκαλούν διάφορα ανεπιθύμητα συμβάντα όπως την διακοπή των υπηρεσιών, την καθυστέρηση της απόκρισης των υπηρεσιών καθώς και την προσπάθεια υποκλοπής δεδομένων και κωδικών σύνδεσης.

## Ζητούμενα

Με βάση τα παραπάνω δεδομένα απαντήστε στις παρακάτω ερωτήσεις ή ολοκληρώστε τις παρακάτω εργασίες:

### A. Γενικά (5pt)
1. Πόσο ήταν συνολικά το traffic που δέχτηκε ο server; (1pt)
2. Πόσα requests προκάλεσαν 5xx server error; (1pt)
3. Πόσες είναι οι ξεχωριστές IP που επισκέφτηκαν τον server; (3pt)

### B. Data Mining (20pt)
4. Ποιο ποσοστό των requests θεωρείτε ότι αποτελούν server attacks; (5pt)
5. Πόσα **SQL Injections**, **XSS**, και **"Local File Inclusion (lfi)"** attacks αναγνωρίσατε συνολικά; (6pt)
6. Ποιες 5 σελίδες δέχονται τις περισσότερες επιθέσεις; (2pt)
7. Από ποια χώρα έρχονται οι περισσότερες επιθέσεις; (5pt)
8. Ποια ώρα της ημέρας έγιναν οι περισσότερες επιθέσεις; (2pt)

### C. UI - Visualisation (15pt)
9. Οπτικοποιήστε τον αριθμό των server requests ανά 1 hr σε γράφημα (Requests per Hour) (2pt)
10. Οπτικοποιήστε το σύνολο των server requests ανά χώρα σε γράφημα τύπου πίτα (Total Requests per Country) (5pt)
11. Αποτυπώστε την προέλευση των attack requests ανά ώρα σε ένα παγκόσμιο χάρτη (8pt)

### D. Bonus (10pt)
12. Ποια IP κατά την γνώμη σας είναι η πιο επικίνδυνη για τον server; Για ποιο λόγο; (10pt)

### Παρατήρηση
- Οι λύσεις που ανιχνεύουν αλγοριθμικά με γενετικούς αλγορίθμους, clustering ή οποιαδήποτε μέθοδο μηχανικής μάθησης τις επιθέσεις αυτές (και άλλα ήδη) και όχι με στατικούς κανόνες θα έχουν +10pt

Δίνονται τα αρχεία καταγραφής: [daily-logs.zip](https://github.com/serrestech/hackathon/raw/topic/daily-logs.zip)


## Παράρτημα
- Keywords: logging, monitoring, log filtering, log visualization, GeoIP, server http attacks, data aggregation, mapping, regex patterns, data mining, owasp.
- [Apache2, Common Log Format](https://httpd.apache.org/docs/2.4/logs.html)
- Top 10 Most Critical Web Application Security Risks: [1](https://www.owasp.org/index.php/Category:OWASP_Top_Ten_Project), [2](https://blog.sucuri.net/2019/01/owasp-top-10-security-risks-part-v.html)
- [Most common HTTP request codes](https://en.wikipedia.org/wiki/List_of_HTTP_status_codes)
- [List of Attack vectors](http://www.tecapi.com/public/relative-vulnerability-rating-gui.jsp)

---

# (English version) Apache2 webserver attacks- Log files analysis

## Description
A NGO (Non Goverment Organisation) hosts a PHP website with a MySQL DB that incudes among others user login, online payments (eshop) as well as a REST API for connecting to other services and applications.
Due to negligence the server is attached uncontrollably from various places in the planet. All of the appache access and error log requests are maintined in the system in files according to the Common Log Format, CLF (see below).
The attacks cause various unwanted events such as service disruption, response delays as well as information and password leakages.

Having said the above, answer the following questions or conclude the following
tasks:

## Tasks & Questions

### A. General (5pt)
1. How much traffic has the server handled? (1pt)
2. How many requests generated requests a 5xx server error? (1pt)
3. How many distinct IPs visited the server? (3pt)

### B. Data Mining (20pt)
4. What percentage of the requests do you consider a server attack? (5pt)
5. How many SQL Injections, XSS, και "Local File Inclusion (lfi)" attacks have
you recognised in total? (6pt)
6. Which 5 pages had the most attacks?(2pt)
7. Which country generated the most attacks? (5pt)
8. What time of the day generated the most attacks? (2pt)

### C. UI - Visualisation (15pt)
9. Visualise the number of server requests/hr in a graph (Requests per Hour)
(2pt)
10. Visualise the total number of server requests/country in a pie chart (Total
Requests per Country) (5pt)
11. Visualise the attack requests/hour on a map(8pt)

### D. Bonus (10pt)
12. Which is the most dangerous IP according to you and why?

### Notice
- Solutions that use genetic algorithms, clustering or any machine learning solutions in order to detect attacks and do not rely on static rules will get +10pt!

Download the server daily log files: [daily-logs.zip](https://github.com/serrestech/hackathon/raw/topic/daily-logs.zip)

## Appendix
- Keywords: logging, monitoring, log filtering, log visualization, GeoIP, server http attacks, data aggregation, mapping, regex patterns, data mining, owasp.
- [Apache2, Common Log Format](https://httpd.apache.org/docs/2.4/logs.html)
- Top 10 Most Critical Web Application Security Risks: [1](https://www.owasp.org/index.php/Category:OWASP_Top_Ten_Project), [2](https://blog.sucuri.net/2019/01/owasp-top-10-security-risks-part-v.html)
- [Most common HTTP request codes](https://en.wikipedia.org/wiki/List_of_HTTP_status_codes)
- [List of Attack vectors](http://www.tecapi.com/public/relative-vulnerability-rating-gui.jsp)