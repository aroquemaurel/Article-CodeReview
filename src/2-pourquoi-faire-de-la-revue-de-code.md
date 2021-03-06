À ce stade, vous êtes peut-être en train de vous dire que ça semble une bonne idée, mais que ça va prendre beaucoup de temps et d'énergie. Je ne peux pas vous contredire sur ce point. Bien que le temps de la revue soit variable d'un développeur à l'autre, oui, ça peut être long. Mais je pense que le temps passé est contrebalancé par les avantages. À long terme, cela permettra d'avoir un projet plus maintenable, avec une équipe efficace. 

# On écrit du code lisible et propre

Quand un projet se met à la revue de code, c'est souvent le premier objectif : avoir un code plus lisible et globalement de meilleure qualité. Et en effet, ça marche.

L'auteur va s'obliger à relire son propre code, il va donc ajouter des commentaires et tout faire pour qu'il soit le plus compréhensible possible pour que la revue de code se passe bien. 

Si le code est intégré, cela veut dire qu'au moins deux personnes ont estimé que le code était lisible et élégant. On peut extrapoler un peu et se dire que si deux personnes de l'équipe le valident, le reste de l'équipe devrait également le comprendre sans difficulté. 

Par ailleurs, un second regard à l’application permet de limiter la duplication de code grâce à une deuxième vision. « J'avais codé *ça* pour un autre module, on doit pouvoir le réutiliser plutôt que réinventer la roue ! ». 

# On limite les *bugs*

Le relecteur ne va pas forcément tester le code, mais va avoir un œil extérieur, contrairement à l’auteur qui était plongé dans son code. Le relecteur peut ainsi :

- identifier certains *bugs* en lisant le code, tel que des cas limites que le développeur aurait pu oublier ou des problèmes d'implémentation ;
- constater une mauvaise compréhension du besoin à la source du changement ;

Le relecteur peut suggérer l'ajout de tests unitaires pour des cas qui n'auraient pas été prévus initialement. C'est un bon moyen de vérifier que le patch est fonctionnel, et que les cas limites sont correctement gérés, tout en améliorant la qualité des tests. 

# On apprend

Ce n'est pas forcément la première chose à laquelle on pense quand on parle de revue de code, mais de mon expérience la revue de code permet d'apprendre. Que ce soit pour l'auteur ou pour le relecteur (principalement dans le cas où les relecteurs « tournent »).

- Le relecteur peut tomber sur quelque chose d'inconnu : « oh, tiens ! Je ne connais pas ça ? Comment ça marche ? » L'auteur va ainsi expliquer ce qu'il a fait et en quoi il estime que c'est avantageux. 
- Mais on peut avoir l'effet inverse : « tu pourrais utiliser cette technique, c'est plus optimisé / élégant / efficace ! » 

On peut aussi apprendre sur des questions de métiers ou des questions d'architecture de notre application. Ces échanges sont toujours bénéfiques. 

# On enrichit la documentation

La revue de code est le meilleur moment pour poser des questions. Lorsqu'un non-expert est relecteur, il peut poser des questions sur un aspect qu'il ne comprend pas. Cela ne veut pas forcément dire qu'il y a un problème. Par contre, cela veut dire qu'il y a du passage de connaissance à effectuer.

C'est une bonne occasion pour améliorer l'existant. Cela peut venir de commentaires manquants ou plus globalement d'un problème de documentation. C'est alors le bon moment pour améliorer cette documentation, ce qui pourra ensuite profiter à toute l'équipe.

# On communique

Ça peut paraître assez basique, mais le simple fait d'avoir une revue de code va obliger l'équipe à communiquer, expliquer ce que chacun a fait, comment et justifier les différents choix.

Une revue de code est l'occasion rêvée pour poser des questions, y répondre et discuter.

# On peut former les nouveaux 

La revue de code est déjà souvent utilisée pour les nouveaux développeurs, mais avoir une revue de code systématique pour l'ensemble de l'équipe permet au nouveau de se sentir complètement intégré à l'équipe : il est dans les mêmes *process*.

Elle est d'autant plus importante pour lui, qu'il ne connaît ni l'application, ni le métier. C'est une bonne occasion pour lui faire des remarques, lui expliquer des choses, lui montrer les bonnes méthodes limitant la duplication de code. D'une entreprise à l'autre, les approches peuvent être différentes, il est donc important de lui transmettre les habitudes de l'équipe.

Une fois qu'il aura bien appréhendé le projet, le fait de relire le code de développeurs plus expérimentés lui permettra d'apprendre de nouvelles choses et de prendre confiance en soi.