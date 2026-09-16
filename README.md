# TP_web_github_Quentin_ROSOLI : Morris

Le ver **Morris** ou ver de Morris était un ver informatique distribué via l'Internet, écrit par Robert Tappan Morris (à l'époque étudiant à l'université Cornell), et lancé le 2 novembre 1988 à partir du MIT. Il est considéré comme le **premier ver** et est certainement le premier à avoir attiré l'attention des médias de masse. Il a aussi mené à la première condamnation en vertu du Computer Fraud and Abuse Act de 1986

## Architecture

>Le ver Morris ne fut pas écrit pour causer des dommages mais pour se propager. Des erreurs dans le code l'ont toutefois rendu plus dangereux : un ordinateur pouvait être infecté plus d'une fois et chaque processus additionnel ralentissait la machine au point de la rendre inutilisable.

Le ver Morris exploitait deux vulnérabilités connues dans sendmail, fingerd, et dans la faiblesse de mots de passe de certains utilisateurs. La faille de sendmail se situait dans la possibilité, en mode DEBUG, d'envoyer des fichiers sur une machine distante en utilisant un shell. Ce shell était utilisé pour compiler le code source envoyé. Ce programme une fois compilé était alors en mesure de tenter de se propager à d'autres machines. La deuxième faille utilisée était un dépassement de tampon de l'utilitaire finger initialement conçu pour connaître à distance l'heure de connexion d'un utilisateur sur un poste. Ce bug permettait au ver de prendre le contrôle et d'utiliser les accès réseau de l'utilitaire pour se connecter à des machines distantes, et d'y migrer comme avec sendmail. Enfin, la troisième technique de propagation profitait des mots de passe faibles des utilisateurs des systèmes infectés : le ver tentait de deviner les mots de passe des utilisateurs à l'aide de dictionnaires, et lorsqu'il trouvait le bon, se copiait sur des machines distantes avec les commandes rsh et rexec.

Lorsque le ver parvenait à une nouvelle machine, il se divisait, effaçait les fichiers qui le contenaient pour ne laisser aucune trace, et une fois sur quinze, envoyait un octet à la machine 128.32.137.13 (ernie.berkeley.edu) de l'université de Berkeley, comme message de bon fonctionnement, ou pour détourner les soupçons.

Même s'il ne pouvait infecter que des machines VAX exécutant les systèmes 4 BSD et Sun 3, le ver Morris s'est propagé à une vitesse qui ne semblait pas avoir été prévue par son auteur. La charge processeur qu'il nécessitait a alors provoqué des dénis de service, que ce soit en matière de performances, et même d'accès (le nombre de processus du ver sur une machine empêchait tout nouveau processus, donc toute connexion d'un utilisateur).


## Défenses


>Une des défenses les plus simples contre ce ver était la création du répertoire /usr/tmp/sh. En effet, le ver utilisait le fichier sh du répertoire /usr/tmp/ pour se propager, et était bloqué lorsque ce chemin était déjà utilisé.

La faille de sendmail nécessitait de patcher l'application pour supprimer l'option DEBUG, celle de finger pouvait être corrigée en le modifiant légèrement, ce qui rendait caduque l'attaque par dépassement de tampon.

Certains systèmes infectés durent se déconnecter du réseau pour se mettre en quarantaine, d'autres se déconnectèrent pour éviter d'être infectés.



## Conséquences

>Il est souvent rapporté qu'environ six mille machines Unix furent infectées par le ver Morris. Le programmeur Paul Graham a affirmé : « J'étais là quand (ce chiffre) a été inventé, et ce qui suit fut la recette : quelqu'un a estimé qu'il y avait environ soixante mille ordinateurs connectés à l'Internet, et que le ver pourrait en avoir infecté dix pour cent. » Le Government Accountability Office, une agence du Congrès américain, a évalué les dommages à une somme de dix à cent millions de dollars américains. Robert Morris a subi un procès et fut condamné pour avoir violé le Computer Fraud and Abuse Act de 1986. Après être allé en appel, il reçut une sentence de trois ans de probation, quatre cents heures de travaux communautaires, et une amende de plus de dix mille dollars.

Le Computer Emergency Response Team (CERT) fut créé en réaction au ver Morris.

Le ver Morris a parfois été appelé le « Grand ver » (Great Worm) à cause de l'effet dévastateur qu'il avait eu sur l'Internet à cette époque, autant pour les pannes causées que pour l'impact psychologique qu'il a eu sur la perception qu'on avait de la sécurité et de la fiabilité de l'Internet. Ce nom dérive des Great Worms de Tolkien, nommés Scatha et Glaurung.
