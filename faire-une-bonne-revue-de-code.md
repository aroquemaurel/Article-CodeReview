On va essayer de voir de quelle manière il est possible de mettre de la revue de code dans un projet, et surtout qu'elle se passe le mieux possible. 

# Les outils

Il est très utile de s'outiller pour effectuer de bonnes revues de code. C'est nécessaire principalement pour gagner du temps, mais aussi pour améliorer la qualité globale du code.

## La revue de code : Github, Gitlab et Bitbucket 

La revue de code est globalement plus simple sur des outils modernes tel que Git, car ils permettent de créer facilement une branche, il est alors aisé de faire relire notre branche. Je connais principalement des outils pour Git que je vais vous présenter ici, ce sont les plus connus. 

[[information]] Pour d'autres systèmes tel que SVN, CVS, Mercurial, bazaar etc. vous pouvez regarder du côté de [Phabricator](https://www.phacility.com/), [Review board](https://www.reviewboard.org/) ou [Crucible](https://fr.atlassian.com/software/crucible). Il en existe d'autres mais je ne les connais pas, un peu de recherche et vous devriez trouver votre bonheur. ;)

Ces trois outils sont assez similaires en terme d'utilisation. Ils sont uniquement prévus pour Git. La principale différence vient du coût et du buisiness model: 

- [Github](https://github.com/) n'est gratuit que si le projet est open source, sinon il faut payer pour un nombre de dépôt fermé. 
- [Gitlab](https://gitlab.com/) permet d'installer une version communautaire, cela demandera un peu d'administration système et un serveur à disposition. Ils proposent également une version *Entreprise Edition* permettant d'utiliser leurs serveurs
- [Bitbucket](https://bitbucket.org/) fait partie de la suite Atlassian, il a donc une bonne intégration avec leurs outils tel que Jira

Le système est assez similaire. Le développeur va coder sa fonctionnalité ou corriger son bug sur une branche Git. Une fois qu'il estime avoir terminé son travail et qu'il souhaite une relecture, il peut ouvrir une Pull Request (Github et Bitbucket) ou une Merge request (Gitlab). À ce moment là, un sujet de discussion est ouvert contenant la différence de code, et un espace commentaire. Il est alors possible de commenter le code, ou de mettre des commentaires plus généraux. 

## L'analyse statique : Sonar

Pour l'analyse statique, cela dépendra complètement de la technologie du projet. L'idée étant de faire une « pré-relecture » par un outil, afin de voir en amont certains bugs possibles ou de non respects de conventions de codage.

Personnellement, j'ai l'habitude d'utiliser Sonar. Sonar permet de brancher d'ajouter plusieurs plugins, il est alors possible de vérifier la qualité statique du code, la duplication de code, le taux de couverture des tests unitaires, du code mort, ...  Lorsqu'un développeur envoie ces modifications de code, une analyse sonar à lieu, et il ajoute éventuellement des commentaires directement sur la Pull Request. Cela permet de gagner du temps en effectuant une première relecture. C'est une aide précieuse !

## L'intégration continue : Jenkins, Travis-CI, Gitlab-CI

Il est également possible de brancher un système d'intégration continue à nos Pull Request. Ainsi, avant qu'une personne relise le code, l'outil est passé et à vérifie certaines actions. Les actions les plus basiques étant de vérifier que le code compile, et que les test unitaires passent. C'est cet outil qui est chargé de lancer l'analyse statique. C'est un peu le chef d'orchestre de tous les outils utilisé avant la revue de code. Cela permet de gagner du temps et d'éviter d'éventuelles régressions. 

# Une bonne revue de code, c'est un effort collectif

Pour qu'une revue de code se passe bien, il faut être en bonne condition. Aussi bien du côté de l'entreprise, que de l'auteur d'une revue que de la personne qui relit le code. 

## Faire des petites revues

Pour qu'une revue de code se passe bien pour tout le monde, et surtout pour qu'elle soit le plus efficace possible, il faut essayer qu'elle soit les plus petites possibles. Il n'est agréable pour personne d'avoir 10000 lignes de code à relire. 

- L'auteur à envie que son travail soit intégré rapidement, et sera réfractaire aux modifications. 
- Le relecteur n'a pas envie de tout relire, il va aller au plus rapide

Tout le monde est globalement épuisé. La relecture ne sera pas efficace. Il faut donc essayer de faire au maximum des petites tâches qui sont intégrés sur une branche de développement au fur et à mesure. 

## Anticiper les revues sur le planning

Si une deadline est proche, la revue de code va être précipité. Elle va être bâclée, et si des modifications ou du refactoring devait avoir lieu, il risque de ne pas être fait, et de provoquer de la dette technique. Globalement, une revue de code, ça se prévoit, il est donc préférable de prévoir un peu de temps pour la relecture d'une part, et les aller-retours d'autre part. 

## Être dans le bon état d'esprit

Ici, il s'agit d'un problème totalement naturel et humain. Il faut accepter que son travail soit analysé, et éventuellement critiqué. 

- Que ça soit du côté de l'auteur du code, qui doit accepter les critiques, et essayer de les prendre en compte si possible.
- Ou du relecteur, qui doit savoir argumenter son avis, et présenter les choses de manières à tirer l'autre développeur vers le haut.

De manière générale, que ça soit l'auteur de la revue ou le relecteur, les deux personnes doivent avoir une attitude positive.

![[Commit Strip](https://www.commitstrip.com/fr/2015/02/10/the-truth-about-code-reviews/)](images/Strip.jpg)