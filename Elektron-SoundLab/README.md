# Elektron SoundLab v3.1

Application HTML autonome pour inventorier, écouter et préparer des sons destinés à l'Elektron Analog Four MKI / Analog Keys et au Digitone MK1.

## Lancer

Ouvrir `index.html` dans un navigateur Chromium récent (Chrome ou Edge). Pour Web MIDI/SysEx et la capture audio, privilégier une origine `localhost` ; voir `docs/INSTALLATION.md`.

## Capacités

- Import de `.afsnd`, `.dnsnd`, `.syx`, projets `.afprj` / `.dnprj`, audio et archives ZIP.
- Lecture audio locale et visualisation de waveform.
- Préécoute synthétique proxy des formats natifs. **Ce n'est pas une émulation fidèle du moteur Elektron** et les paramètres propriétaires ne sont pas décodés.
- Liaison manuelle d'un enregistrement réel à un patch, capture depuis une entrée audio et export de capture.
- Analyse de messages SysEx, détection conservatrice de fabricant, note MIDI de test et envoi avec confirmation.
- Inventaire JSON, favoris, filtres et navigation séquentielle.

## Limites importantes

- Le protocole USB-MIDI natif utilisé par Elektron Transfer pour les fichiers `.afsnd` / `.dnsnd` n'est pas implémenté ici. Ces fichiers ne sont jamais envoyés comme SysEx brut.
- L'envoi SysEx indique uniquement une mise en file côté navigateur, pas la réception ni l'écriture confirmée sur la machine.
- Les projets et firmwares ne sont pas transférés.
- Les paramètres propriétaires et les sons ne sont pas décodés au niveau DSP.

## Sécurité

Avant tout transfert SysEx, sauvegarder la destination et configurer explicitement la machine pour recevoir le dump. Ne transférer que des messages dont l'origine, l'appareil cible et la destination sont connus.

## Licence et marques

Le code de l'application est distribué sous licence MIT (voir `LICENSE`). Elektron et les noms de produits cités sont des marques de leurs titulaires respectifs. Ce projet est indépendant et non affilié à Elektron.

## Structure

- `index.html` : application autonome (HTML/CSS/JavaScript, sans build requis).
- `docs/` : guide utilisateur et notes techniques.
- `scripts/` : lanceurs Windows optionnels.
