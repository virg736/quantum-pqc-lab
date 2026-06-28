<p align="center">
  <img src="quantum-pqc-lab.jpeg" alt="Quantum-PQC-Lab" width="700">
</p>

<h1 align="center">Quantum-PQC-Lab</h1>

<p align="center">
  <strong>Laboratoire de cybersécurité post-quantique - aperçu public</strong>
</p>

<p align="center">
  Debian Server · Parrot Security · VirtualBox · TLS · OpenSSL · oqs-provider · Qiskit
</p>


---

## Aperçu public du projet

Quantum-PQC-Lab est un laboratoire pédagogique et technique autour de la cybersécurité post-quantique.

Ce dépôt public présente uniquement un aperçu du projet : objectif, architecture générale, environnement de test et état d’avancement.

La version complète du laboratoire contient les configurations détaillées, les scripts, les tests TLS, les captures réseau, les notebooks Qiskit et les supports pédagogiques.

---

## Objectif du projet

L’objectif est de créer un laboratoire reproductible afin de démontrer concrètement :

- les limites réelles des ordinateurs quantiques actuels ;
- les impacts possibles sur RSA et ECC ;
- les différences entre cryptographie classique et cryptographie post-quantique ;
- les ordres de grandeur liés aux algorithmes de Shor et Grover ;
- les mécanismes actuels de transition vers la cryptographie post-quantique ;
- le risque dit **Store Now, Decrypt Later**.

Le projet vise à vulgariser le sujet sans sensationnalisme, tout en s’appuyant sur des mécanismes techniques réels.

Ce dépôt public présente une version de démonstration. La version complète est destinée aux formations professionnelles, aux écoles d’ingénieurs, aux accompagnements encadrés et aux usages professionnels.

--- 

## Architecture générale du laboratoire

| Élément | Rôle | Services / outils | Objectifs |
|---|---|---|---|
| Machine hôte | Virtualisation | VirtualBox, 16 Go de RAM recommandés, 4 vCPU minimum, 80 Go de disque | Héberger les machines virtuelles du laboratoire |
| VM 1 - Debian Server | Serveur TLS | Nginx ou Apache, OpenSSL 3, liboqs, oqs-provider | Générer des certificats classiques et PQC, tester TLS classique et TLS hybride post-quantique, mesurer les impacts techniques |
| VM 2 - Parrot Security | Client de test et d’analyse | Wireshark, tcpdump, testssl.sh, openSSL client, nmap | Capturer les handshakes TLS, comparer RSA/ECC avec Kyber, observer les tailles de paquets et étudier les échanges réseau |
| VM 3 -  Qiskit Lab | Simulation pédagogique d’algorithmes quantiques | Python, Jupyter Notebook, Qiskit | Simuler Grover, simuler Shor sur de petits nombres, illustrer les contraintes quantiques réelles et les limites actuelles du hardware |

---

### Capture - structure du projet Debian

Cette capture montre la structure locale du projet créée sous Debian, ainsi que la validation de l’accès à Internet depuis la machine virtuelle.

![Structure du projet Debian](debian-structure-projet.png)

---

## État d’avancement

Éléments déjà validés dans l’environnement de test :

- Debian installé et mis à jour ;
- Parrot Security installé et mis à jour ;
- accès à Internet validé sous Debian ;
- accès à Internet validé sous Parrot ;
- structure locale du projet créée sous Debian ;
- Nginx installé sous Debian ;
- Nginx actif sous Debian ;
- serveur HTTP Debian validé en local ;
- netcat-openbsd installé sous Parrot ;
- Configuration réseau VirtualBox validée ;
- choix final : adaptateur 1 en réseau interne, adaptateur 2 en NAT.

---

### Capture - nginx actif sous Debian

Cette capture montre que le service Nginx est installé, lancé et actif sur la machine Debian Server.

![Nginx actif sous Debian](debian-nginx-actif.png)

## Aperçu réseau

La configuration réseau repose sur deux interfaces par machine virtuelle :

- une interface en réseau interne pour les échanges entre Debian et Parrot ;
- une interface NAT pour conserver l’accès Internet.

Cette configuration permet de construire un laboratoire isolé tout en gardant la possibilité d’installer les dépendances nécessaires.

---

### Capture - port 80 ouvert sous Debian

Cette capture montre que Nginx écoute bien sur le port HTTP 80.

![Port 80 ouvert sur Debian](debian-port-80-ouvert.png)


## Captures d’écran

Les captures disponibles dans ce dépôt montrent uniquement une partie de la configuration :

