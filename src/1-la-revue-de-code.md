Pour commencer, une petite définition de la revue de code tirée de Wikipédia : 

> La **revue de code** (de l'anglais *code review*) est un examen systématique du [code source](https://fr.wikipedia.org/wiki/Code_source) d'un logiciel. 
>
> Il peut être comparé au processus ayant lieu dans un [comité de lecture](https://fr.wikipedia.org/wiki/Comit%C3%A9_de_lecture), l'objectif étant de trouver des [bugs](https://fr.wikipedia.org/wiki/Bug_informatique)  ou des vulnérabilités potentielles ou de corriger des erreurs de  conception afin d'améliorer la qualité, la maintenabilité et la sécurité  du logiciel. 
>
> Source: https://fr.wikipedia.org/wiki/Revue_de_code

Le principe est assez simple : un autre regard sur notre travail est assez bénéfique. Chaque développeur, et plus généralement chaque personne, a une façon différente de penser et d’appréhender un problème. Un autre regard peut donc amener une autre approche. 

La revue de code se fait de plus en plus régulièrement dans des entreprises de différentes tailles, aussi bien dans des petites *startups* de quelques développeurs que dans des mastodontes tel que [Google](https://www.quora.com/What-is-Googles-internal-code-review-policy-process) ou le projet [Linux](https://github.com/torvalds/linux/pulls). 

Une revue fait donc intervenir au moins deux personnes, une personne qui soumet le code, que j’appellerai « l'auteur », et une ou plusieurs personne qui relit le code, le « relecteur ». 

# Qui peut relire le code

Il y a deux écoles, les deux ont pour moi leurs avantages et leurs inconvénients. 

Un développeur expérimenté, tel que le *lead dev* va relire l'ensemble du code de l'équipe. Ce développeur ayant la meilleure connaissance de l'application et du métier, il sera plus à même de relire le code de l'équipe. L'inconvénient est que la connaissance de l'application restera au sein de la même personne, si un jour ce développeur est absent ce sera dommageable pour le projet. 

Il est également possible de faire tourner le relecteur, chaque personne sera amené à lire le code d'un autre développeur. Le gros avantage est de responsabiliser le développeur, et de faire monter en compétence l'ensemble de l'équipe, cela permet également de partager la connaissance du projet. Toutefois, cette solution peut être plus difficile à mettre en place. En effet, si le projet est conséquent, chaque développeur n'a pas toujours une vision assez globale du projet pour relire efficacement le code de quelqu'un d'autre. De plus, la relecture de code n'est pas quelque chose de simple, un bon développeur peut avoir du mal à se plonger dans le code de quelqu'un d'autre. Il sera donc nécessaire de faire monter l'équipe en compétence.

Ces deux approches ne sont pas forcément exclusives. Il est aussi possible d'avoir d'abord une relecture par un autre développeur, et que ça soit le *lead dev* qui valide l'intégration. Cela permet  de combiner les deux avantages, en revanche, cela va prendre plus de temps, en raison d'une double validation. 

# Comment faire une revue de code

Il y a plusieurs manières d'aborder une revue de code. Celle-ci dépend principalement du contexte du projet et de la culture de l'entreprise. Lorsque le développeur estime avoir terminé le changement, il peut demander une relecture. Voici plusieurs manières pour effectuer cette relecture : 

- Les *pull* ou *merge requests* : ce sont des méthodes très utilisées dans le monde du libre notamment au travers de [Github](https://github.com/) ou [Gitlab](https://gitlab.com/). Un développeur envoie ses changements et une autre personne valide et intègre le moment venu. 
- « Analyse par-dessus l'épaule » : deux personnes sont devant l'ordinateur, l'auteur commente son code et la seconde personne donne éventuellement des conseils ou pose des questions.
- La revue de code par *mail* : c'est une technique qui avait court avant la démocratisation des outils plus modernes tel que Github, il est possible de faire une simple liste de diffusion et de s'envoyer des *patchs* par *mail*. La relecture se faisant directement par retours de *mails*.