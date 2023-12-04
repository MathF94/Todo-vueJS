# Exercice ToDO LISTE
dans votre fichier App vue !

# ETAPE 1 ADD
1- Créer un objet data contenant un tableau simple

2- dans votre data mettre en place un titre h3: Liste à faire

3- Afficher les éléments de l'objet data dans une liste

4- mise en place d'un formulaire qui permettra de rejouter une tâche faire à notre tableau

5- mise en place de la méthode qui rajoutera l'information entrée dans nos formulaires a notre tableau

# ETAPE 2 DELETE
mise en place d'un button delete dans notre liste
!!! ATTENTION !!! le button doit être placé entre les balises "Li"
afin que pour chaque tâche j'ai un button 

le button delete devra appeler la méthode Delete(index)

mise en place de la méthode Delete(index) qui prendra en paramètre l'index de la tâche par rapport a sa position dans le tableau afin de le supprimer 

supprimer l'élément :)

# ETAPE 3 UPDATE
mise en place d'une propriété "isEditing" qui return "false"
--> fait

mise en place d'une propriété "selectIndex" qui return "null"
--> fait

mise en place d'un button update comme pour l'exemple de Delete "ETAPE 2"
--> fait

le button update devra appeler la méthode Update(index, task)
--> fait

mise en place d'un second formulaire qui permettra d'Update une tâche dans notre tableau (on se retrouve avec 2 formulaires afficher)
--> fait

mise en place d'une directive "v-if" qui affichera le formulaire add ou update en fonction de "isEditing"
--> fait

mise en place de la méthode Update(index, task) qui prendra en paramètre l'index de la tâche et la tâche, les deux paramètres auront "null" comme valeur par défaut.

dans le cas ou la méthode Update(index, task) est appelée par le button update, vous devrez initialiser la propriété "this.SelectIndex" avec "index" et "this.task" avec task.

dans le cas où la méthode update(index, task) est appelée avec le formulaire vous devrez récupérer this.SelectIndex et this.task et modifier le tableau 
Rénitialiser "isediting" a false
Rénitialiser "task" a null

# ETAPE 4 DECOUPAGE DE CODE



```javascript
<script src="https://cdn.jsdelivr.net/npm/vue/dist/vue.js"></script>
new Vue({
    el: '#app',
    // <!-- Créer un objet data contenant un tableau simple et un tableau composé d'objet  -->
    
    // <!-- Afficher les éléments de l'objet data dans des listes et tables   -->
});
```
