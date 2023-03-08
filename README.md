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

# 2. Écrire la classe Carte qui a comme attribut une matrice de cases, et un trésor qui a des 
# coordonnées [x,y] sur la carte (on suppose qu’il est bien sur la carte). Écrire la classe Aventurier 
# qui a un nom et des coordonnées, et qui a une méthode « déplacer(x, y) qui permet de le déplacer 
# sur la carte.

TYPE Carte 
  Déclarer cases[][]
  Déclarer trésor[] 
FINTYPE
TYPE Aventurier
  Déclarer Carte carte
  Déclarer nom
  Déclarer coordonnée[]
  PROCEDURE déplacer(var x, var y)
  DÉBUT
    SI x >= 0 ET x < taille(this.carte.cases) ET y < taille(this.Carte.cases[x]) ET y > 0 ALORS
      this.coordonnées <- [x, y]
    FINSI
    AFFICHER "La map " . this.nom . "qui a bougé de" . this.x . " x et de " . this.y " y."
  FIN
FINTYPE

# Modifier la classe Aventurier pour vérifier qu’on essaie de déplacer l’aventurier sur une case 
# adjacente (haut, gauche, bas, droite), sinon afficher une erreur. 
 
# Modifier la classe Aventurier pour lui permettre de se déplacer en diagonale



Type Carte
    Déclarer cases[][]
    Déclarer trésor[]

    FONCTION coordonnéesValides(var x, var y)
    DÉBUT
        SI x >= 0 ET x < taille(this.cases)
            ET y < taille(this.cases[x]) ET y >= 0 ALORS
            Renvoyer VRAI
        FINSI
        Renvoyer FAUX
    FIN

FinType


Type Aventurier
    Déclarer nom
    Déclarer coordonnées[]
    Déclarer Carte carte

    FONCTION estCaseGauche( var dest_x, var dest_y)
    DÉBUT
        Déclarer x <- this.coordonnées[0]
        Déclarer y <- this.coordonnées[1]
        SI dest_y = y ET dest_x = x - 1 ALORS
            Renvoyer VRAI
        FINSI
        Renvoyer FAUX
    FIN

    FONCTION estCaseDroite( var dest_x, var dest_y)
    DÉBUT
        Déclarer x <- this.coordonnées[0]
        Déclarer y <- this.coordonnées[1]
        SI dest_y = y ET dest_x = x + 1 ALORS
            Renvoyer VRAI
        FINSI
        Renvoyer FAUX
    FIN

    FONCTION estCaseHaut( var dest_x, var dest_y)
    DÉBUT
        Déclarer x <- this.coordonnées[0]
        Déclarer y <- this.coordonnées[1]
        SI dest_x = x ET dest_y = y + 1 ALORS
            Renvoyer VRAI
        FINSI
        Renvoyer FAUX
    FIN

    FONCTION estCaseBas( var dest_x, var dest_y)
    DÉBUT
        Déclarer x <- this.coordonnées[0]
        Déclarer y <- this.coordonnées[1]
        SI dest_x = x ET dest_y = y - 1 ALORS
            Renvoyer VRAI
        FINSI
        Renvoyer FAUX
    FIN

    FONCTION estCaseHautGauche( var dest_x, var dest_y)
    DÉBUT
        Déclarer x <- this.coordonnées[0]
        Déclarer y <- this.coordonnées[1]
        SI dest_y = y + 1 ET dest_x = x - 1 ET ALORS
            Renvoyer VRAI
        FINSI
        Renvoyer FAUX
    FIN

    FONCTION estCaseAdjacente(var dest_x, var dest_y)
    DÉBUT

        SI estCaseGauche(dest_x, dest_y) 
            OU estCaseHaut(dest_x, dest_y)
            OU estCaseDroite(dest_x, dest_y)
            OU estCaseBas(dest_x, dest_y)
            ALORS
            Renvoyer VRAI
        FINSI
        Renvoyer FAUX
    FIN