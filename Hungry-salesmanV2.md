---
name: hungry-salesman-v2
description: >
  Déclenche ce skill dès que Nicolas prépare un premier contact / call de découverte / RDV commercial B2B avec un prospect.
  Expressions : "hungry salesman", "hungry salesman v2", "prépare-moi un script de call", "j'ai un RDV avec X chez Y", "premier contact avec",
  "call de découverte", "prépare mon call", "script d'appel", "brief commercial".
  Produit un .docx avec : (1) note de contexte enrichie — presse 6 mois + revue de presse 10 articles FR/international + buzz social media + earning calls si cotée ;
  (2) script de call OPA + questions d'introduction (reporting line + approfondissement challenges) + SPIN, règle 80/20, annexes objections + cases Haigo + post-call.
  Utilise ce skill même sans phrase explicite — dès qu'il s'agit de préparer un entretien commercial B2B avec un prospect nommé.
---

# Hungry Salesman Skill — V2

## Purpose

Ce skill aide Nicolas (Head of Sales chez Haigo) à préparer chaque premier contact avec un prospect de manière rigoureuse et rapide. Un commercial "affamé" arrive en RDV avec :

1. **Une connaissance fraîche du contexte du prospect** (actualités récentes, orientations stratégiques, enjeux, signaux faibles, **buzz médiatique et social media**)
2. **Un plan d'entretien structuré** qui maximise la parole du prospect (80/20) tout en couvrant systématiquement Reporting line → Challenges → Situation → Problèmes → Implications → Bénéfices de la solution
3. **Des munitions prêtes** : cases Haigo mappés aux objections probables, pitch agence en 3 formats (20/40/60 sec), questions de réserve

Le skill produit un **document Word unique** que Nicolas peut imprimer, annoter à la main et emporter en RDV.

**Nouveautés V2 :**
- Bloc **Revue de presse** étoffé avec 10 derniers articles (FR + international) + monitoring social media
- Bloc **Questions d'introduction** structurées sur le reporting line et l'approfondissement des challenges du moment

---

## Activation

Le skill s'active sur :
- **Phrase explicite** : "hungry salesman", "hungry salesman v2"
- **Intents commerciaux** : "prépare un script de call / entretien / RDV avec X", "premier contact", "call de découverte avec", "je vais rencontrer", "brief pour mon call", "prépare mon rendez-vous chez"
- **Tout message** où l'utilisateur mentionne un **prénom+nom+entreprise** d'un prospect et demande de l'aider à s'y préparer

Si le déclenchement est ambigu (ex. "parle-moi de la société X"), **NE PAS déclencher** — c'est probablement une demande de recherche simple, pas un brief de call.

---

## Configuration — variables Haigo (à utiliser tel quel)

Ces variables s'insèrent dans le pitch et les annexes. Elles concernent **l'agence Haigo**, pour laquelle Nicolas travaille.

| Variable | Valeur |
|---|---|
| `HAIGO_POSITIONING` | Équipe internationale de spécialistes CX qui conçoivent des produits, services et expériences utiles, utilisables et désirables |
| `HAIGO_PARENT` | Filiale du groupe Kyu (Hakuhodo DY) depuis 2020 |
| `HAIGO_COLLECTIVE` | Kyu Collective — 3 500+ talents dans 14 pays |
| `HAIGO_EMPLOYEES` | [XX employés] (à demander à Nicolas si non fourni ; laisser le placeholder sinon) |
| `HAIGO_3_PILIERS` | Recherche qualitative (terrain, ethnographie, interviews) · Analyses quantitatives (data, modélisations) · Design (service design, UX/UI, prototypage) |
| `HAIGO_3_OFFRES` | Insight Sprint (3–4 sem.) · CX Action Mapping (4–6 sem.) · Design Sprint (5 jours) |

**Important :** ces variables ne changent jamais d'un prospect à l'autre — elles sont génériques au skill. Seul le contenu prospect change.

---

## Processus — 3 phases

### Phase 1 — Note de contexte d'entreprise (AVANT le script)

