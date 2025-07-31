Le protocole de transfert hypertexte (HTTP) est un protocole d'application pour les systèmes d'information hypermédia distribués et collaboratifs. HTTP est la base de la communication de données pour le World Wide Web, où les documents hypertextes incluent des hyperliens vers d'autres ressources auxquelles l'utilisateur peut facilement accéder, par exemple, en cliquant sur un bouton de souris ou en tapotant l'écran dans un navigateur web. HTTP a été développé pour soutenir la fonctionnalité hypertexte et la croissance du World Wide Web.
La fonction principale d'un serveur web est de stocker, traiter et fournir des pages web aux clients. La communication entre le client et le serveur s'effectue via le protocole de transfert hypertexte (HTTP). Les pages fournies sont le plus souvent des documents HTML, qui peuvent inclure des images, des feuilles de style et des scripts en plus du contenu textuel. Plusieurs serveurs web peuvent être utilisés pour un site web à fort trafic, répartissant le trafic entre plusieurs machines physiques.
Un agent utilisateur, généralement un navigateur web ou un robot d'indexation, initie la communication en demandant une ressource spécifique via HTTP, et le serveur répond avec le contenu de cette ressource ou un message d'erreur s'il ne peut pas le faire. La ressource est généralement un fichier réel sur le stockage du serveur ou le résultat d'un programme, mais ce n'est pas toujours le cas et peut en réalité être bien d'autres choses.
Bien que sa fonction principale soit de fournir du contenu, HTTP permet également aux clients d'envoyer des données. Cette fonctionnalité est utilisée pour soumettre des formulaires web, y compris le téléchargement de fichiers.

• Votre programme ne doit en aucun cas planter (même en cas de manque de mémoire) ou se terminer de manière inattendue. Si cela se produit, votre projet sera considéré comme non fonctionnel et votre note sera de 0.
• Vous devez soumettre un Makefile qui compile vos fichiers sources. Il ne doit pas effectuer de relinkage inutile.
• Votre Makefile doit au moins contenir les règles : $(NAME), all, clean, fclean et re.
• Compilez votre code avec c++ et les drapeaux -Wall -Wextra -Werror.
• Votre code doit respecter la norme C++ 98 et doit toujours se compiler en ajoutant le drapeau -std=c++98.
• Assurez-vous d'exploiter au maximum les fonctionnalités de C++ (par exemple, préférez <cstring> à &#x3C;string.h>). Vous êtes autorisé à utiliser des fonctions C, mais préférez toujours leurs versions C++ si possible.
• Toute bibliothèque externe et les bibliothèques Boost sont interdites.</cstring>

• **.ipp** : Fichier d'implémentation inline, généralement inclus dans un fichier d'en-tête (.h ou .hpp) pour contenir des définitions de fonctions inline ou de templates, séparant ainsi l'implémentation de la déclaration tout en évitant les fichiers .cpp supplémentaires.


• **Configuration files**: Fichiers texte (souvent .conf, .ini, .json, ou .yaml) définissant les paramètres du serveur web, comme les ports, les chemins des répertoires, les règles de routage, les types MIME, ou les configurations de virtual hosts. Pour "webserv", un fichier .conf est typique, inspiré des formats comme nginx.conf.



Voici les définitions des fonctions externes autorisées pour le projet "webserv", en respectant leur utilisation dans un contexte C++ 98. Chaque fonction est expliquée brièvement et clairement.

