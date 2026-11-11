---
description: "Use when writing, modifying, testing, reviewing, or documenting code in the Travel & Expense assistant project."
---

# Règles de développement

- Écris un code simple, lisible, typé et cohérent avec le projet.
- Respecte les conventions de nommage et l'organisation des fichiers du projet.
- Commente le code, mais seulement la logique non évidente ; garde les commentaires concis et à jour.
- Pour chaque changement de comportement, ajoute ou adapte les tests. Lance les vérifications pertinentes : `uv run pytest`, `uv run ruff check .`, `uv run ruff format --check .` et `uv run pyright .`.
- Vérifie que les tests passent et que le code respecte les standards avant de valider les changements.
- Indique les vérifications réellement exécutées et les éventuelles limites.
- Si Context7 est disponible, consulte sa documentation avant d'utiliser une API et vérifie sa compatibilité avec les versions de `uv.lock`.
- Si le fichier de specification (SPEC.md) existe, lis-le avant de coder. Respecte la spec ; en cas de conflit ou d'ambiguïté, demande une décision.
- Consigne les décisions durables dans `docs/adr/NNNN-titre.md` (contexte, décision, conséquences). Ne réécris pas une ADR acceptée : remplace-la par une nouvelle. Respecte les ADR existantes et ne contredis pas les décisions déjà prises.
- Maintiens la documentation du projet à jour.
