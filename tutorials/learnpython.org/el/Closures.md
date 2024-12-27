Μια Κλείσιμο (Closure) είναι ένα αντικείμενο συνάρτησης που θυμάται τιμές σε περιβάλλοντα πεδία, ακόμα και αν αυτές δεν υπάρχουν στη μνήμη. Ας το δούμε βήμα προς βήμα

Πρώτα απ' όλα, μια **Φωλιασμένη Συνάρτηση** είναι μια συνάρτηση που ορίζεται μέσα σε άλλη συνάρτηση. Είναι πολύ σημαντικό να σημειώσουμε ότι οι φωλιασμένες συναρτήσεις μπορούν να έχουν πρόσβαση στις μεταβλητές του περιβάλλοντος πεδίου. Ωστόσο, τουλάχιστον στην Python, είναι μόνο ανάγνωσης. Ωστόσο, μπορούμε να χρησιμοποιήσουμε τη δεσμευμένη λέξη "nonlocal" ρητά με αυτές τις μεταβλητές προκειμένου να τις τροποποιήσουμε.

Για παράδειγμα:

    def transmit_to_space(message):
        "Αυτή είναι η περιβάλλουσα συνάρτηση"
        def data_transmitter():
            "Η φωλιασμένη συνάρτηση"
            print(message)
    
        data_transmitter()

    print(transmit_to_space("Δοκιμαστικό μήνυμα"))

Αυτό λειτουργεί καλά καθώς η συνάρτηση 'data_transmitter' μπορεί να έχει πρόσβαση στο 'message'. Για να δείξουμε τη χρήση της δεσμευμένης λέξης "nonlocal", εξετάστε το εξής

    def print_msg(number):
        def printer():
            "Εδώ χρησιμοποιούμε τη δεσμευμένη λέξη nonlocal"
            nonlocal number
            number=3
            print(number)
        printer()
        print(number)
    
    print_msg(9)

Χωρίς τη χρήση της δεσμευμένης λέξης nonlocal, το αποτέλεσμα θα ήταν "3 9", ωστόσο, με τη χρήση της, λαμβάνουμε "3 3", δηλαδή η τιμή της μεταβλητής "number" τροποποιείται.

Τώρα, τι θα λέγατε να επιστρέψουμε το αντικείμενο συνάρτησης αντί να καλέσουμε τη φωλιασμένη συνάρτηση μέσα:

    def transmit_to_space(message):
        "Αυτή είναι η περιβάλλουσα συνάρτηση"
        def data_transmitter():
            "Η φωλιασμένη συνάρτηση"
            print(message)
        return data_transmitter

Και καλούμε τη συνάρτηση ως εξής:

      def transmit_to_space(message):
        "Αυτή είναι η περιβάλλουσα συνάρτηση"
        def data_transmitter():
            "Η φωλιασμένη συνάρτηση"
            print(message)
        return data_transmitter
        
  	  fun2 = transmit_to_space("Κάψε τον Ήλιο!")
  	  fun2()

Παρόλο που η εκτέλεση της "transmit_to_space()" ολοκληρώθηκε, το μήνυμα διατηρήθηκε. Αυτή η τεχνική με την οποία τα δεδομένα συνδέονται με κάποιο κώδικα ακόμα και μετά το τέλος αυτών των άλλων αρχικών συναρτήσεων ονομάζεται κλείσιμο (closures) στην Python.

ΠΛΕΟΝΕΚΤΗΜΑ: Τα κλεισίματα μπορούν να αποφύγουν τη χρήση καθολικών μεταβλητών και παρέχουν κάποια μορφή απόκρυψης δεδομένων. (Π.χ. Όταν υπάρχουν λίγες μέθοδοι σε μια κλάση, χρησιμοποιήστε κλείσιμο.)

Επίσης, οι Διακοσμητές (Decorators) στην Python κάνουν εκτεταμένη χρήση των κλεισίμων.

Exercise
--------

Φτιάξτε μια φωλιασμένη βρόχο και ένα κλείσιμο στην Python για να δημιουργήσετε συναρτήσεις για να αποκτήσετε πολλαπλές συναρτήσεις πολλαπλασιασμού χρησιμοποιώντας κλείσιμο. Δηλαδή, χρησιμοποιώντας κλείσιμο, κάποιος θα μπορούσε να δημιουργήσει τις συναρτήσεις multiply_with_5() ή multiply_with_4() χρησιμοποιώντας κλείσιμο.