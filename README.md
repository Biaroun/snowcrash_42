<div align="center">
  <img src="https://upload.wikimedia.org/wikipedia/commons/8/8d/42_Logo.svg" alt="42 logo" width="120"/>
  <h1>snowcrash_42</h1>
  <p>Projet cybersécurité 42 : progression CTF Linux autour de failles locales et escalade de privilèges</p>

  <p>
    <img src="https://img.shields.io/badge/Project-SnowCrash-1f6feb?logo=hackthebox&logoColor=white" alt="SnowCrash"/>
    <img src="https://img.shields.io/badge/Domain-Cybersecurity-bd2c00?logo=securityscorecard&logoColor=white" alt="Cybersecurity"/>
    <img src="https://img.shields.io/badge/Focus-Privilege%20Escalation-6f42c1?logo=gnu-bash&logoColor=white" alt="Privilege Escalation"/>
    <img src="https://img.shields.io/badge/Levels-00%20to%2014-2da44e?logo=probot&logoColor=white" alt="Levels"/>
    <img src="https://img.shields.io/badge/School-42-black?logo=42&logoColor=white" alt="42"/>
  </p>
</div>

---

## 📚 Description

`snowcrash_42` est un dépôt de progression du projet SnowCrash de 42.

Le projet regroupe 15 niveaux (`level00` à `level14`) avec, pour chacun :

- un fichier **flag** (preuve de validation du niveau)
- un dossier **ressources/** avec l’analyse et la méthode d’exploitation

Les writeups couvrent des vulnérabilités classiques :

- mauvaises permissions / exposition d’informations
- injection de commandes (Perl, PHP, Lua, CGI)
- détournement d’exécution via variable d’environnement (`PATH`, `LOGNAME`)
- race condition de type TOCTOU
- contournement de contrôles logiques via debugging (`gdb`)

---

## 🗂️ Architecture

- `level00/` à `level14/` : un dossier par niveau
- `levelXX/flag` : token récupéré pour passer au niveau suivant
- `levelXX/ressources/README.md` : explication détaillée (ou `readme.md` / `explanation.md` selon le niveau)

---

## ⚙️ Lancement

### Prérequis

- Environnement SnowCrash 42 accessible (VM ou machine du projet)
- Outils Linux classiques (`find`, `cat`, `grep`, `curl`, `nc`, `gdb`, `ltrace`)

### Utiliser le dépôt

```bash
cd levelXX
```

Puis consulter le writeup correspondant :

```bash
cat ressources/README.md
```

Selon les niveaux, le document peut être nommé :

- `README.md`
- `readme.md`
- `explanation.md`

---

## 🧪 Progression (résumé)

- `level00` : récupération d’un secret chiffré en ROT
- `level01` : extraction d’un hash depuis `/etc/passwd` et cassage avec John
- `level02` : analyse PCAP/Telnet et reconstruction avec backspaces
- `level03` : hijack d’exécutable via `PATH`
- `level04` : injection commande via CGI Perl
- `level05` : exécution différée via script système
- `level06` : code execution via `preg_replace /e` (PHP)
- `level07` : injection shell via variable d’environnement
- `level08` : bypass d’un filtre nom de fichier via symlink
- `level09` : inversion d’un chiffrement positionnel
- `level10` : exploitation TOCTOU avec `access()` / `open()`
- `level11` : injection de commande dans serveur Lua
- `level12` : command injection Perl avec contournement d’entrée
- `level13` : contournement de vérification UID via `gdb`
- `level14` : patch runtime de `getuid()` dans `getflag`

---

## 🔐 Notes de sécurité

- Les flags ne sont pas exposés dans ce README.
- Ce dépôt est destiné à un usage pédagogique sur environnement dédié.
- Ne pas reproduire ces techniques hors cadre autorisé.

---

## 🛠️ Outils principalement utilisés

- `find`, `grep`, `cat`, `strings`
- `john`, `tcpdump` / Wireshark
- `curl`, `nc` (netcat)
- `ltrace`, `gdb`

---

## 👤 Auteur

- `biaroun` — 42

---

## 📄 Licence

Projet académique 42.
Usage pédagogique et personnel.
