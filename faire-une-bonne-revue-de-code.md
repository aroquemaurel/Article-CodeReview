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
Figure: [Commit Strip revue de code](https://www.commitstrip.com/fr/2015/02/10/the-truth-about-code-reviews/)