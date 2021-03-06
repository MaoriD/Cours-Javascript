# Cours de Javascript
Ce mini-cours a pour but de répertorier les lignes de codes essentielles de Javascript avec un commentaire pour les comprendre dans le but d'apprendre beaucoup plus rapidement ! J'y aborde le Javascript, le jQuery, NodeJS, npm et le scrapping avec Nightmare ! Basé sur la formation Le Wagon.

## Création des documents
Tout d'abord, il faut créer un dossier `html`contenant un fichier `nom.html`. Ensuite, il faut entrer dans ce fichier et y écrire :

```html
<!doctype html>
<html>

<head>
    <meta charset="utf-8">
    <title>Cours de Javascript par Maori D/title>
</head>

<body>
    <!-- Exécuter un script provenant d'un fichier javascript -->
    <script src="../js/cours.js"></script>
</body>

</html>
```

Ensuite, il faut créer un dossier `js`et y créer un fichier `nom.js`. Attention à bien respecter ce même nom dans la balise script pour que cela fonctionne !

> Pour avoir un aperçu de notre code Javascript, il faut ouvrir le fichier `nom.html` dans le navigateur, puis faire clic droit n'importe où "Inspecter l'élement" et ouvrir la console.

## Place au code


> Documentation : [https://developer.mozilla.org/fr/docs/Web/JavaScript](https://developer.mozilla.org/fr/docs/Web/JavaScript)

**Déclarer des  variables constantes**

    var nomVariable = number; // Variable de type nombre, avec une valeur
    var nomString = "string"; // Variable string, une chaîne de caractères
    var nomBoolean = false; // Variable boolean, vrai ou faux
    var nomTableau [1, "string", false]; // Tableau, valeurs à séparer par des virgules. On peut mettre les 3 précédentes dans le tableau
    var nomObjet = {
    	propriete1: "myProperty1",
    	propriete2: "myProperty2",
    } // Variable objet avec plusieurs propriétés dedans
    let nomVariable // Permet de créer comme var (mieux que var, donc à favoris)
    const nomConstante // créer une valeur qui ne change pas

**Ecrire des variables**

On écrit en camelCase. On met une majuscule à tous les mots sans espace à part le premier

Exemple : ceciEstUneVariableEnCamelCase

**Executer le javascript**

    console.log(trucAExecuter); // Affiche dans la console du navigateur
    alert() // Affiche une popin
    prompt() // Afficher une poppin avec une chaîne de caractère à entrer

**Modulo (%)**

Divise puis affiche le nombre restant
Exemple : 10%3 = 1 car il peut diviser 9 par 3 et il restera 1

**Renvoyer le type de la variable**

    var nomVariable = "test";
    console.log(typeof(nomVariable));
    
    // Renvoie "string"

**Faire un commentaire, utiliser pour expliquer le code**

    // Commentaire sur une ligne
    
    /* 
    Commentaire sur plusieurs lignes
    */

**Faire une concaténation, afficher deux variables**

    var variable1 = "hello"
    var variable2 = "bien?"
    
    console.log(variable1 + " " + variable2); // " " permet de mettre un espace entre les deux, on aurait pu mettre du texte aussi
    
    // Renvoie "hello bien?"

**Condition si, sinon**

    if (laCondition){
    console.log("Ce qui se passe si laCondition est vraie")
    } else if (laCondition2) {
    console.log("Ce qui se passe si laCondition2 est vraie")
    } else {
    console.log("Ce qui se passe si aucune condition n'est respectée = faux")
    }
    
    // On peut imbriquer des if dans des if

**Opérateurs de comparaisons, pour vérifier des variables**

    === // Vérifie si deux variables sont égales
    !== // Vérifie si deux variables sont différentes
    < // Inférieur
    > // Supérieur
    >= // Supérieur ou égal
    <= // Inférieur ou égal
    
    // Ajouter un = à chaque fois permet de vérifier le type de variable également
    // Exemple : !== vérifiera si les deux variables ET le type des variables sont différentes

**Opérateurs logique pour combiner la vérification de plusieurs variables**

    && // et
    || // ou

**Condition switch**

    switch (nomCondition) {
      case valeur1:
        // Instructions à exécuter lorsque le résultat
        // de l'expression correspond à valeur1
        instructions1;
        [break];
      case valeur2:
        // Instructions à exécuter lorsque le résultat
        // de l'expression correspond à valeur2
        instructions2;
        [break];
    [default:
        // Instructions à exécuter lorsqu'aucune des valeurs
        // ne correspond à instructions_def;
        [break];

**Indiquer l'heure actuelle**

    var nowHour = new Date().getHours(); 
    // N'affiche que l'heure en cours pas les minutes (ex: 12 pour 12:00 à 12:59)

**Condition ternaire (autre façon d'une condition)**

    console.log(nowHour < 17 ? "Bonjour" : "Bonsoir");
    // condition ? code_if_true : code_if_false
    // Ici, on vérifie si nowHour est inférieur à 17. Si c'est vrai, on affiche Bonjour, sinon on affiche bonsoir
    

**Afficher la taille (nombre de valeurs) : length**

    console.log(nomVariable.length);

**Les tableaux**

    var nomTableau [1, 2, 3]; // Créer un tableau 
    nomTableau; // Affiche le tableau
    nomTableau[1]; // Afficher la seconde valeur du tableau (la première valeur d'un tableau est égale à 0 en JS)
    nomTableau.push("valeur"); // Ajoute une valeur à la fin du tableau
    nomTableau.unshift("valeur"); // Ajoute une valeur au début du tableau
    nomTableau.pop(); // Supprime la dernière valeur du tableau
    nomTableau[0] = 5; // Remplace la première valeur du tableau par 5
    nomTableau.length; // Renvoie le nombre de valeurs dans le tableau

**Classe**

    class Contact { // Créer une classe nommé Contact (mettre toujours en majuscule)
        constructor(nom, prenom) { // Composé d'un constructeur avec paramètre nom et prénom
          this.nom = nom; // Son nom correspond au paramètre nom
          this.prenom = prenom; // Son prénom correspond au paramètre prénom
        }
        description() { // Je créé une fonction qui retourne une phrase compréhensive
            return `Nom: ${this.nom}, prénom: ${this.prenom}`;
        }
    }
    
    const listeContacts = []; // Je créé un tableau 
    listeContacts.push(new Contact("Lévis", "Carole")); // J'ajoute un contact dans ce tableau
    
    listeContacts.forEach(contact => { // Je créé une boucle du tableau avec le paramètre contact
                console.log(contact.description()); // Affiche la fonction description du contact
            }); // Vu que c'est une boucle forEach ça l'execute tant qu'il y a des contacts

**Boucle, exécute le code en boucle tant que la condition d'arrêt n'est pas valide**

    var nomTableau = [12, 15, 9, 18, 11, 14];
    //        Index   0,  1,  2,  3,  4,  5 (la première valeur d'un tableau correspond à 0, la seconde à 1 etc... JS commence toujours par 0)
    
    var sum = 0;
    
    
    for(var i = 0; i < nomTableau.length; i++) {
    sum = sum + nomTableau[i];
    } 
    
    // 1. On déclare une variable tableau comprenant différents nombres;
    // 2. On déclare une variable "sum";
    // 3. On initialise une variable i valant 0, correspondant à l'Index;
    // 4. On vérifie que i est inférieur à la taille du tableau ;
    // 5. On ajoute 1 à i (l'index) grâce à " ++ "
    // 6. Enfin, on écrase la variable sum en addionnant toutes les valeurs du tableau

**Boucle while, autre façon de faire une boucle**

    var nomTableau = [12, 15, 9, 18, 11, 14];
    
    var sum = 0;
    var i = 0;
    
    while (i < nomTableau.length) {
    	sum = sum.nomTableau[i];
    	i++
    }

**Fonction, permet d'éviter de répéter du code qu'on pourra utiliser plusieurs fois**

    function nomFonction(parametre) { // On créé une fonction en lui donnant un nom et un paramètre
      var message = "Bonjour cher utilisateur"; // Le code à exécuter dans la fonction
    	return blablabla; // Ce qu'on souhaite que la fonction renvoie
    }
    nomFonction("parametre"); // Appelle la fonction, la lance
    
    // Exemple 1 :
    function direBonjour(prenom) {
      const message = `Bonjour, ${prenom} !`;
      return message;
    }
    
    console.log(direBonjour("Baptiste")); // "Bonjour, Baptiste !"
    console.log(direBonjour("Sophie")); // "Bonjour, Sophie !"
    
    // Exemple 2:
    function average(grades) {
      var sum = 0;
      for (var i = 0 ; i < grades.length; i++) { // Boucle for dans la fonction (voir section boucle for)
        sum = sum + grades[i];
      }
      
      return sum / grades.length; // Renvoie la moyenne des valeurs dans le paramètre qu'on va définir, grâce à l'adition faite précédemment dans la boucle for
    }
    
    var firstAverage = average([11, 15, 12]); // Je stocke mon résultat dans une variable, et définis les paramètres de la fonction (17, 14, 11)
    
    console.log(firstAverage); // Enfin, j'affiche ma variable
    
    // Renvoie la moyenne, 14
    
    // On peut mettre plusieurs paramètres en les séparant par une virgule
    // Les variables dans les fonctions existent que à l'intérieur de la fonction, on ne peut pas les réutiliser en dehors

**Objets, permet de définir plusieurs propriétés à une variable**

    var nomVariable = { // Utiliser les accolades
    	firstName: "John", // Séparer par une virgiule les différentes propriétés
    	lastName: "Lennon"; 
    }
    
    // Ici j'ai définis une variable nomVariable qui a les propriétés John et Lennon.
    
    nomVariable.age = 14; // Permet d'ajouter une propriété
    
    console.log(nomVariable.lastName) // Affiche le lastName (Lennon) de ma variable
    
    // On peut ajouter une fonction dans la variable objet :
     
    var nomVariable = {
    	firstName: "John", 
    	lastName: "Lennon";
    	fullName: function() {
    		return.this.firstName + " " + this.lastName; // this permet de sélectionner la variable dans laquelle on se trouve
    	}
    }

## Accéder et manipuler le DOM

**Accéder**

    const Elt = document.getElementById('myID'); // Créer une constante qui récupere le contenu de la balise avec l'ID myID
    document.getElementsByClassName('myClass') // Idem avec une class, s'il y a plusieurs class, créer un tableau avec les différents éléments
    document.getElementsByTagName('div') // Idem avec une balise HTML
    document.querySelector("#myId p.article > a") // Sélectionner le lien enfant du p avec la class article qui se trouve dans la balise avec l'ID myID
    element.children // Les enfants d'un élément
    element.parentElement // Le parent d'un element
    element.nextElementSibling // L'élément d'après qui se trouve à la même hauteur 
    element.nextElementSibling // L'élément qui se trouve avant à la même hauteur
    

**Ajouter du contenu HTML**

    let elt = document.getElementById('main');
    elt.innerHTML = "<ul><li>Elément 1</li><li>Elément 2</li></ul>"; // Ajouter une liste à la main

**Ajouter/supprimer/modifier des class**

    elt.classList.add("nouvelleClasse");    // Ajoute la classe nouvelleClasse à l'élément
    elt.classList.remove("nouvelleClasse"); // Supprime la classe nouvelleClasse que l'on venait d'ajouter
    elt.classList.contains("nouvelleClasse");   // Retournera false car on vient de la supprimer
    elt.classList.replace("oldClass", "newClass"): // Remplacera oldClass par newClass si oldClass était présente sur l'élément

**Changer le style d'un élément**

    elt.style.color = "#fff";      // Change la couleur du texte de l'élément à blanche
    elt.style.backgroundColor = "#000"; // Change la couleur de fond de l'élément en noir
    elt.style.fontWeight = "bold"; // Met le texte de l'élément en gras

**Modifier les attributs**

    elt.setAttribute("type", "password"); // Change le type de l'input en un type password
    elt.removeAttribute("attribute"); // Ajouter un attribut appelé attribute
    elt.setAttribute("name", "my-password"); // Change le nom de l'input en my-password
    elt.getAttribute("name"); // Retourne my-password

**Créer de nouveaux éléments**

    const newElt = document.createElement("div"); // Créer une div
    let elt = document.getElementById("main"); // Récupère la main
    
    elt.appendChild(newElt); // Ajoute à main (elt) la div (newElt) en tant qu'enfant
    elt.removeChild(newElt); // Supprime l'élément newElt de l'élément elt
    elt.replaceChild(document.createElement("article"), newElt); // Remplace l'élément newElt par un nouvel élément de type article

**Détecter des éléments**

    const elt = document.getElementById('mon-lien'); // On récupère l'élément sur lequel on veut détecter le clic
    elt.addEventListener('click', function(event) { // On écoute l'événement click, notre callback prend un paramètre que nous avons appelé event ici
        elt.innerHTML = "C'est cliqué !"; // On change le contenu de notre élément pour afficher "C'est cliqué !"
    		event.preventDefault(); // On utilise la fonction preventDefault de notre objet event pour empêcher le comportement (changer de page pour un lien) par défaut de cet élément lors du clic de la souris
    		event.stopPropagation(); // Empêche la propagation de l'évènement vers le parent, ce qui est le cas par defaut en Javascript
    });

**Détecter mouvement souris**

    elt.addEventListener('mousemove', function(event) { // Ecouter l'évènenement
        const x = event.offsetX; // Coordonnée X de la souris dans l'élément
        const y = event.offsetY; // Coordonnée Y de la souris dans l'élément
    });

*Exemple*

    document.getElementById("name").addEventListener("input", function(event) { // Je détecte la balise avec ID name et je detecte l'event input et créé une fonction
      document.getElementById("res-name").innerHTML = event.target.value; // J'ajoute dans res-name (target signifie l'élément sur lequel s'est produit l'évènement et value la valeur du champs
    });
    
    document.getElementById("gender").addEventListener("change", function(event) { // Je detecte gender et j'écoute le changement d'un select grâce à "change"
      document.getElementById("res-gender").innerHTML = event.target.value; // J'ajoute la valeur à res gender
    });
    
    document.querySelector('body').addEventListener('mousemove', function(event) { // Je détecte le mouvement de la souris à mouvemove
        document.getElementById("mouse-x").innerHTML = event.offsetX + ""; // J'ajoute la valeur de X de la souris dans mouse-x
        document.getElementById("mouse-y").innerHTML = event.offsetY + ""; // J'ajoute la valeur de Y de la souris dans mouse-y
    });

**Vérifier les données d'un formulaire**

    myInput.addEventListener('input', function(e) {
        var value = e.target.value;
        if (value.startsWith('Hello ')) { // Je vérifie ici si il commence par Hello
            isValid = true;
        } else {
            isValid = false;
        }
    });

## Scrapping via Ajax

    var request = new XMLHttpRequest(); // Créer un nouvel objet de type XMLHttpRequest qui correspond à l'objet Ajax
    request.onreadystatechange = function() { // onreadystatechange = Contient l'état de la requête
        if (this.readyState == XMLHttpRequest.DONE && this.status == 200) { // status = contient le code de statut de la requête
            var response = JSON.parse(this.responseText); // responseText qui contient la réponse du service web au format Texte
            console.log(response.current_condition.condition);
        }
    };
    
    request.open("GET", "http://url-service-web.com/api/users"); // Ouvrir une connexion vers un service web
    // request.setRequestHeader("Content-Type", "application/json");
    request.send(JSON.stringify(jsonBody); // On envoie la requête au service web, JSON.stringify(jsonBody) permet de transformer le javascript en json

## **Programmation orientée objet**

    function Student () { // Créer une variable avec une fonction en UpperCase 
    }
    
    var john = new Student();
    var paul = new Student(); // j'ajoute deux variables dans ma variable Student
    
    console.log(john instanceof Student); // Je peux vérifier si ma variable est bien contenu dans Student, renvoie true
    
    Student.prototype.fullName = function() { // Prototype permet de prendre en compte le fait qu'on utilise une certaine variable
    	return this.firtName + " " + this.lastName;
    }
    
    paul.fullName(); // Affiche le fullName de la variable paul qui est dans la variable Student
    

## **Ajouter du HTML avec Javascript/jQuery**

> Documentation : [https://api.jquery.com/](https://api.jquery.com/)

**Ajouter/Supprimer une balise p**

    var firstParagraph = document.createElement("p"); // Créer une variable qui créer une balise p (paragraphe en HTML)
    firstParagraph.textContent = "Bonjour, ceci est le premier paragraphe"; // Ajouter du texte dans cette variable
    document.body.appendChild(firstParagraph); // Ajouter cette variable au parent body
    document.body.removeChild(firstParagraph); // Supprimer la variable du parent body

**Attendre que le document est chargé (obligatoire pour utiliser du jQuery)**

    $(document).ready(function() {
    	// Ecrire le jQuery ici
    });

**Sélecteurs jQuery**

    $('.myClass'); // Sélectionner une classe
    $('#myId'); // Sélectionner une ID
    $('balise'); // Sélectionner une balise HTML

**Masque/Afficher quelque chose (jQuery)**

    $('element').hide(); // Masquer element
    $('element').show(); // Afficher element
    
    // Remplace element par ce qu'on souhaite masquer/afficher exemple : img, p ou même une div #mydiv ...

**Récupérer le contenu html d'un élément**

    // Mettre au préalable dans le HTML une balise avec un ID #myID
    
    var nomVariable = $('#myID') // Créer une variable contenant le contenu html de l'id first-paragraph
    
    nomVariable.html(); // Affiche le contenu html récupéré de la variable
    nomVariable.text(); // Récupère le contenu de toutes les balises enfants (utile si .firstParagraph était une div par exemple, cela récuperera le contenu de tous les enfants de la div)

**Remplacer le html** 

    // Mettre au préalable dans le HTML une balise avec un ID #myID
    
    var nomVariable = $('#myID') // Créer une variable firstParagraph reprenant 
    
    nomVariable.html("Bonjour"); // Remplace le contenu de l'ID par le paramètre "Bonjour"

**Récupérer les valeurs d'un formulaire**

    $('#myID').val(); 

**Ajouter/Retirer une classe**

    $('#cart').addClass('bold'); // Ajouter une classe .bold à la balise ayant l'ID #cart
    $('#cart').removeClass('bold'); // La retire (si présente)

**Afficher le nombre d'éléments**

    console.log($('.beatle').length); // Affiche le nombre d'éléments ayant la classe beatle

**Détecter un clic jQuery et appliquer/retirer une class**

    $('element').click(function() { // Lorsque je clic sur element, je créé une fonction
    	$(this.toggleClass('classAjoutee'); // qui ajoute une class classAjoutee si elle est pas déjà présente, sinon la retire (grâce à toggle). Remplacer 
    }

**Vérifier si une class est présente sur un élément**

    $('element').hasClass('classAVerifier')

**Appeler un plugin jQuery**

1. Télécharger le plugin, le mettre dans le dossier de notre site
2. L'appeler en faisant <script src="monPlugin.js"> en le mettant AVANT le script js
3. Voir la doc du plugin lol, dépend de chaque plugin

**Appeler du contenu avec Ajax**

    $.ajax({ // Utiliser ajax
    	url: "http://httpbin.org/html", // Url où prendre le contenu
    	success: function(data) { // S'il y arrive faire une fonction avec le paramètre data
    		$('#content').html(data); // Insérer dans la div #content le contenu html qui se trouve dans data
    		}
    	});
    });
    
    

**Appeler du contenu Google Spreed Sheet**

    $('#display-link').on('click', function() { // Au clic sur le lien display link, je lance la fonction
    
            $.ajax({ // Fonction ajax
                url: "https://spreadsheets.google.com/feeds/list/1yB5fRnSp7CoZhip-q-Tzig7mrp14Ykg4668XadOUiJk/od6/public/values?alt=json", // Lien du contenu à récuperer
                success: function(data) {
                    var entries = data.feed.entry; // Je créé une variable contenant la donnée json entry qui est dans feed qui est dans data
                    for (var i = 0; i < entries.length; i++){ // Boucle for
                        var ville = entries[i].gsx$ville.$t; // Je créé une variable ville qui contient ma ligne ville
                        var habitants = entries[i].gsx$habitants.$t; // Je créé une variable ville qui contient ma ligne ville
                        var image = entries[i].gsx$image.$t;
                            $('#content').append($('<h2>' + ville + '</h2>'));
                    }
                }
            });
        });

**Récupérer les données d'un formulaire pour les afficher**

    // 1. Créer une bdd
    // 2. Créer un formulaire en HTML avec un input auteur et un textarea content + bouton submit
    // 3. 
    
    
    function appendComment(element) {
    	$('#element').append($('<p>' + element.content + ' - <em>' + element.author + '</em></p>'));
    } // Créer une fonction qui ajoute le contenu sur la page
    
    $('#new-comment-form').on('submit', function(e) {
    	e.preventDefault(); 
    	$.ajax({
    		url: "http://localhost:3000.comments.json", // Lien de la bdd
    		method: "POST", // Type de méthode (post pour un formulaire)
    		data: $('#new-comment-form').serialize(), // Récupérer  le contenu du form et l'ajouter à la bdd grâce au bouton submit #new-comment-form
    		success: function(data) {
    			appendComment(data); // Appeler la fonction qui ajoute le contenu
    		}
    

**RegEx**

**Permet de faire des recherches dans le code**

![](Capture_decran_2019-04-13_a_00-5b788b98-8d87-40f0-a9a1-8b4881ddfde7.36.29.png)

**Tester si un code postal est correct**

    function isFrenchZipCode(zipCode) { // Je créé une fonction isFrenchZipCode
    	var pattern = /^[0-9][0-9AB][0-9]{3}$/; // Je créé une variable qui test si : le premier caractère est un chiffre entre 0 et 9 [0-9], le second entre 0 et 9 ou la lettre A ou B [0-9AB], puis si les trois prochains caractères {3} sont entre 0 et 9 [0-3] et je termine mon test RegEx $, je l'ai ouvert grâce à ^
    	return pattern.test(zipCode); // Renvoi la variable pattern
    }
    
    // Demande au préalable de créer un formulaire avec l'ID contactForm, une div pour chaque label + input appelé form-group et une class has-success qui met le tout en vert et has-error qui met en rouge (bootstrap)
    $(document).ready(function(){ // Lorsque mon document est prêt
    	$('#contactForm').on('submit', function(e) { // Je créé une fonction lorsque mon formulaire est submit
    
    		var valid = true; // Par défaut ma variable valid est true
    		var zipCode = $('#ZipCode').val(); // La variable zipCode correspond au contenu de l'input avec l'ID ZipCode
    		var formGroup = $ ('$zipCode').parents('.form-group'); // la variable formGroup correspond au parent de zipCode
    	
    		if (isFrenchZipCode(zipCode)) { // Si la variable zipCode de ma fonction isFrenchZipCode est valide
    			formGroup.removeClass('has-error').addClass('has-success'); // Je retire la class has-error si elle y est, et j'ajoute la class has-success
    			} else { // Sinon
    			valid = false; // Ma variable valid devient false
    			formGroup.removeClass('has-success').addClass('has-error'); // Je retire la class has-success si elle y est, et j'ajoute la class has-error
    		}
    		if(!valid) { // Si la variable valid est different de sa valeur (true)
    			e.preventDefault(); // J'autorise le chargement de la page au submit
    		}
    	});
    }

**Node & npm**

    node -v = vérifier si node est présent (voir la version)
    npm init = initier npm dans notre dossier
    npm install --save nomDuPlugin = installer un plugin npm, nécessite parfois d'avoir un autre plugin installé
    brew install nomDuPlugin = installer grâce à homebrew un plugin
    

**Scrapping avec Nightmare**

    var Nightmare = require ('nightmare');
    var department = process.argv[2] // Définie une variable qui prend l'argument que l'on tape dans dans la commande node script.js "alsace"
    new Nightmare() 
    	.goto (https://www.wikipedia.org/'); // Se rendre sur la page de wikipedia
    	// TODO : empiler des actions ici
    
    	.viewport(1024, 768) // Définis la taille du navigateur
    	.screenshot'home_wikipedia.png') // Prendre un screenshot de la page avec la taille définie
    
    	.url(function(url){ // Créer une fonction url avec paramètre url
    		console.log("Our url :" + url); // Afficher l'url de la page
    
    	.type("#searchInput", department) // Ecrit ce que l'on met dans l'argument department, dans l'input avec l'ID searchInput
    	.selector("#searchLanguage", "fr") // Sélectionne la valeur fr dans le selecteur avec l'ID searchLanguage
    	.click(".formBtn") // Clique sur la balise avec la class formBtn
    	.wait() // Attendre que la page se charge
    	.evaluate (function(){ // Permet d'executer du js dans la page
    	var inhabitants = $('abbr[title=habitants]'.parent().text(); // Créé une variable qui contient le texte du parent de la balise abbr qui a le title habitants
    	return inhabitants; // Renvoie la valeur de inhabitants
    	}
    
    // Faire node script.js "seine maritime" dans le terminal (en étant dans notre dossier de travail)
