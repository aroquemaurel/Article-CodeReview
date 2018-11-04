À ce stage, vous êtes peut-être en train de vous dire que ça semble une bonne idée, mais que ça va prendre beaucoup de temps et je ne peux pas vous contredire sur ce point. Bien que le temps de la revue soit variable d'un développeur à l'autre, oui, ça peut être long si on met bout à bout les revues. Mais je pense que le temps passé est contrebalancé par les avantages. À long terme, cela permettra d'avoir un projet plus maintenable, avec une équipe efficace. 

# On écrit du code lisible et propre

C'est pour moi un des avantages les plus importants de la revue de code : le code est plus lisible et globalement de meilleur qualité.

L'auteur va s'obliger à relire son propre code, il va donc ajouter des commentaires, et tout faire pour qu'il soit compréhensible au maximum pour que la revue de code se passe le mieux possible. 

Si le code est intégré, cela veut dire qu'au moins deux personnes ont estimés que le code était compréhensibles et élégant. On peut extrapoler un peu et se dire que si deux personnes de l'équipe le comprends, le reste de l'équipe devrait également le lire sans difficultés. 

Un second regard à l’application permet de limiter la duplication de code grâce à une deuxième vision. « J'avais codé *ça* pour un autre module, on doit pouvoir le réutiliser plutôt que réinventer la roue ! ». 

# On limite les bugs

Le relecteur va avoir un œil extérieur, contrairement à l'auteur qui était plongé dans son code. Il va également tester le code et donc : 

- Penser à des cas limites que le développeur aurai pu oublier
- Certains bugs sont visibles uniquement en lisant le code. Même un développeur relisant son propre code pourrait voir d'éventuels problèmes, de la même manière qu'un auteur doit relire son papier avant de le soumettre. La revue de code oblige l'équipe à avoir cette approche.
- Deux personnes comprendront plus facilement le besoin du client. Il peut arriver que le développeur se soit trompé, une deuxième personne pourra voir le problème avant intégration.
- Tester sur un second environnement, cela peut également jouer. Dans mon cas personnel, il nous arrive régulièrement de voire des problèmes d'affichage Windows / Linux en revue de code.

# On apprend

Ce n'est pas forcément le premier avantage auquel on pense, mais de mon expérience la revue de code permet d'apprendre, que ça soit pour l'auteur, ou pour le relecteur (principalement dans le cas ou les relecteurs « tournent »).

- Le relecteur peut tomber sur quelque chose d'inconnu : « Oh, tiens ! Je ne connais pas ça ? Comment ça marche ». L'auteur va ainsi expliquer ce qu'il a fait, et en quoi il estime que c'est avantageux. 
- Mais on peut avoir l'effet inverse : « Tu pourrai utiliser cette technique, c'est plus optimisé / élégant / efficace ! » 

On peut également apprendre sur des questions métiers, où des questions d'architecture de notre application.

# On communique

Ça peut paraître assez basique. Mais le simple fait d'avoir une revue de code va obliger l'équipe à communiquer. Expliquer ce que chacun a fait, comment. Justifier les différents choix.

# On peut former les nouveaux 

La revue de code est déjà souvent utilisé pour les nouveaux développeurs. Mais avoir une revue de code systématique pour l'ensemble de l'équipe permet au nouveau de se sentir complètement intégré à l'équipe : il est dans les même *process*.

Elle est d'autant plus importante pour lui, car il ne connaît ni l'application ni le métier. C'est une bonne occasion pour lui faire des remarques, lui expliquer des choses, lui montrer les bonnes méthodes limitant la duplication de code. D'une entreprise à l'autre, les approches peuvent être différente, il est donc important de lui transmettre les habitudes de l'équipe.

Une fois qu'il aura bien appréhendé le projet, lui faire relire le code de développeurs plus expérimenté lui permettra d'apprendre de nouvelles choses et de prendre confiance en lui.