• **execve**: Exécute un programme en remplaçant le processus actuel par un nouveau, avec un tableau d'arguments et un environnement spécifié.
• **pipe**: Crée un tube (pipe) pour la communication inter-processus, permettant à un processus d'écrire des données qu'un autre peut lire.
• **strerror**: Retourne une chaîne de caractères décrivant l'erreur correspondant au code d'erreur stocké dans errno.
• **gai_strerror**: Retourne une chaîne décrivant une erreur spécifique issue des fonctions de résolution d'adresses réseau comme getaddrinfo.
• **errno**: Variable globale contenant le code de la dernière erreur survenue lors d'un appel système.
• **dup**: Duplique un descripteur de fichier, créant un nouveau descripteur pointant vers le même fichier.
• **dup2**: Duplique un descripteur de fichier vers un descripteur spécifique, fermant ce dernier s'il est déjà ouvert.
• **fork**: Crée un nouveau processus en dupliquant le processus appelant, retournant le PID du fils au parent et 0 au fils.
• **socketpair**: Crée une paire de sockets connectés pour la communication bidirectionnelle entre deux processus.
• **htons**: Convertit un entier court (16 bits) de l'ordre hôte (host) vers l'ordre réseau (network, big-endian).
• **htonl**: Convertit un entier long (32 bits) de l'ordre hôte vers l'ordre réseau.
• **ntohs**: Convertit un entier court de l'ordre réseau vers l'ordre hôte.
• **ntohl**: Convertit un entier long de l'ordre réseau vers l'ordre hôte.
• **select**: Surveille plusieurs descripteurs de fichiers pour détecter des événements (lecture, écriture, erreur) avec un timeout.
• **poll**: Similaire à select, mais surveille des descripteurs de fichiers avec une structure plus efficace pour gérer les événements.
• **epoll_create**: Crée une instance epoll pour surveiller efficacement un grand nombre de descripteurs de fichiers (Linux).
• **epoll_ctl**: Modifie (ajoute, supprime, met à jour) les descripteurs surveillés dans une instance epoll.
• **epoll_wait**: Attend les événements sur les descripteurs surveillés par une instance epoll, avec un timeout.
• **kqueue**: Crée une file d'événements pour surveiller des descripteurs de fichiers ou autres ressources (BSD/macOS).
• **kevent**: Enregistre ou récupère des événements dans une file kqueue, gérant des changements ou des notifications.
• **socket**: Crée un socket pour la communication réseau, spécifiant le domaine (IPv4/IPv6), le type et le protocole.
• **accept**: Accepte une connexion entrante sur un socket en écoute, créant un nouveau socket pour la communication.
• **listen**: Met un socket en mode écoute, prêt à accepter des connexions entrantes avec une file d'attente.
• **send**: Envoie des données via un socket connecté.
• **recv**: Reçoit des données depuis un socket connecté.
• **chdir**: Change le répertoire de travail courant du processus.
• **bind**: Associe un socket à une adresse locale (IP et port).
• **connect**: Établit une connexion entre un socket et une adresse distante.
• **getaddrinfo**: Résout un nom d'hôte et un service en une liste d'adresses réseau utilisables.
• **freeaddrinfo**: Libère la mémoire allouée par getaddrinfo.
• **setsockopt**: Configure les options d'un socket, comme le mode non bloquant ou la réutilisation d'adresses.
• **getsockname**: Récupère l'adresse locale associée à un socket.
• **getprotobyname**: Récupère les informations sur un protocole réseau à partir de son nom (par exemple, "tcp").
• **fcntl**: Manipule les propriétés d'un descripteur de fichier, comme le mode non bloquant.
• **close**: Ferme un descripteur de fichier ou un socket.
• **read**: Lit des données depuis un descripteur de fichier ou un socket.
• **write**: Écrit des données vers un descripteur de fichier ou un socket.
• **waitpid**: Attend la terminaison d'un processus fils spécifique, récupérant son statut.
• **kill**: Envoie un signal à un processus ou un groupe de processus.
• **signal**: Configure un gestionnaire pour un signal spécifique (par exemple, SIGINT).
• **access**: Vérifie les permissions d'accès à un fichier pour l'utilisateur courant.
• **stat**: Récupère les métadonnées d'un fichier, comme sa taille ou ses permissions.
• **open**: Ouvre un fichier, retournant un descripteur de fichier.
• **opendir**: Ouvre un répertoire pour la lecture.
• **readdir**: Lit une entrée dans un répertoire ouvert.
• **closedir**: Ferme un répertoire précédemment ouvert.


Vous devez écrire un serveur HTTP en C++ 98.

Votre exécutable doit être exécuté comme suit : ./webserv [fichier de configuration]

Bien que poll() soit mentionné dans le sujet et la grille d'évaluation,

vous pouvez utiliser une fonction équivalente telle que select(), kqueue() ou epoll().

Veuillez lire les RFC définissant le protocole HTTP et effectuer des tests avec telnet et NGINX avant de commencer ce projet. Bien que vous ne soyez pas tenu d'implémenter l'ensemble des RFC, leur lecture vous aidera à développer les fonctionnalités requises. La version HTTP 1.0 est suggérée comme point de référence, mais n'est pas imposée.

III.1 Exigences

Votre programme doit utiliser un fichier de configuration, fourni en argument sur la ligne de commande ou disponible dans un chemin par défaut.
Vous ne pouvez pas utiliser execve pour exécuter un autre serveur web.
Votre serveur doit rester non bloquant à tout moment et gérer correctement les déconnexions des clients lorsque nécessaire.
Il doit être non bloquant et utiliser un seul appel à poll() (ou équivalent) pour toutes les opérations d'entrée/sortie entre les clients et le serveur (y compris listen).
poll() (ou équivalent) doit surveiller simultanément la lecture et l'écriture.
Vous ne devez jamais effectuer une opération de lecture ou d'écriture sans passer par poll() (ou équivalent).
Vérifier la valeur de errno pour ajuster le comportement du serveur après une opération de lecture ou d'écriture est strictement interdit.
Vous n'êtes pas tenu d'utiliser poll() (ou équivalent) avant un read() pour récupérer votre fichier de configuration.

Comme vous devez utiliser des descripteurs de fichiers non bloquants, il est possible d'utiliser les fonctions read/recv ou write/send sans poll() (ou équivalent), et votre serveur ne serait pas bloquant. Cependant, cela consommerait plus de ressources système. Ainsi, si vous tentez de lire (read/recv) ou d'écrire (write/send) sur un descripteur de fichier sans utiliser poll() (ou équivalent), votre note sera de 0.

