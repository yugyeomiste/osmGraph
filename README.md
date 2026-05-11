# TD7 - Graphes
## Exercice 2

### 1. 
Dans le projet, on utilise **WeightedGraph** pour gérer la structure du graphe avec une liste d'adjacence. C'est ce qui stocke les connexions et les poids des arêtes. La structure **PositionedGraph** sert à rajouter les coordonnées X et Y sur chaque point pour qu'on puisse placer les noeuds sur la carte et calculer des distances réelles.

### 2. 
* **Extraction OSM** : Lit le fichier .osm pour transformer les données XML en un graphe utilisable dans le code C++.
* **Simplification** : Sert à épurer le graphe pour enlever les noeuds inutiles et gagner en performance.
* **Visualisation** : S'occupe de l'affichage avec la bibliothèque raylib pour qu'on puisse voir le réseau et interagir avec.

### 3. 
Le fichier **simplify.cpp** contient les étapes pour réduire le nombre de noeuds. Le but est de supprimer les noeuds de "degré 2", soit ceux qui sont juste au milieu d'une route sans être une intersection.

L'avantage principal est que ça réduit énormément la taille du graphe. Du coup, l'algorithme de Dijkstra tourne beaucoup plus vite car il y a moins d'éléments à trier dans la file de priorité. L'inconvénient est qu'on simplifie un peu le tracé visuel des routes, mais pour calculer un itinéraire, c'est beaucoup plus efficace.
