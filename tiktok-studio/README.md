# TikTok Studio

Pipeline de création de vidéos TikTok verticales avec des sous-agents Claude Code. Ouvrir Claude Code **dans ce dossier** pour charger `CLAUDE.md` (la charte) et `.claude/agents/`.

## Flux
1. `scenariste` -> `scripts/<slug>.md` (brouillon) -> **validation par toi** (STATUT: VALIDÉ, figé ensuite)
2. `directeur-motion` + `sound-designer` -> `storyboards/<slug>.md` -> `controle-qualite` -> **validation par toi**
3. **Feu vert de génération** -> voix ElevenLabs (par toi ou via API) -> `motion-designer` scène par scène -> `controle-qualite` -> rendu `renders/`

## À fournir
- `assets/sfx/` : ta bibliothèque de sons motion
- la voix ElevenLabs (voice id) et la version du modèle
- palette et polices de ta marque, si tu en as