**Objectif :** permettre à Nicolas de lire en 5 minutes et d'arriver en RDV avec une compréhension fraîche du moment business de son interlocuteur, y compris **ce qui se dit publiquement et viralement** sur la marque.

**Recherche à effectuer (web search) :**

1. **Fiche identité** — nom, secteur, CA, effectifs, périmètre géographique, maison-mère, cotation en bourse (oui/non, ticker)

2. **Signaux presse (6 derniers mois)** — chercher explicitement avec des requêtes comme `"[nom entreprise]" news 2026`, `"[nom entreprise]" announcement`, `"[nom entreprise]" strategy`, `"[nom entreprise]" CEO`, `"[nom entreprise]" layoffs / hiring / acquisition`. Cibler : réorganisations, nominations, acquisitions/cessions, nouveaux produits/services, incidents, partenariats majeurs, changements de stratégie, levées de fonds.

3. **🆕 REVUE DE PRESSE — 10 derniers articles** (BLOC OBLIGATOIRE V2)
   - **Presse française (5 articles minimum)** : Les Échos, Le Figaro, Le Monde, La Tribune, BFM Business, L'Usine Nouvelle, LSA, e-marketing.fr, Stratégies, CB News, ainsi que la presse sectorielle pertinente
   - **Presse internationale (5 articles minimum)** : Financial Times, Wall Street Journal, Reuters, Bloomberg, The Economist, Forbes, Fortune, Business Insider, ainsi que la presse sectorielle internationale
   - **Pour chaque article :** Date · Titre exact · Média · Lien (URL complète) · 1 phrase de résumé (max 25 mots)
   - Privilégier les articles des **6 derniers mois**, classés du plus récent au plus ancien
   - **Buzz social media (en complément)** : identifier les 3–5 contenus les plus discutés sur la marque sur LinkedIn, X (Twitter), Reddit, TikTok (selon pertinence sectorielle). Pour chacun : plateforme · auteur · sujet · volume d'engagement (likes/partages/commentaires si visible) · sentiment global (positif / neutre / négatif / polémique). Sources possibles : Brand24, Talkwalker, Mention, ou recherche directe sur les plateformes.
   - **Lecture stratégique :** en 3 lignes, dire ce que cette revue de presse révèle sur le **momentum** de la marque (en croissance / sous tension / en repositionnement / sous attaque réputationnelle / silencieuse)

4. **Earning calls (si cotée uniquement)** — chercher les **2 dernières publications trimestrielles/annuelles**. Source : site investor relations de l'entreprise, seekingalpha, transcripts officiels. Extraire pour chacune :
   - Chiffres-clés (CA, marge, guidance)
   - 3 thèmes stratégiques dominants mentionnés par le CEO/CFO
   - Risques cités
   - Questions récurrentes des analystes

5. **Contexte interlocuteur** — LinkedIn, tribunes, interviews du prospect. Son parcours, ses priorités annoncées, ses éventuelles prises de parole publiques. **Identifier en particulier sa probable reporting line** (à qui il rapporte / qui rapporte à lui — déduit de l'organigramme public ou d'indices LinkedIn).

6. **Enjeux stratégiques probables** — déduits de ce qui précède : quelles sont les 3 tensions CX/produit/service que cette entreprise est susceptible de vivre ?

**Web search obligatoire.** Ne jamais rédiger cette note à partir de la seule mémoire interne — le contexte change trop vite. Si une information ne peut pas être trouvée, dire explicitement "non trouvé sur le web" plutôt que d'inventer.

**Format de la note dans le docx :**

