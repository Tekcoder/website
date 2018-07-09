---
title: "Installer Jupyterhub"
date: 2018-06-19T16:47:44+02:00
draft: true
---

* Ubuntu 16.04
* CUDA 9.2
* cuDNN 7.1.4
* Dépendances TF
* Anaconda 3 dans /usr/local/anaconda3
* Clone TF 1.8
* Compil TF (Python 3.6 par défaut)
* Build package TF
* sudo visudo. Add /usr/local/anaconda3/bin at end of secure_path
* sudo pip install tensorflow*.whl

* conda install -c conda-forge jupyterhub
* pip install oauthenticator
* jupyterhub --generate-config /etc/jupyterhub/
* Modif fichier config
<https://github.com/jupyterhub/jupyterhub/wiki/Run-jupyterhub-as-a-system-service>
* sudo systmectl enable jupyterhub pour le lancer au démarrage
* ssh-keygen -t rsa
* SSL : chaine certificats
* Zone DNS

* sudo pip install keras
<https://stackoverflow.com/a/48214084/2380880>
