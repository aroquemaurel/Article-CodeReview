Si vous avez déjà travaillé à plusieurs sur un projet logiciel plus ou moins conséquent, vous avez certainement dû être confronté à au moins un de ces problèmes :

- Une dette technique difficilement rattrapable
- Du code incompréhensible 
- Des bugs qui auraient dû être vus avant la livraison
- Toute la connaissance technique du projet porté par une seule personne

Une des solutions pour limiter ce genre de problème, c'est la revue de code. Voyons un peu son intérêt et ce que ça peut apporter dans un projet logiciel. :)

[[information]]
| Je parle de limiter les problèmes, la revue de code ne s'oppose pas à des tests automatisés ou une bonne gestion de projet bien entendu. 

Pour commencer, une petit définition de la revue de code sur Wikipédia : 

> La **revue de code** (de l'anglais *code review*) est un examen systématique du [code source](https://fr.wikipedia.org/wiki/Code_source) d'un logiciel. 
>
> Il peut être comparé au processus ayant lieu dans un [comité de lecture](https://fr.wikipedia.org/wiki/Comit%C3%A9_de_lecture), l'objectif étant de trouver des [bugs](https://fr.wikipedia.org/wiki/Bug_informatique)  ou des vulnérabilités potentielles ou de corriger des erreurs de  conception afin d'améliorer la qualité, la maintenabilité et la sécurité  du logiciel. 
>
> Source: https://fr.wikipedia.org/wiki/Revue_de_code

Le principe est assez simple, un autre regard sur notre travail est assez bénéfique. Chaque développeur, et plus généralement chaque personne, a une façon différente de penser et d’appréhender un problème. Un autre regard peut donc amener une autre approche. 

La revue de code se fait de plus en plus régulièrement dans des entreprises de différentes tailles, aussi bien dans des petites startup de quelques développeurs que dans des mastodontes tel que le [Google](https://www.quora.com/What-is-Googles-internal-code-review-policy-process) ou le projet [Linux](https://github.com/torvalds/linux/pulls). 

Une revue fait donc intervenir au moins deux personnes, une personne qui soumet le code, que j’appellerai « l'auteur », et une ou plusieurs personne qui relit le code, le « relecteur ». 

# Qui peut relire le code

Il y a deux écoles, les deux ont pour moi leurs avantages et leurs inconvénients. 

Un développeur expérimenté, tel que le *lead dev* va relire l'ensemble du code de l'équipe. Ce développeur ayant la meilleure connaissance de l'application et du métier, il sera plus à même de relire le code de l'équipe. L'inconvénient est que la connaissance de l'application restera au sein de la même personne, si un jour ce développeur est absent ce sera dommageable pour le projet. 

Il est également possible de faire tourner le relecteur, chaque personne sera amené à lire le code d'un autre développeur. Le gros avantage est de responsabiliser le développeur, et de faire monter en compétence l'ensemble de l'équipe, cela permet également de partager la connaissance du projet. Cette solution peut-être plus difficile à mettre en place. Si le projet est conséquent chaque développeur n'a pas toujours une vision assez globale du projet pour relire efficacement le code de quelqu'un d'autre. De plus, la relecture de code n'est pas quelque chose de simple. Un bon développeur peut avoir du mal à se plonger dans le code de quelqu'un d'autre. Il sera donc nécessaire de faire monter l'équipe en compétence.

Ces deux approches ne sont pas forcément exclusive. Il est aussi possible d'avoir d'abord une relecture par un autre développeur, et que ça soit le *lead dev* qui valide l'intégration. Cela permet  de combiner les deux avantages, en revanche, cela va prendre plus de temps, en raison d'une double validation. 

# Comment faire une revue de code

Il y a plusieurs manières d'aborder une revue de code, et celle-ci dépends principalement du contexte du projet et de la culture de l'entreprise. Lorsque le développeur estime avoir terminé le changement, il peut demander une relecture. Voici plusieurs manières pour effectuer cette relecture : 

- Les Pull ou Merge requests : ce sont des méthodes très utilisés dans le monde du libre notamment au travers de [Github](https://github.com/) ou [Gitlab](https://gitlab.com/). Un développeur envoie ses changements, et une autre personne valide, et intègre le moment venu. 
- « Analyse par-dessus l'épaule » : Deux personnes sont devant l'ordinateur, l'auteur commente son code, et la seconde personne donne éventuellement des conseils ou pose des questions.
- La revue de code par mail : c'est un technique qui avait court avant la démocratisation des outils plus modernes tel que Github, il est possible de faire une simple liste de diffusion, et de s'envoyer des patchs par mail. La relecture se faisant directement par retours de mails.

À ce stage, vous êtes peut-être en train de vous dire que ça semble une bonne idée, mais que ça va prendre beaucoup de temps et d'énergie. Je ne peux pas vous contredire sur ce point. Bien que le temps de la revue soit variable d'un développeur à l'autre, oui, ça peut être long si on met bout à bout les revues. Mais je pense que le temps passé est contrebalancé par les avantages. À long terme, cela permettra d'avoir un projet plus maintenable, avec une équipe efficace. 

# On écrit du code lisible et propre

Quand un projet se met à la revue de code, c'est souvent le premier objectif : avoir un code plus lisible et globalement de meilleur qualité. Et en effet, ça marche.

L'auteur va s'obliger à relire son propre code, il va donc ajouter des commentaires, et tout faire pour qu'il soit le plus compréhensible possible pour que la revue de code se passe bien. 

Si le code est intégré, cela veut dire qu'au moins deux personnes ont estimés que le code était lisible et élégant. On peut extrapoler un peu et se dire que si deux personnes de l'équipe le valident, le reste de l'équipe devrait également le comprendre sans difficultés. 

Un second regard à l’application permet de limiter la duplication de code grâce à une deuxième vision. « J'avais codé *ça* pour un autre module, on doit pouvoir le réutiliser plutôt que réinventer la roue ! ». 

# On limite les bugs

Le relecteur ne va pas forcément tester le code, mais va avoir un œil extérieur, contrairement à l'auteur qui était plongé dans son code, ainsi il va : 

- Penser à des cas limites que le développeur aurai pu oublier
- Certains bugs sont visibles uniquement en lisant le code. Même un développeur relisant son propre code pourrait voir d'éventuels problèmes, de la même manière qu'un auteur doit relire son papier avant de le soumettre. La revue de code oblige l'équipe à avoir cette approche.
- Deux personnes comprendront plus facilement le besoin à la source du changement. Il peut arriver que le développeur ai mal compris, une deuxième personne pourra voir le problème avant intégration.

Le relecteur peut suggérer l'ajout de tests unitaires pour des cas qui n'auraient pas été prévus initialement. C'est un bon moyen de vérifier que le patch est fonctionnel, et que les cas limites sont correctement gérés, tout en améliorant la qualité des tests. 

# On apprend

Ce n'est pas forcément le premier avantage auquel on pense, mais de mon expérience la revue de code permet d'apprendre. Que ça soit pour l'auteur, ou pour le relecteur (principalement dans le cas ou les relecteurs « tournent »).

- Le relecteur peut tomber sur quelque chose d'inconnu : « Oh, tiens ! Je ne connais pas ça ? Comment ça marche ». L'auteur va ainsi expliquer ce qu'il a fait, et en quoi il estime que c'est avantageux. 
- Mais on peut avoir l'effet inverse : « Tu pourrai utiliser cette technique, c'est plus optimisé / élégant / efficace ! » 

On peut aussi apprendre sur des questions métiers, où des questions d'architecture de notre application. Ces échanges sont toujours bénéfiques.

# On enrichit la documentation

La revue de code est le meilleur moment pour poser des questions. Lorsqu'un non-expert est relecteur, il peut poser des questions sur un aspect qu'il ne comprends pas. Cela ne veut pas forcément dire qu'il y a un problème. Par contre, cela veut dire qu'il y a du passage de connaissance nécessaire.

C'est une bonne occasion pour améliorer l'existant. Cela peut être des commentaires manquants, où plus globalement un problème de documentation, ça peut-être le bon moment pour améliorer cette documentation, ce qui pourra ensuite profiter à toute l'équipe.

# On communique

Ça peut paraître assez basique. Mais le simple fait d'avoir une revue de code va obliger l'équipe à communiquer. Expliquer ce que chacun a fait, comment. Justifier les différents choix.

Une revue de code est l'occasion rêvée pour poser des questions, y répondre, de discuter.

# On peut former les nouveaux 

La revue de code est déjà souvent utilisé pour les nouveaux développeurs. Mais avoir une revue de code systématique pour l'ensemble de l'équipe permet au nouveau de se sentir complètement intégré à l'équipe : il est dans les même *process*.

Elle est d'autant plus importante pour lui, car il ne connaît ni l'application ni le métier. C'est une bonne occasion pour lui faire des remarques, lui expliquer des choses, lui montrer les bonnes méthodes limitant la duplication de code. D'une entreprise à l'autre, les approches peuvent être différentes, il est donc important de lui transmettre les habitudes de l'équipe.

Une fois qu'il aura bien appréhendé le projet, le fait de relire le code de développeurs plus expérimenté lui permettra d'apprendre de nouvelles choses et de prendre confiance en lui.

On va essayer de voir de quelle manière il est possible de mettre en place de la revue de code dans un projet, et surtout qu'elle se passe le mieux possible. 

# Les outils

Il est très utile de s'outiller pour effectuer de bonnes revues de code. C'est nécessaire principalement pour gagner du temps, mais aussi pour améliorer la qualité des revues. 

## La revue de code : Github, Gitlab et Bitbucket 

La revue de code est globalement plus simple avec un système de versionnement moderne tel que Git, car ils permettent de créer facilement une branche, il est alors aisé de faire relire notre branche. Je connais principalement des outils pour Git que je vais vous présenter ici, ce sont les plus connus. 

[[information]]
| Pour d'autres systèmes tel que SVN, CVS, Mercurial, bazaar etc. vous pouvez regarder du   côté de [Phabricator](https://www.phacility.com/), [Review board](https://www.reviewboard.org/) ou [Crucible](https://fr.atlassian.com/software/crucible). 
|
| Il en existe d'autres mais je ne les connais pas, un peu de recherche et vous devriez trouver votre bonheur. ;)

Ces outils permettent principalement d'avoir un fonctionnement *asynchrone* : le développeur propose son code, et le relecteur peut le relire un peu plus tard. Il n'est pas nécessaire d'avoir les deux personnes disponibles en même temps, comme ça peut-être le cas avec la méthode « d'analyse par-dessus l'épaule » par exemple.

Ces trois outils sont assez similaires en terme d'utilisation. Ils sont uniquement prévus pour Git. La principale différence vient du coût et du buisiness model: 

- [Github](https://github.com/), très connu et utilisé dans le monde du libre. Il n'est gratuit que si le projet est open source, sinon il faut payer pour un nombre de dépôt fermé. 
- [Gitlab](https://gitlab.com/), est un projet libre similaire à Github, il permet d'installer une version communautaire. Cela demandera un peu d'administration système et un serveur à disposition. Ils proposent également une version *Entreprise Edition* permettant d'utiliser leurs serveurs
- [Bitbucket](https://bitbucket.org/) fait partie de la suite Atlassian, il a donc une bonne intégration avec leurs outils tel que Jira

Le développeur va coder sa fonctionnalité ou corriger son bug sur une branche Git. Une fois qu'il estime avoir terminé son travail et qu'il souhaite une relecture, il peut ouvrir une Pull Request (Github et Bitbucket) ou une Merge request (Gitlab). À ce moment là, un sujet de discussion est ouvert contenant la différence de code, et un espace commentaire. Il est alors possible d'ajouter un commentaire dans le code, ou de mettre des commentaires plus généraux. 

![Exemple de Pull Request sur Github](/media/galleries/5520/d9894a55-e740-487f-b8e0-90ce6db71c14.png)
Figure: Exemple de Pull Request sur Github

## Les outils d'intégration continue 

Il est possible de lier l'outil de revue de code à un outil d'intégration continue. Il faut voir ça comme un complément à une bonne revue. Des outils permettent d'effectuer une vérification automatique, et un humain va faire une revue permettant d'améliorer significativement la qualité du projet comme nous l'avons vu précédemment.

Cet outil peut effectuer plusieurs actions, tel que : 

- Compiler le projet
- Lancer les tests automatisés (unitaires, de non-régression, de performance, ...)
- Calculer le taux de couverture des tests
- Effectuer une analyse statique, l'idée est de faire une « relecture » du code par un outil qui va appliquer une « checklist » interne, afin de voir en amont certains bugs possibles ou de non respects de conventions de codage[^sonar]
- Générer la documentation

Il existe une multitude d'outils d'intégration continue. Les plus connus sont [Jenkins](https://jenkins.io/), [Gitlab-CI](https://gitlab.com/gitlab-ci) et [Travis-CI](https://travis-ci.org/). Ceux-ci sont capable de mettre des commentaires directement dans la revue de code.

[^sonar]: Pour l'analyse statique, l'outil dépends de la technologie utilisée. Un des plus connus multi-langage est [SonarLint](https://www.sonarlint.org/).

# Une bonne revue de code, c'est un effort collectif

Pour qu'une revue de code se passe bien, il faut être en bonne condition. Aussi bien du côté de l'auteur que du relecteur.

## Faire des petites revues

Pour que ça se passe bien pour tout le monde, et surtout pour qu'elle soit le plus efficace possible, il faut faire des petites revues. Il n'est agréable pour personne d'avoir 10 000 lignes de code à relire. 

- L'auteur à envie que son travail soit intégré rapidement, et sera réfractaire aux modifications. 
- Le relecteur n'a pas envie de tout relire, il va aller au plus vite

Tout le monde est globalement épuisé. La relecture ne sera pas efficace. Il faut donc essayer de faire au maximum des petites tâches qui sont intégrés sur une branche de développement au fur et à mesure. 

## Anticiper les revues sur le planning

Si une deadline est proche, la revue de code va être précipitée. Elle risque d'être bâclée, et si des modifications ou du refactoring devrait avoir lieu, il risque de ne pas être fait, et de provoquer de la dette technique. Globalement, une revue de code, ça se prévoit, il est donc préférable de prendre en compte le temps de relecture d'une part, et les allers-retours d'autre part. 

## Être dans le bon état d'esprit

Ici, il s'agit d'un problème plus humain : il faut accepter que son travail soit analysé, et éventuellement critiqué. 

- Que ça soit du côté de l'auteur, qui doit accepter les critiques, et essayer de les prendre en compte si possible.
- Ou du relecteur, qui ne doit pas avoir peur de donner des remarques sur le travail de son collègue. Mais surtout, il doit argumenter son avis, et présenter les choses de manières à tirer le développeur vers le haut. 

Une bonne revue doit susciter des échanges, des discussions, des remises en question.

De manière générale, que ça soit l'auteur ou le relecteur, les deux personnes doivent avoir une attitude positive.

![Commit Strip revue de code](/media/galleries/5520/114a976c-cf5c-4633-9a4e-a65077621462.jpg)
Figure: [Commit Strip revue de code](https://www.commitstrip.com/fr/2015/02/10/the-truth-about-code-reviews/)- On apprends (celui qui relit, et celui qui fait relire)
- Limite les bugs (quatre yeux vallent mieux que deux)
- Etre outillé (asynchrone => Pull/merge requests)
- Faire des « petites » revues de code régulières
- etre bienveillant
- Séparer les responsabilités (problème => deux personnes au lieu d'une)Merci d'avoir lu jusqu'au bout ! Il ne reste plus qu'à essayer de mettre en place de la revue de code dans vos projets. 

Je sais que j'ai été dans un monde idéal : on revoit systématiquement l'ensemble du code. Ce n'est pas toujours évident, surtout pour les *bug fix* qui doivent être corrigés rapidement. Il est toujours possible de commencer à faire un peu de revue sur les nouveaux développements, et essayer d'étendre le périmètre vers les corrections de bugs, pour finalement arriver à 100% de revue de code ! 

Et surtout, n'oubliez pas :

- Restez positifs 
- Faites de petites revues
- Prévoyez les revues
- Les outils peuvent effectuer un travail complémentaire