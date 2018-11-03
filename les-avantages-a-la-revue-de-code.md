La revue de code à de nombreux avantages comme j'ai commencé à le présenter.  Voici les principaux avantages que j'y vois. 

# On écrit du code lisible et propre

C'est pour moi un des avantages les plus importants de la revue de code : le code est plus lisible et globalement de meilleur qualité.

L'auteur du code va s'obliger à relire son propre code, il va donc ajouter des commentaires, et tout faire pour qu'il soit compréhensible au maximum pour que la revue de code se passe le mieux possible. 

Si le code est intégré, cela veut dire que deux personnes ont estimés que le code était compréhensibles. On peut extrapoler un peu et se dire que si deux personnes de l'équipe le comprends, le reste de l'équipe devrait également le lire sans difficultés. 

Un second regard à l’application permet de limiter la duplication de code par exemple grâce à une deuxième vision. « J'avais fait ça pour un autre module, on doit pouvoir le réutiliser plutôt que réinventer la roue ! ». 

# On limite les bugs

La seconde personne de la revue de code va avoir un œil extérieur, contrairement à l'auteur qui était plongé dans son code. Elle va également tester le code et donc : 

- Penser à des cas limites que le développeur aurai pu oublier
- Certains bugs sont visibles uniquement en lisant le code. Même un développeur relisant son propre code pourrait voir d'éventuels problèmes, de la même manière qu'un auteur doit relire son papier avant de le soumettre. La revue de code oblige l'équipe à avoir cette approche.
- Deux personnes comprendront plus facilement le besoin du client. Il peut arriver que le développeur se soit trompé, une deuxième personne pourra voir le problème avant intégration.
- Tester sur un second environnement, cela peut également jouer. Dans mon cas personnel, il nous arrive régulièrement de voire des problèmes d'affichage Windows / Linux en revue de code

# On apprend

Ce n'est pas forcément le premier avantage auquel on pense, mais de mon expérience la revue de code permet d'apprendre, mais pas uniquement pour les personnes qui proposent du code, également pour le relecteur (principalement dans le cas où l'ensemble de l'équipe peut-être relecteur).

Cela peut arriver sur des « *tips* » du langage que l'on utilise : 

- Le relecteur de code peut tomber sur quelque chose d'inconnu : « Oh, tiens ! Je ne connais pas ça ? Comment ça marche ». L'auteur du code va ainsi expliquer ce qu'il a fait, et en quoi il estime que c'est avantageux. 
- Mais on peut avoir l'effet inverse : « Tu pourrai utiliser cette technique, c'est plus optimisé / rapide / efficace ! » 

On peut également apprendre sur des questions métiers, où des questions d'architecture de notre application.

# On peut former les nouveaux 

La revue de code est certainement déjà très souvent utilisés pour les nouveaux développeurs. Mais avoir une revue de code systématique pour l'ensemble de l'équipe permet au nouveau de se sentir complètement intégré à l'équipe : il est dans les même process.

Ensuite, évidemment elle est d'autant plus importante pour lui, car il ne connaît ni l'application ni le métier. C'est une bonne occasion pour lui faire des remarques, lui expliquer des choses, lui montrer les bonnes méthodes limitant la duplication de code. 

