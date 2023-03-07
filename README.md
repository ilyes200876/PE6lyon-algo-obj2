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
  Déclarer mat []
  Déclarer trésor [] 
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


 
