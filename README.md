# LAB-14-Bypass-Root-Detection-sur-Android-Techniques-Dynamiques-avec-Frida-Objection-et-Hooks-Natif
markdown_content = """# LAB-14 : Contournement de la détection Root Android avec Frida, Objection et Hooks natifs

> **Avertissement de sécurité :** Ce lab est réalisé dans un environnement contrôlé à des fins strictement pédagogiques. L'application cible appartient à la famille OWASP UnCrackable.

## 📝 Contexte et Objectifs
Ce lab va un cran plus loin que les précédents : on ne se contente plus d'un simple bypass Java ou d'une commande automatisée sous Objection. Nous allons combiner les deux approches, ajouter des **hooks natifs**, et tracer les appels système pour comprendre ce que l'application fait réellement sous le capot.

L'application cible reste la même — **OWASP UnCrackable Level 1** — mais cette fois, nous l'attaquons méthodiquement, couche par couche (Java puis C/C++), pour identifier précisément les blocages et la manière de les contourner.

---

## 🛠️ Environnement de Travail

| Élément | Détail / Spécification |
| :--- | :--- |
| **Système** | Windows (PowerShell) |
| **Émulateur** | Android Emulator 5554 |
| **Frida** | Version 17.8.0 |
| **Objection** | Version 1.12.4 |
| **OS Cible** | Android 11 |
| **Package Cible** | `owasp.mstg.uncrackable1` |

---

## 📂 Structure du projet

Voici l'arborescence des scripts que nous allons utiliser pour ce lab :
