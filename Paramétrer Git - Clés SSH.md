# Paramétrage de base pour Git et génération des clés SSH

## Pré-requis

---

* Compte utilisateur actif sur Github
* Git & Git Bash sont installés (voir Ressources)

## Ressources

---

* [Installation de Git et de Git Bash sous Windows](https://git-scm.com/downloads)

## Marche à suivre

---

Dans Git Bash, exécuter ces deux commandes l’une après l’autre :

`git config --global user.name "Ton nom utilisateur"`

`git config --global user.email "Ton email Github"`

Exécuter ensuite la commande suivante, en remplaçant email@exemple.com par l’email utilisé dans le compte Github :

`ssh-keygen -t ed25519 -C "email@exemple.com"`

Cette commande va permettre de générer la paire de clé publique / privée SSH nécessaire à Git. Pour le chemin d’accès, laisser celui proposé par défaut (recommandé) ou en saisir un autre (attention sous Windows, les \ deviennent des /).
La passphrase est une sorte de mot de passe utilisé pour renforcer la sécurité des clés. Pas obligatoire en formation, mais fortement recommandé dans le milieu professionnel (quelqu’un qui arrive à obtenir votre clé privée devra également connaître la passphrase).
Pour ne pas indiquer de passphrase, appuyer sur la touche *Entrée*.

Exemple de retour de commande :

~~~
Generating public/private ed25519 key pair.
Enter file in which to save the key (/c/Users/Guillaume/.ssh/id_ed25519):
Created directory '/c/Users/Guillaume/.ssh'.
Enter passphrase (empty for no passphrase):
Enter same passphrase again:
Your identification has been saved in /c/Users/Guillaume/.ssh/id_ed25519
Your public key has been saved in /c/Users/Guillaume/.ssh/id_ed25519.pub
The key fingerprint is:
SHA256:3z6EOxPo5AdzSgc36Vb1SfZiGknSocvapkuNznn5rwo gmasquelier@gmail.com
The key's randomart image is:
+--[ED25519 256]--+
|                 |
|            . .o |
|           + oo.o|
|        . * + ..o|
|        S* B o . |
|        *+X.+ o  |
|       =oXo*.=   |
|       +=.X.+ .  |
|        ** +oo   |
+----[SHA256]-----+
~~~

La paire de clé publique / privée a été enregistrée dans le répertoire choisi (ici `/c/Users/Guillaume/.ssh`). La clé publique porte l'extension .pub. La clé privée ne comporte pas d’extension.

**Très important : la clé privée doit rester… privée ! Personne d’autre que toi ne doit la connaître, tu ne dois donc pas la transmettre à un tiers. Seule la clé publique peut être librement distribuée.**

## Pour aller plus loin

---

Un cours OpenClassrooms est disponible pour en savoir plus sur les clés et l’authentification : https://openclassrooms.com/fr/courses/7274161-administrez-un-systeme-linux/7529351-connectez-vous-a-distance-avec-ssh

## Crédits

---

Rédigé par Guillaume Masquelier ([Github](https://github.com/gmasquelier59))