# TikTok Studio - charte de production

Tout ce qui est produit ici (script, storyboard, animation, son, rendu) respecte cette charte.
Elle passe avant toute autre préférence. En cas de doute : demander, ne pas improviser.

## Règles absolues

1. **Aucune génération sans feu vert.** Ne lancer ni voix ElevenLabs, ni rendu vidéo, ni génération d'image tant que l'utilisateur n'a pas dit « go » pour cette vidéo.
2. **Aucune modification du script sans prévenir.** Un script validé est figé. Toute retouche (même une virgule, une balise, un timing) est proposée sous forme de diff avec la raison, et attend un oui.
3. **Contrôle qualité avant de montrer quoi que ce soit.** Rien n'est présenté à l'utilisateur sans être passé par l'agent `controle-qualite` avec un verdict « OK ». Un seul point bloquant = on corrige d'abord.
4. **Itérer vite.** Prévisualisations courtes (scène par scène, basse résolution) avant le rendu final 1080x1920.

## Format

- Vertical 9:16, 1080x1920, 30 ou 60 fps.
- Zones sûres TikTok : ne rien placer d'important dans les 220 px du bas (légende, nom), les 120 px du haut, ni dans la colonne droite x > 900 entre y 700 et y 1500 (boutons), **sauf** le CTA d'abonnement qui vise volontairement ce bouton.
- **Rythme accéléré, toujours.** Voix accélérée de 1.15x à 1.25x avec hauteur préservée (time-stretch, pas de voix aiguë), blancs internes resserrés. Aucun plan fixe de plus de 1.5 s sans mouvement.

## Direction artistique

**Le motion design est poussé au maximum.** Chaque élément à l'écran entre, vit et sort en mouvement.

À faire :
- Palette restreinte : 1 couleur de fond profonde, 1 couleur d'accent, 1 neutre clair, plus leurs nuances. Look pro, éditorial, sobre et riche à la fois.
- **Fonds travaillés** : dégradés profonds, grain ou bruit léger, texture, vignettage, profondeur (flous, couches en parallaxe), lumière volumétrique discrète. Jamais un aplat uni.
- Objets avec **ombres, bords, matière, reflets** : volume, éclairage cohérent, éléments 3D ou pseudo-3D.
- **Toutes les infographies animées** : chiffres qui comptent, graphes qui se construisent, icônes qui se morphent. Les illustrations sont animées autant que possible.
- **Transformations** : un objet qui se change en un autre, un objet qui se dissout en particules qui reforment autre chose, des morphings de formes.
- **Transitions entre assets** (match cut, morph, masque, zoom à travers un objet).
- **Caméra** : mouvements fluides entre les plans (easing doux, motion blur), parfois des plans en 3D ou de la parallaxe. **Fin en dézoom** qui révèle l'ensemble des plans comme une carte (« workmap »).
- Des assets complémentaires remplissent vite les espaces vides et dynamisent l'image.

Interdit (refusé d'office au contrôle qualité) :
- Dessins enfantins, style Roblox, cartoon naïf, bonshommes simplistes.
- Couleurs nombreuses ou criardes, look « clown ».
- Aplats sans ombre, sans bord ni texture ; formes basiques sans finition.
- Fonds complètement unis.
- **Slop IA** : encarts avec traits colorés en blend, lignes ou traits volants sans signification, glows arc-en-ciel gratuits, particules décoratives qui ne racontent rien.
- Éléments statiques, ou animés par un simple fondu.

## Sources

Affichées en petit, police discrète (sans-serif fine, environ 22-26 px en 1080p, opacité 60-70 %), texte court (« INSEE, 2024 », pas d'URL complète), dans un coin hors zones de boutons.

## Abonnement

- **Rappel discret** : petite notification ou popup « Abonne-toi », placée dans un moment creux de la narration (respiration, fin d'idée), **tôt dans la vidéo** (vers 6-12 s, jamais dans le dernier tiers), avec un son court et satisfaisant (pop, ding doux, clic).
- **CTA ambitieux à partir de 20 s** : séquence motion design forte autour du bouton d'abonnement TikTok (le « + » sous l'avatar, colonne de droite). Une **flèche placée au-dessus du bouton pointe vers le bas**. Comme la position varie selon les téléphones, la flèche est longue et sa pointe vise la zone x 940-1030, y 1000-1250, avec halo ou pulsation sur toute cette zone. Ce placement est à vérifier sur des captures d'écran de plusieurs modèles.

## Son

- Utiliser en priorité **la bibliothèque de sons motion fournie** (`assets/sfx/`) : whoosh, pop, clic, glitch, riser. Ne pas en créer si un son existant convient.
- S'il manque un type de son, **le signaler à l'utilisateur** avec la liste précise de ce qu'il faut.
- Mixage : voix au premier plan, SFX calés à l'image près sur les animations, musique en ducking sous la voix.

## Script ElevenLabs

- Écrit pour **ElevenLabs** (modèle à confirmer par l'utilisateur, « v4 ») avec des **balises d'audio** entre crochets, par exemple `[confident]`, `[excited]`, `[curious]`, `[serious]`, `[short pause]`.
- **Pas de `[sighs]` ni de `[whispers]`**, sauf si c'est vraiment justifié par le sens, et dans ce cas on le signale.
- **Narration cohérente et continue** : une seule voix, un seul ton de fond, aucune coupure audible. Le script est accompagné des conseils pour obtenir cet effet (voir l'agent `scenariste`).
