# Pour l'évaluation

- **Prendre 10 min à chaque fin de séance pour écrire ce qu'on a fait
    dans le fichier
    [./rapports_hebdomadaires.md](./rapports_hebdomadaires.md)**
- le rapport terminal doit être rédiger en Latex dans le répertoire
  [./rapports](rapports)

# Résolution du système d'équations de Saint-Venant

## Objectif final, très ambitieux.

Les équations de Saint-Venant (appelées équations de *Shallow Water* en anglais)
modélisent la hauteur et la quantité de mouvement des étendues d'eau, dans le
cadre de l'approximation des grands lacs. Elle peut être utilisée par exemple
pour calculer l'écoulement d'une rivière, ou son débordement. Un cas test
standard modélise l'écoulement après une rupture de barrage.

Il s'agit d'un système d'EDP non linéaire de nature assez complexe, et on
s'intéressera pour commencer à l'équation de transport scalaire, \(\partial_t u +
div(cu) = 0\) dans un ouvert \(\Omega\), avec un champ de vecteur vitesse \(c\), tel
que \(div(c)=0\). Les méthodes adaptées à ce type d'équation sont les méthodes de
volumes finis.

Notre objectif final est de résoudre un rupture de barrage pour les équations de
Saint-Venant.

## Première partie : recherche de resources, documentation

1.  Trouver et synthétiser de la documentation sur le type d'équation dont il
    s'agit: l'équation de transport (ou advection) linéaire, à coefficients
    constants ou a divergence nulle. Comment doit-on poser les conditions aux
    limites pour cette équation ?
2.  Dans le cas 1D avec un champ de vitesse constant, comment écrit-on la
    solution exacte ?
3.  Trouver de la documentation sur les méthodes de volumes finis pour cette
    équation. Donner quelques exemples de flux numériques.
4.  Doit-on résoudre un système linéaire ? Comment doit-on choisir le pas de
    temps ?
5.  Dans le cas d'un système d'équations de transport à coefficients constants,
    qu'est-ce qui change dans l'équation ? comment peut-on modifier notre méthode
    numérique ?

## Deuxième partie : programmation dans un cas simplifié

On se place pour cette partie dans le cas de l'équation en dimension \(d=1\),
c'est à dire sur l'intervalle \(\Omega = (0,1)\). L'objectif est de comprendre
l'implémentation des méthodes.

1.  Détailler l'architecture du code à implémenter, en essayant d'avoir un code
    modulaire et extensible facilement. Entrées et sorties ? Structuration du
    code en fichiers ? Quels outils de l'ensemble scipy/numpy ?
2.  Choisir quelques exemples concrets de solution exactes. Nous les utiliserons
    pour valider notre implémentation.
3.  Programmer la résolution du problème dans le cas linéaire, et vérifier cette
    implémentation à l'aide des tests de la question 2.

## Troisième partie : le cas général

On va généraliser le code produit dans la partie précédente au cas 2D et
au cas non-linéaire.

1.  Déterminer comment le code produit précédant peut se généraliser à la
    dimension 2, dans le cas linéaire. Qu'est-ce qui change ? Quels sont les
    fichiers à modifier ? Comment pourrait-on trouver des solutions analytiques
    permettant de valider l'implémentation ?
2.  Produire le code de résolution du problème en 2D et le tester,
3.  Construire de la même manière la résolution du problème de rupture de barrage
    des équations de Saint-Venant, et montrer quelques résultats numériques.

## refs

À compléter dans le répertoire [./refs](./refs)

-   Livre de R. Levêque,
    <https://babordplus.hosted.exlibrisgroup.com/permalink/f/1iou14g/33PUDB_Alma_Unimarc7158699040004671>
-   Livre de E. Godlewski et P.-A. Raviart, très théorique, mais
    accessible en ligne (via Babord+)
    <https://babordplus.hosted.exlibrisgroup.com/permalink/f/1iou14g/33PUDB_Alma_Unimarc7159464460004671> 
-   Resources en ligne ?
    + diapo/cours G. James: <http://www-ljk.imag.fr/membres/Guillaume.James/transport.pdf>
    + cours F. Boyer (bcp plus difficile): <https://www.math.univ-toulouse.fr/~fboyer/_media/enseignements/cours_transport_fboyer.pdf>
