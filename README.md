# Site de contenu DoseTrack (exemple prêt à pousser)

Copie de départ du dépôt public **`dosetrack-contenu`** servi par GitHub Pages
(`https://burundidatainitiative.github.io/dosetrack-contenu/`). Procédure complète :
`docs/admin/PUBLICATION-CONTENU.md` du dépôt de l'application.

```
dosetrack-contenu/
├── .nojekyll              ← GitHub Pages sert les fichiers tels quels
├── index.html             ← page d'explication (aucun script, aucun cookie, aucune mesure d'audience)
├── manifest.json          ← créé et mis à jour par `content_tool.py sign`
└── contenu/
    ├── paquet-<version>.json       ← paquet préparé dans DoseTrack Admin
    └── paquet-<version>.json.sig   ← signature ECDSA P-256 (base64)
```

- Ne jamais modifier un paquet à la main après signature (l'empreinte et la signature ne correspondraient plus :
  l'application le refuse et garde le contenu précédent).
- Garder les anciens paquets : ils servent au retour en arrière (`sign --version`).
- Aucune clé privée dans ce dépôt.
