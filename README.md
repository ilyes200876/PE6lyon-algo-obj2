# PE6lyon-algo-obj2

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