```
Page 1 — NOTE DE CONTEXTE ENTREPRISE

[En-tête] Prospect : [Prénom Nom, Fonction] — [Entreprise]
         Date du RDV : [date]
         Durée prévue : [30 min]

[Bloc 1] FICHE IDENTITÉ (tableau 2 colonnes)
[Bloc 2] 📰 SIGNAUX PRESSE — 6 DERNIERS MOIS (liste à puces, 5–8 items, chaque item = date + headline + une phrase de contexte + source)

[Bloc 3 — 🆕 V2] 🗞️ REVUE DE PRESSE — 10 DERNIERS ARTICLES
   3.A — Presse française (5 articles, tableau : Date | Titre | Média | Lien | Résumé 1 phrase)
   3.B — Presse internationale (5 articles, même format)
   3.C — Buzz social media (3–5 contenus les plus discutés : plateforme, auteur, sujet, engagement, sentiment)
   3.D — Lecture stratégique (3 lignes : ce que ça dit du momentum de la marque)

[Bloc 4] 📊 SYNTHÈSE EARNING CALLS (si coté) — 2 derniers trimestres, avec chiffres et thèmes
[Bloc 5] 👤 CONTEXTE INTERLOCUTEUR (parcours, publications, priorités, reporting line probable)
[Bloc 6] 🎯 3 ENJEUX STRATÉGIQUES PROBABLES (déduction raisonnée, à valider dans le call)
[Bloc 7] 🎤 3 ANGLES D'ACCROCHE (3 ouvertures possibles en lien avec l'actualité ou un article récent)
```

---

### Phase 2 — Script de call OPA + INTRODUCTION + SPIN