- aperçu de la configuration réseau VirtualBox ;
- validation de connectivité ;
- structure du projet sur Debian ;
- nginx actif sur Debian ;
- port HTTP ouvert sur le serveur Debian.

---

## Contenu non inclus dans cette version publique

La version publique ne contient pas :

- les scripts complets ;
- les commandes avancées OpenSSL ;
- la configuration complète oqs-provider ;
- les certificats ;
- les tests TLS complets ;
- les captures Wireshark détaillées ;
- les benchmarks ;
- les notebooks Qiskit complets ;
- les exercices ;
- les corrections ;
- les supports de formation.

---

## Version complète

La version complète du laboratoire comprend :

- configuration complète VirtualBox ;
- configuration Debian Server ;
- configuration Parrot Security ;
- OpenSSL 3 ;
- liboqs ;
- oqs-provider ;
- comparaison TLS classique / TLS post-quantique ;
- démonstration TLS hybride ;
- captures réseau Wireshark ;
- scripts de benchmark ;
- simulations des algorithmes de Shor et de Grover ;
- documentation complète ;
- supports de formation.

> 🔒 **Accès réservé**  
> La version complète du laboratoire est réservée aux formations professionnelles, aux écoles d’ingénieurs et aux accompagnements encadrés.

---

## Finalité du projet

Quantum-PQC-Lab a pour objectif de produire :

- un laboratoire reproductible ;
- un support pédagogique ;
- un portfolio en cybersécurité ;
- une base de démonstration post-quantique ;
- une série de contenus techniques documentés pour GitHub, LinkedIn et la formation professionnelle.

---

## Accès complet

> 🔒 **Accès réservé**  
> La version complète du laboratoire est réservée aux formations professionnelles, aux écoles d’ingénieurs et aux accompagnements encadrés.

Pour obtenir plus d’informations sur la version complète du laboratoire, organiser une formation ou échanger autour d’une collaboration professionnelle :

**Virginie Lechene**  
Contact : `virginielechene@proton.me`

---

## Lexique

| Terme | Signification |
|---|---|
| **PQC** | Post-Quantum Cryptography, ou cryptographie post-quantique. Elle désigne les algorithmes conçus pour résister aux attaques d’ordinateurs quantiques. |
| **RSA** | Algorithme de cryptographie classique utilisé notamment pour le chiffrement et la signature numérique. |
| **ECC** | Elliptic Curve Cryptography. Cryptographie basée sur les courbes elliptiques, très utilisée aujourd’hui pour TLS, signatures et échanges de clés. |
| **TLS** | Protocole qui sécurise les communications sur Internet, par exemple entre un navigateur et un serveur web. |
| **TLS hybride** | Mode de transition combinant cryptographie classique et cryptographie post-quantique. |
| **OpenSSL** | Bibliothèque logicielle utilisée pour gérer TLS, certificats, clés et fonctions cryptographiques. |
| **liboqs** | Bibliothèque open source dédiée aux algorithmes de cryptographie post-quantique. |
| **oqs-provider** | Fournisseur OpenSSL permettant d’intégrer des algorithmes post-quantiques dans OpenSSL 3. |
| **Kyber** | Algorithme post-quantique d'encapsulation de clés, utilisé pour protéger les échanges de clés. |
| **Qiskit** | Framework Python permettant de créer etde simuler des circuits quantiques. |
| **Shor** | Algorithme quantique théorique capable de factoriser de grands nombres, ce qui menace RSA si des ordinateurs quantiques suffisamment puissants existent. |
| **Grover** | Algorithme quantique qui accélère certaines recherches, avec un impact notamment sur la taille de sécurité des clés symétriques. |
| **Store Now, Decrypt Later** | Stratégie consistant à stocker aujourd’hui des données chiffrées pour tenter de les déchiffrer plus tard avec de meilleures capacités, notamment quantiques. |
| **Wireshark** | Outil d’analyse réseau permettant de capturer et observer les paquets échangés. |
| **VirtualBox** | Logiciel de virtualisation permettant de créer et d'exécuter plusieurs machines virtuelles. |
| **Debian Server** | Machine virtuelle utilisée comme serveur TLS dans le laboratoire. |
| **Parrot Security** | Distribution Linux orientée cybersécurité utilisée ici comme client de test et d’analyse. |

---

## Droits d’auteur

© Virginie Lechene. Tous droits réservés.

Ce dépôt est fourni uniquement comme aperçu public.  
Toute copie, redistribution, revente ou réutilisation sans autorisation est interdite.
