# Consignes pour Claude — CV de Med Karim Bchini

## Ce dépôt est la référence

**`karimtn/cv` est la seule version de référence du CV.** Pour toute question sur le CV de Karim (comparer à une offre, adapter, corriger), partir d'ici : `index.html` (données de tous les profils) et `pdf/`. Les CV Markdown du dépôt `karimtn/linkedin-cv` sont des archives plus anciennes : ne pas s'en servir comme source.

Site en ligne : https://karimtn.github.io/cv/ (ex. `#fr-ia`, `#en-staff`).

## Faits à respecter

- **Autorisation de travail** : éligible à la **carte bleue européenne (Passeport Talent)**, sans opposabilité de la situation de l'emploi. **Pas** « salarié qualifié » : Karim n'a pas de diplôme français. Seuil de salaire carte bleue 2026 : 59 373 € brut/an (à revérifier à chaque nouvelle année).
- Diplôme : ingénieur ESPRIT (Tunis, 2007–2010). Localisation affichée : Paris (relocalisation en cours).
- Cloud : AWS, Azure, et **GCP (utilisé chez NEXT)**.
- Projet agent : `karimtn/jeff-browser` (public). L'agent n'a pas encore tourné sur de vrais sites avec Playwright : ne pas l'affirmer.

## Modifier le CV

1. Les données sont dans `index.html` : `V` (profils), `SK` (compétences, communes à tous les profils), `J` (expériences), `P` (projets), `E` (formation). Les tags (`'ia back'`, `'-ia'` pour exclure un profil) décident où chaque élément s'affiche.
2. Régénérer les PDF (12 fichiers) avec Chrome sans tête :
   ```bash
   for r in lead staff ia fullstack back front; do for l in fr en; do
     google-chrome --headless=new --no-sandbox --disable-gpu --no-pdf-header-footer \
       --virtual-time-budget=3000 --print-to-pdf=pdf/$r-$l.pdf "file://$PWD/index.html?print#$l-$r"
   done; done
   ```
   Le profil IA doit tenir sur **2 pages** ; vérifier le rendu.
3. Pousser `main`, puis `main:gh-pages` (le site est publié depuis `gh-pages`).