**Règles de rédaction (non négociables) :**
- **Durée cible : 30 minutes maximum**
- **Prospect parle 80% du temps** — cela se traduit par peu de phrases côté Nicolas, beaucoup de questions ouvertes.
- **OPA** en ouverture (Objectif, Plan, Accord) : 3–4 minutes max
- **🆕 V2 — INTRODUCTION** : bloc de questions visant à établir le **reporting line** de la personne interrogée et à **approfondir ses challenges du moment** (3–4 minutes), AVANT le SPIN
- **SPIN** ensuite, en 4 temps clairement titrés :
  - **S — Situation** (3–4 questions factuelles)
  - **P — Problème** (3–4 questions sur les difficultés)
  - **I — Implications** (3–4 questions sur les conséquences)
  - **N — Need-payoff / Conclusion** (2–3 questions projetant la valeur d'une solution)
- Chaque bloc de questions est **numéroté** et **laisse de l'espace pour prendre des notes** à la main
- Les **mots exacts à dire** par Nicolas sont en **bloc citation** (stylé visuellement)
- Les **indications scéniques** (pauses, postures, intentions) sont en **italique grisé**
- Un **tableau de timing** sur la page d'intro rappelle la répartition minute par minute

**🆕 V2 — Questions d'introduction (à insérer entre OPA et SPIN-Situation)**

Objectif du bloc : avant de plonger dans la Situation factuelle, **comprendre où se situe l'interlocuteur dans l'organisation et ce qui l'anime/l'inquiète au quotidien**. C'est ce qui permettra de calibrer toute la suite du SPIN.

**Sous-bloc A — Reporting line (2 minutes, 3 questions)**

> 1. *"Pour bien me situer dans votre organisation : à qui rapportez-vous directement, et qui rapporte à vous aujourd'hui ?"*
>
> 2. *"Sur le périmètre que vous couvrez, qui sont les autres décisionnaires-clés avec qui vous travaillez en transverse — marketing, digital, IT, opérations, finance ?"*
>
> 3. *"Sur un projet comme celui dont nous allons parler, qui valide quoi ? Vous décidez seul·e du cadrage, ou ça remonte à un comex / sponsor ?"*

*Indication scénique : noter immédiatement le nom du N+1, le sponsor probable et la liste des co-décideurs — ce sera essentiel pour la suite (closing + post-call).*

**Sous-bloc B — Approfondissement challenges du moment (2 minutes, 4 questions)**

> 4. *"Si je vous demandais 'qu'est-ce qui occupe 80% de votre temps en ce moment ?', vous me répondriez quoi ?"*
>
> 5. *"Sur ces sujets, qu'est-ce qui marche bien — et qu'est-ce qui vous résiste vraiment ?"*
>
> 6. *"Quels sont les 2 ou 3 indicateurs que vous regardez chaque semaine, et lesquels ne vont pas dans le bon sens en ce moment ?"*
>
> 7. *"Quand vous présentez votre activité à votre N+1 / au comex, quelle est LA question qui revient à chaque fois et que vous redoutez un peu ?"*

*Indication scénique : la question 7 est la plus puissante — elle révèle le pain point politique du prospect. Laisser le silence faire son travail. Ne pas embrayer sur une solution avant 5 secondes de pause.*

**Articulation avec le SPIN :** les réponses à ces 7 questions d'introduction servent à **personnaliser en live** les questions Situation et Problème du SPIN. Si le prospect a déjà mentionné un challenge en intro, ne pas le re-poser — l'approfondir en Implications.

**Structure du script dans le docx :**

```
Page 2 — PRINCIPES DU CALL
  Bloc vert : Les 3 règles (80/20, écoute active, closing explicite)
  Tableau : Timing par section (Accueil 2' / OPA 3' / INTRO 4' / SPIN-S 5' / SPIN-P 6' / SPIN-I 5' / SPIN-N 3' / Closing 2')

Page 3 — ACCUEIL + OPA
  Verbatim exact d'ouverture (bloc citation)
  Pitch Haigo 20 secondes (bloc citation, à lire si et seulement si le prospect demande)
  Bloc OPA : Objectif / Plan / Accord — chacun en verbatim + question pour l'accord

Page 4 — 🆕 INTRODUCTION (V2)
  Sous-bloc A — Reporting line (3 questions)
  Sous-bloc B — Challenges du moment (4 questions)
  Espace de prise de notes large (organigramme à main levée + 3 challenges)

Pages 5–8 — SPIN (une section par page)
  S — Situation : 3–4 questions ouvertes numérotées, avec espace de notes
  P — Problème : 3–4 questions ouvertes, avec relances suggérées
  I — Implications : 3–4 questions ("qu'est-ce que ça coûte que X ne soit pas résolu ?")
  N — Need-payoff : 2–3 questions ("à quoi ressemblerait la réussite dans 12 mois ?")

Page 9 — CLOSING
  Verbatim de synthèse + proposition d'étape suivante
  3 options d'étape suivante (atelier 2h / Insight Sprint / second RDV + collègue)
```

**Personnalisation au prospect :** le script reste 80% standard, mais **3 points doivent être personnalisés** à partir de la note de contexte (phase 1) :
1. Une question "Situation" qui cite un **fait précis de l'actualité du prospect** ou **un article de la revue de presse** ("j'ai vu dans Les Échos la semaine dernière que vous avez annoncé X — comment est-ce que ça change votre roadmap CX ?")
2. Une question "Implication" qui relie un thème de leur earning call ou un buzz social à un enjeu CX
3. Le choix du case Haigo à garder "en chambre" pour la partie Closing (voir Annexe cases)

---

### Phase 3 — Annexes (4 annexes obligatoires)

Page 10 — **Annexe 1 — Signaux faibles à repérer pendant le call**
  Liste des mots/phrases du prospect qui trahissent un vrai pain point ("on a essayé en interne", "ça traîne depuis", "le board demande", etc.)

Page 11 — **Annexe 2 — Banque de cases Haigo (anti-sèche)**
  Tableau : Objection/Besoin prospect → Case Haigo pertinent → Chiffre-clé à citer
  Cases disponibles (voir section Haigo Case Bank plus bas)

Page 12 — **Annexe 3 — Traitement des 5 objections les plus fréquentes**
  Tableau : Objection → Réponse courte (verbatim) → Case à dégainer

Page 13 — **Annexe 4 — Post-call**
  Checklist : email de synthèse sous 24h, prochaine étape confirmée par écrit, création de la fiche HubSpot, tag nouveau prospect/existant, **mise à jour de l'organigramme client (reporting line capturée en intro)**

---

## Haigo Case Bank (à utiliser tel quel dans l'annexe 2)

| # | Client / Secteur | Problématique | Approche Haigo | Résultat clé |
|---|---|---|---|---|
| 1 | **Maison LVMH** (Luxe) | Refonte expérience flagship | Ethnographie + service design | Parcours store redesigné, +X% NPS |
| 2 | **L'Oréal** (Beauté) | Comprendre usages cross-canal | Étude qualitative + quantitative omnicanale | Roadmap CX 3 ans |
| 3 | **Assureur européen** | Repositionnement offre B2C | Insight Sprint 3 semaines | 3 territoires de marque testés |
| 4 | **Broker CFD / Trading** | Onboarding trop long, churn J+30 | CX Action Mapping | -30% churn onboarding |
| 5 | **Baromètre Omnicanal** (publication propriétaire Haigo) | Benchmark de marché | Étude quanti 2000+ répondants | Publication annuelle référencée |
| 6 | **Banque privée** | Digitalisation relation conseiller | Design Sprint 5 jours | 2 prototypes validés en 1 semaine |
| 7 | **Retailer alimentaire** | Expérience caisse / self-checkout | Observation terrain + co-design | Nouveau flow déployé en magasin |

*Note : Nicolas ajustera les chiffres exacts s'il les connaît mieux. Les chiffres flous type "+X%" sont des placeholders à remplir.*

---

## Les 3 offres Haigo (pour l'Accueil / pitch)

| Offre | Durée | Livrable | Quand la proposer |
|---|---|---|---|
| **Insight Sprint** | 3–4 semaines | Cartographie des insights clients actionnables | Prospect veut comprendre ses clients avant d'agir |
| **CX Action Mapping** | 4–6 semaines | Plan d'action priorisé sur le parcours client | Prospect a les insights mais pas de plan |
| **Design Sprint** | 5 jours | Prototype testé utilisateur | Prospect veut décider vite entre 2–3 options |

---

## Pitch Haigo — 3 formats (à utiliser dans Accueil)

**Format 20 sec** (défaut, pour ouvrir)
> "Haigo est une agence CX — 80 personnes chez Kyu depuis 2020. On aide nos clients à concevoir des services utiles, utilisables et désirables, en croisant recherche qualitative, data et design. LVMH, L'Oréal, grands assureurs."

**Format 40 sec** (si demandé "vous faites quoi exactement ?")
> "Haigo, c'est [XX] spécialistes CX à Paris, partie du groupe Kyu (Hakuhodo DY, 3 500 talents dans 14 pays) depuis 2020. On travaille sur 3 piliers : recherche qualitative — on va sur le terrain — analyses quantitatives, et design de services. Trois formats : Insight Sprint de 3 semaines, CX Action Mapping de 4 à 6 semaines, Design Sprint de 5 jours. On bosse avec LVMH, L'Oréal, des grands assureurs, des retailers."

**Format 60 sec** (si le prospect veut vraiment creuser)
> [Format 40 sec] + "Ce qui nous différencie, c'est qu'on ne livre pas des slides : on livre des prototypes testés utilisateur, des parcours cartographiés avec les chiffres derrière, et des plans d'action que vos équipes peuvent s'approprier. On a notre propre Baromètre Omnicanal qu'on publie chaque année, c'est un bon signal de notre rigueur."

---

## Traitement des 5 objections standard (Annexe 3)

| Objection prospect | Réponse courte (verbatim) | Case / chiffre |
|---|---|---|
| "On a déjà une agence" | "Très bien — on intervient souvent en complément, sur les phases de cadrage rapide. Je vous donne un exemple : chez [X], on est venus en amont de leur agence historique pour poser le terrain." | Case #2 ou #3 |
| "On le fait en interne" | "C'est la bonne approche sur le long terme. Notre valeur, c'est de vous faire gagner 2–3 mois sur le cadrage. Un Insight Sprint, c'est 3 semaines." | Case #4 (onboarding) |
| "C'est trop cher" | "Quel était l'ordre de grandeur que vous aviez en tête ? Un Insight Sprint démarre à [ordre de grandeur]. C'est souvent moins que le coût d'un trimestre sans insights." | — |
| "Pas le bon moment" | "Je comprends. Qu'est-ce qui rendrait le moment opportun ? Un trigger budget, un arbitrage, une échéance board ?" | — |
| "Envoyez-moi un deck" | "Je peux vous envoyer un onepager ciblé — plus utile qu'un deck générique. Sur quel enjeu je le cible ?" | — |

---

## Production du livrable — .docx

**Format de sortie : un seul fichier Word .docx** à sauvegarder dans le workspace folder de l'utilisateur.

**Outil recommandé :** `docx` (npm) en Node.js — permet un contrôle fin sur couleurs, encadrés, tableaux, blocs citation.

**Charte visuelle Haigo :**
- Bleu principal : `1F3A5F`
- Rouge accent : `B8322A`
- Gris foncé : `333333` · Gris moyen : `666666` · Gris clair : `E8E8E8`
- Vert (blocs OK) : `2E7D32`
- Fond jaune (encadrés verbatim prospect) : `FFF8DC`

**Rendu des éléments :**
- **Verbatim à dire par Nicolas** → bloc citation bleu sur fond gris clair, italique
- **Indications scéniques** (pauses, postures) → italique gris moyen, indenté
- **Questions numérotées** → chiffre en rouge, question en bold, espace de 3 lignes pour notes à la main
- **Tableaux** → entêtes bleu foncé, texte blanc, bordures fines
- **Encadrés principes** → fond vert très pâle, bordure verte, titre en vert foncé
- **🆕 V2 — Tableau revue de presse** → 5 colonnes (Date | Titre | Média | Lien | Résumé), entête bleu, lignes alternées gris clair, liens cliquables
- **🆕 V2 — Bloc social media** → encadré sur fond gris très clair, icône par plateforme si possible (LinkedIn, X, Reddit, TikTok)

**Nommage du fichier :**
`Brief_Call_[PrenomNom]_[Entreprise]_[YYYY-MM-DD].docx`
ex. `Brief_Call_AudreyMartin_AcmeCorp_2026-04-23.docx`

**Emplacement :** `/sessions/<session>/mnt/<workspace>/` (via `computer://` link).

---

## Workflow (à suivre)

1. **Extraire du prompt utilisateur** : Prénom+Nom, Fonction, Entreprise, Date du RDV (si fournie)
2. Si l'une de ces 3 infos manque (sauf la date), **demander avant de continuer** via AskUserQuestion
3. **Phase 1** — lancer les web searches en parallèle :
   - fiche identité
   - signaux presse 6 mois
   - **🆕 V2 : revue de presse 10 articles (5 FR + 5 international)** — requêtes ciblées par média
   - **🆕 V2 : monitoring social media** (LinkedIn, X, Reddit, TikTok selon pertinence)
   - earning calls si cotée
   - LinkedIn du contact (parcours + reporting line probable)
4. Rédiger la note de contexte (7 blocs en V2)
5. **Phase 2** — rédiger le script OPA + INTRODUCTION (reporting line + challenges) + SPIN, en personnalisant 3 points à partir de la note de contexte
6. **Phase 3** — rédiger les 4 annexes (cases, objections, signaux faibles, post-call enrichi avec capture organigramme)
7. Générer le .docx via Node.js + docx
8. Convertir en PDF pour QA visuel (via `scripts/office/soffice.py` ou `soffice --headless --convert-to pdf`)
9. Inspecter 2–3 pages au hasard pour vérifier qu'il n'y a pas de texte coupé, de blocs vides, de placeholder oublié, de **lien d'article cassé**
10. Livrer avec un lien `computer://` et une phrase de résumé (3–4 lignes max, sans post-amble lourd)

---

## Règles de ton et de style

- **Français professionnel, pas de jargon anglo-saxon inutile** (ok pour CX, NPS, B2B, sprint — pas ok pour "leverage", "pain point", "seamless")
- **Phrases courtes** dans les verbatim — le document doit se lire vite en RDV
- **Pas de flatterie vis-à-vis du prospect** — le script doit rester factuel et direct
- **Pas de "accent lines" sous les titres** (hallmark AI-généré — utiliser whitespace ou fond coloré)
- **Équilibrer densité et respiration** — marges 2cm minimum, espace entre blocs
- **Citer les sources** de la note de contexte, inline, avec URL ou référence courte
- **🆕 V2 — Liens de la revue de presse cliquables** dans le .docx (hyperlink Word, pas juste du texte)
- **🆕 V2 — Sentiment social media coloré** : vert (positif), gris (neutre), orange (polémique), rouge (négatif)
