# PE6lyon-algo-obj2
# 1. Écrire la classe Apprenant qui a comme attribut un nom et un liste de notes, et comme méthode 
# une méthode calculerMoyenne() qui retourne sa moyenne, et une méthode afficher() qui affiche 
# son nom et sa moyenne. ##

Objets partie 2 énoncé 1 : 
Type Apprenant
    Déclarer notes[]
    Déclarer nom
    FONCTION calculerMoyenne()
    DÉBUT
        Déclarer somme <- 0
        Déclarer moyenne <- -1
        // Je vérifie que j'ai au moins une note pour calculer la moyenne
        SI taille(this.notes) >= 1 ALORS
            Déclarer indice <- 0
            TANT QUE indice < taille(this.notes) FAIRE
                somme <- somme + this.notes[indice]
                indice <- indice + 1
            FIN TANTQUE
            moyenne <- somme/taille(this.notes)
        FINSI

        Renvoyer moyenne
    FIN
    FONCTION afficher()
    DÉBUT
      AFFICHER "la note de" this.nom "est" this.calculerMoyenne()
    FIN
FinType