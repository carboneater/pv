# pv
Librairie de création de PVs pour Assemblées Délibérantes

## Comment l'utiliser
Renommer chacun des fichiers  * .sample.tex en un fichier  * .tex

Ensuite, il suffit de suivre les instructions dans chacun des fichiers et le guide pour cuisiner un beau PV.

### Configuration
Le fichier de configuration contient de nombreuses options pour gérer la mise en forme du PV.

#### Les macros de textes
Les macros de texte ont tous la même forme: \newcommand{Nom_du_macro}{Texte}
Pour modifier ces macros, il suffit de changer le texte dans les deuxièmes accolades.

#### Les booléens de mise en page
Les booléens de mise en page ont la forme suivante:
```
\newbool{Nom}
\booltrue{Nom}
% \boolfalse{Nom}
```
Pour désactiver un booléen, il faut commenter la ligne booltrue et décommenter la ligne boolfalse. (Pour commenter, précéder la ligne d'un %, pour décommenter, retirer le symbole.)

##### L'utilité de chacun des booléens:
- showFEUSCoverHeader: La FEUS utilise une entête particulier sur ses PVs qu'elle est la seule à utiliser, pour contrôler l'affichage de cet entête.
- showAttendees: Affiche la liste de présences. (Utile pour toutes les instances où la liste des présences est connue. Les AGs sont souvent des instances où le secrétaire n'a pas de liste de présence à remplir.)
- showYear: Affiche l'année d'opération de la compagnie dans la numérotation des points. (Le modèle FEUS pour numéroter ses points en instance est: Instance Année/Session.Point)
- showSession: Même utilité que showYear, mais pour le numéro de la session active.
- useUnderline: Pour activer/désactiver les soulignés dans le texte. Certaines conversion de PDF vers DOCX brisent ces lignes et on doit les désactiver.
- showLogo: Pour afficher le logo de la compagnie en page couverture.

## Compiler le résultat
Votre éditeur LaTeX devrait gérer la compilation par lui-même.

Sinon, il est toujours possible de compiler le PV en invoquant la commande
`pdflatex pv.tex`