Lors de l'utilisation de poll() ou d'un équivalent, vous pouvez utiliser toutes les macros ou fonctions associées (par exemple, FD_SET pour select()).
Une requête à votre serveur ne doit jamais rester bloquée indéfiniment.
Votre serveur doit être compatible avec les navigateurs web standards de votre choix.
NGINX peut être utilisé pour comparer les en-têtes et les comportements des réponses (attention aux différences entre les versions HTTP).
Les codes de statut de réponse HTTP de votre serveur doivent être précis.
Votre serveur doit avoir des pages d'erreur par défaut si aucune n'est fournie.
Vous ne pouvez pas utiliser fork pour autre chose que les CGI (comme PHP, Python, etc.).
Vous devez être capable de servir un site web entièrement statique.
Les clients doivent pouvoir téléverser des fichiers.
Vous devez implémenter au minimum les méthodes GET, POST et DELETE.
Testez la robustesse de votre serveur pour garantir qu'il reste disponible à tout moment.
Votre serveur doit pouvoir écouter plusieurs ports pour fournir différents contenus (voir fichier de configuration).

Nous avons délibérément choisi de n'offrir qu'un sous-ensemble des RFC HTTP. Dans ce contexte, la fonctionnalité d'hôte virtuel est considérée hors champ. Cependant, vous êtes libre de l'implémenter si vous le souhaitez.


III.2 Pour macOS uniquement

Puisque macOS gère write() différemment des autres systèmes d'exploitation basés sur Unix, vous êtes autorisé à utiliser fcntl().

Vous devez utiliser des descripteurs de fichiers en mode non bloquant pour obtenir un comportement similaire à celui des autres systèmes Unix.

Cependant, vous ne pouvez utiliser fcntl() qu'avec les drapeaux suivants :

F_SETFL, O_NONBLOCK et FD_CLOEXEC.

Tout autre drapeau est interdit.
III.3 Fichier de configuration

Vous pouvez vous inspirer de la section server du fichier de configuration de NGINX.

Dans le fichier de configuration, vous devez pouvoir :

Définir toutes les paires interface:port sur lesquelles votre serveur écoutera (permettant de définir plusieurs sites web servis par votre programme).
Configurer des pages d'erreur par défaut.
Définir la taille maximale autorisée pour le corps des requêtes des clients.
Spécifier des règles ou configurations pour une URL/route (aucune expression régulière requise ici) pour un site web, parmi les suivantes :

Liste des méthodes HTTP acceptées pour la route.
Redirection HTTP.
Répertoire où le fichier requis doit être recherché (par exemple, si l'URL /kapouet est mappée à /tmp/www, l'URL /kapouet/pouic/toto/pouet cherchera /tmp/www/pouic/toto/pouet).
Activer ou désactiver l'affichage du contenu des répertoires.
Fichier par défaut à servir lorsque la ressource demandée est un répertoire.
Autoriser le téléversement de fichiers des clients vers le serveur, avec un emplacement de stockage spécifié.

Exécution de CGI, basée sur l'extension de fichier (par exemple, .php). Voici quelques remarques spécifiques concernant les CGI :

Vous vous demandez ce qu'est un CGI ?
Examinez attentivement les variables d'environnement impliquées dans la communication entre le serveur web et le CGI. La requête complète et les arguments fournis par le client doivent être disponibles pour le CGI.
Pour les requêtes en mode chunked, votre serveur doit les déchunker ; le CGI s'attendra à un EOF pour marquer la fin du corps de la requête.
Il en va de même pour la sortie du CGI : si aucun content_length n'est retourné par le CGI, un EOF marquera la fin des données renvoyées.
Le CGI doit être exécuté dans le répertoire correct pour permettre l'accès aux fichiers via des chemins relatifs.
Votre serveur doit prendre en charge au moins un CGI (php-CGI, Python, etc.).


Vous devez fournir des fichiers de configuration et des fichiers par défaut pour tester et démontrer que toutes les fonctionnalités fonctionnent lors de l'évaluation.
Vous pouvez inclure d'autres règles ou informations de configuration dans votre fichier (par exemple, un nom de serveur pour un site web si vous prévoyez d'implémenter des hôtes virtuels).
Si vous avez une question sur un comportement spécifique, vous pouvez comparer le comportement de votre programme avec celui de NGINX.
Nous avons fourni un petit testeur. Son utilisation n'est pas obligatoire si tout fonctionne correctement avec votre navigateur et vos tests, mais il peut vous aider à trouver et corriger des bugs.
La résilience est essentielle. Votre serveur doit rester opérationnel à tout moment.
Ne testez pas avec un seul programme. Écrivez vos tests dans un langage plus adapté, comme Python ou Golang, ou même en C ou C++ si vous préférez.