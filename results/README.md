# Hackathon Serres 2019 - Results

## Α. Πως δημιουργήθηκαν τα log files

Τα [log files](https://github.com/serrestech/hackathon/tree/topic/daily-logs.zip) που δόθηκαν στο Hackahton δημιουργήθηκαν με το εργαλείο [apache-log-generator](https://github.com/theodorosploumis/apache-log-generator) που είναι ένας fake apache log generator σε php και δημιουργήθηκε ειδικά για τις ανάγκες αυτού του Hackathon. 

Για να δείτε ένα παράδειγμα settings παρόμοιο με αυτό που χρησιμοποιήθηκε στο Hackathon δείτε το [settings.example.php](https://github.com/theodorosploumis/apache-log-generator/blob/master/settings.example.php).

Όπως θα διαπιστώσετε όλα τα [attack_suffixes](https://github.com/theodorosploumis/apache-log-generator/blob/master/settings.example.php#L83) που **δεν είναι κενά** αποτελούν ένα attack request.

Αν από τα logs αφαιρέσουμε τα requests που δεν έχουν "attack suffix" τότε θα πάρουμε log files μόνο με τα attack requests (βλ. επισύναψη).


## Β. Πως απαντήθηκαν τα ερωτήματα

- Για την απάντηση στα 1 - 3 χρησιμοποιήθηκαν κοινά cli commands.
- Για τα θέματα Data Mining χρησιμοποιήθηκαν ειδικοί [attack log analyzers](https://github.com/theodorosploumis/apache-log-generator#log-analyzers-for-security-problems) και ιδιαιτέρως το LORG και Scalp. Αυτά τα εργαλεία είναι parsers με patterns που παίρνουν κυρίως από το [PHPIDS](https://en.wikipedia.org/wiki/PHPIDS).

## Γ. Βαθμολογία ομάδων

Όλες οι ομάδες έλαβαν βαθμούς ανάλογα με την απάντηση που έδωσαν σε κάθε θέμα. Οι χορηγοί συμμετείχαν με ποσοστό 30% στην βαθμολόγηση του UI καθώς και της παρουσίασης που έκαναν οι ομάδες.

Η [αναλυτική βαθμολογία των ομάδων βρίσκεται εδώ](https://github.com/serrestech/hackathon/blob/topic/results/team_results_2019.pdf).


## Δ. Απαντήσεις - βαθμοί

### Γενικά (5pt)
| No | Ερώτηση | Απάντηση |
|-----| ------- | -------- |
| 1 | Πόσο ήταν συνολικά το traffic που δέχτηκε ο server; (1pt) | 3708 MB |
| 2 | Πόσα requests προκάλεσαν 5xx server error; (1pt) | 4729 |
| 3 | Πόσες είναι οι ξεχωριστές IP που επισκέφτηκαν τον server; (3pt) | 20 |

### Data Mining (15pt)
| No | Ερώτηση | Απάντηση |
|-----| ------- | -------- |
| 4 | Ποιο ποσοστό των requests θεωρείτε ότι αποτελούν server attacks; (3pt) | 63929 of 86400 = 74 % |
| 5 | Πόσα SQL Injections, XSS, και "Local File Inclusion (lfi)" attacks αναγνωρίσατε συνολικά; (5pt) | sql (2618) + xss (12728) + lfi (13316) = 28662 |
| 6 | Ποιες 5 σελίδες δέχονται τις περισσότερες επιθέσεις; (2pt) | `/, /index.php, /login.php, /api/v1/login, /core/files/js/editor.js` |
| 7 | Από ποια χώρα έρχονται οι περισσότερες επιθέσεις; (3pt) | China |
| 8 | Ποια ώρα της ημέρας έγιναν οι περισσότερες επιθέσεις; (2pt) | 20:00 - 21:00 GMT+2 |

### UI - Visualisation (18pt)
| No | Ερώτηση | Απάντηση |
|-----| ------- | -------- |
| 9 | Οπτικοποιήστε τον αριθμό των server requests ανά 1 hr σε γράφημα (Requests per Hour) (2pt) | |
| 10 | Οπτικοποιήστε το σύνολο των server requests ανά χώρα σε γράφημα τύπου πίτα (Total Requests per Country) (5pt) | |
| 11 | Αποτυπώστε την προέλευση των attack requests ανά ώρα σε ένα παγκόσμιο χάρτη (8pt) | |

### Bonus (10pt)
| No | Ερώτηση | Απάντηση |
|-----| ------- | -------- |
| 12 | Ποια IP κατά την γνώμη σας είναι η πιο επικίνδυνη για τον server; Για ποιο λόγο; (10pt) | 62.109.16.162 |

### Extra Bonus (10pt)
Οι ομάδες που είχαν υλοποίηση με μέθοδο **Clustering** παίρνουν +10pts.

### Presentation (10pt)
Αξιολόγηση της παρουσίασης. Πόσο κοντά ήταν στο θέμα, πόσο κατανοητή, αν ήταν ικανοποιητική αισθητικά, αν ήταν εντός χρόνου κτλ.

Στην κατηγορία αυτή συμμετείχαν και οι χορηγοί.



---

## Attachments

- [Hackathon Team results & Points](https://github.com/serrestech/hackathon/blob/topic/results/team_results_2019.pdf)
- [list-of-attack-suffixes.txt](https://github.com/serrestech/hackathon/blob/topic/results/list-of-attack-suffixes.txt)
- [Log file only with the attack requests](https://github.com/serrestech/hackathon/blob/topic/results/only-attacks.log)
- [LORG, Scalp & Goaccess analysis report](https://github.com/serrestech/hackathon/blob/topic/results/attack-reports.zip)