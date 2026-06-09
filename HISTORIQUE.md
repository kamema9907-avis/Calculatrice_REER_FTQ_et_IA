# Historique des échanges

## 2026-06-09
- **Demande de l'utilisateur** : Définition des règles de base du projet "Calculatrice de Richesse" (retenues à la source, REER FTQ avec crédit supplémentaire de 30%, REER IA Alliance, taux d'imposition 2026 QC/CAN, 5% du salaire avec rendement instantané de 30%). Mise en place de la règle absolue de maintenir ce fichier à jour.
- **Action de l'IA** : Rédaction et proposition du prompt de départ / cahier des charges en tant que spécialiste fiscaliste. Création du fichier `HISTORIQUE.md` à la racine du projet. En attente des corrections et de la validation de l'utilisateur.
- **Demande de l'utilisateur** : Ajout d'une précision : utiliser le rendement de 30% sur les 5% du salaire brut pour démontrer comment cela réduit le coût d'achat des REER. Demande d'un plan d'implémentation clair sous forme d'onglet.
- **Action de l'IA** : Mise à jour de l'historique et création du document `implementation_plan.md`.
- **Commentaires de l'utilisateur sur le plan** : Précision que le 5% du salaire du travailleur est investi dans un placement où la *compagnie* verse un rendement de 30%. Ce montant brut (incluant le rendement) sert à abaisser le coût d'achat des REER. Précision que la cotisation FTQ donnant droit au crédit d'impôt ne peut dépasser 5 000 $.
- **Action de l'IA** : Mise à jour du plan d'implémentation et de l'historique. En attente des réponses aux questions ouvertes.
- **Réponses de l'utilisateur** : Choix des technologies (Vite + React), ajout d'une option de slider pour le rendement (par paliers de 0.1%), et mention d'une image ajoutée contenant les taux d'imposition combinés.
- **Action de l'IA** : Mise à jour du plan. L'IA indique ne pas pouvoir lire l'image directement et demande à l'utilisateur de transcrire le tableau des taux d'imposition dans le chat.
- **Réponses de l'utilisateur** : Transcription manuelle des paliers d'imposition combinés de 0 % à 53,31 %.
- **Action de l'IA** : Intégration complète des paliers dans le plan d'implémentation et mise à jour de l'historique. Demande d'approbation finale avant de débuter le code.
- **Réponses de l'utilisateur** : L'utilisateur précise que le prélèvement de 5 % sert à obtenir un rendement de 30 % de l'employeur, ce qui *augmente* le salaire brut. C'est la totalité de cette somme qui sert à acheter les REER.
- **Action de l'IA** : Correction de la logique dans `taxCalculations.js` et de l'interface `App.jsx`. L'employeur ajoute 30 %, ce qui fait augmenter le revenu imposable. L'économie d'impôt est recalculée spécifiquement sur cette base. Les libellés UI sont mis à jour en "Rendement Employeur" et "Total Achat REER".
- **Commentaires de l'utilisateur** : Le prélèvement de 5 % ne sert PAS à acheter les REER directement. C'est le travailleur qui décide de ses montants d'achats pour le REER FTQ et le REER IA Alliance. Il faut deux curseurs de rendement distincts.
- **Commentaires de l'utilisateur** : Le calcul du retour d'impôt REER doit être précis et tenir compte du changement de paliers marginaux (ex: une cotisation peut faire baisser le revenu imposable d'un palier à 41,12 % vers un palier à 36,12 %).
- **Action de l'IA** : Mise à jour du plan d'implémentation (Section 3). Le calcul fiscal ne se fera plus par une simple multiplication, mais par le calcul complet de l'impôt dû *avant* vs *après* les REER en traversant chaque palier d'imposition pour obtenir l'économie exacte au sou près.
- **Commentaires de l'utilisateur** : L'utilisateur veut partager la calculatrice sur une page web via GitHub (GitHub Pages).
- **Action de l'IA** : Modification de `vite.config.js` avec `base: './'` et création d'un fichier d'automatisation GitHub Actions (`.github/workflows/deploy.yml`) pour que le déploiement se fasse tout seul dès que l'utilisateur dépose ses fichiers sur GitHub.
