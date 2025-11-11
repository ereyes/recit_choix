# recit_choix

Prototype simple :  
https://ereyes.github.io/recit_choix/01-choices.html

Application web minimaliste qui propose une narration interactive en 3 étapes :  
https://ereyes.github.io/recit_choix/02-choices-csv.html 

* **Écran 1 (bleu)** : 3 choix (divs) → on enregistre le choix
* **Écran 2 (vert)** : 3 choix → on enregistre le choix
* **Écran 3 (rouge)** : 3 choix → on enregistre le choix
* **Écran final (blanc)** : récapitulatif des 3 choix

Les contenus (libellés, descriptions, titres d’étape) sont **pilotés par un fichier CSV** afin de faciliter la personnalisation sans toucher au code.

## Spécification du CSV

**En‑têtes (à conserver tels quels pour compatibilité) :**

```
step,step_title,step_subtitle,step_bg,label,description
```

* `step` : numéro de l’étape (`1`, `2`, `3`)
* `step_title` : titre affiché en haut de l’écran
* `step_subtitle` : sous‑titre (ex. “Étape 1 sur 3”)
* `step_bg` : couleur d’arrière‑plan de l’étape
  **Valeurs acceptées :** `blue | green | red` **ou** `bleu | vert | rouge`
* `label` : libellé du choix (titre dans la carte)
* `description` : texte optionnel sous le libellé

> L’UI affiche **3 choix par écran**.
> Si vous mettez plus de 3 lignes pour une étape, **seules les 3 premières** seront affichées.
> Si vous en mettez moins, l’UI complète avec des cartes vides pour garder la grille.

### Exemple `choices.csv` (français)

```csv
step,step_title,step_subtitle,step_bg,label,description
1,Où commence votre voyage ?,Étape 1 sur 3,blue,Forêt,"Des pins qui chuchotent et des sentiers cachés."
1,Où commence votre voyage ?,Étape 1 sur 3,blue,Ville,"Néons et rues bondées."
1,Où commence votre voyage ?,Étape 1 sur 3,blue,Mer,"Air salin, mouettes et horizons lointains."
2,Qui voyage avec vous ?,Étape 2 sur 3,green,Renard,"Rusé, rapide et discret."
2,Qui voyage avec vous ?,Étape 2 sur 3,green,Robot,"Fiable, logique et lumineux."
2,Qui voyage avec vous ?,Étape 2 sur 3,green,Barde,"Des chansons pour le courage et des indices."
3,Que cherchez-vous ?,Étape 3 sur 3,red,Trésor,"De l'or, des reliques et des cartes perdues depuis longtemps."
3,Que cherchez-vous ?,Étape 3 sur 3,red,Sagesse,"Des réponses à des questions pas encore posées."
3,Que cherchez-vous ?,Étape 3 sur 3,red,Liberté,"Pas de murs. Pas de limites. Ciel ouvert."
```

**Encodage recommandé :** UTF‑8 (pour conserver les accents).
