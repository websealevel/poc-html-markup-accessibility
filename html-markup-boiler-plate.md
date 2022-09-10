# HTML, du bon usage du Markup

L'essentiel pour avoir un markup correct et accessible (personnes mal-voyantes, etc.)

## Dans la section `head`

- `<meta lang="fr">`, la langue de la page
- `<meta name="description" content="La description du contenu de la page">`
-  `<meta name="keywords" content="HTML, sémantique, accesibilité, Bootstrap">`, des mots clefs pertinents décrivant le contenu de la page
- `<meta name="author" content="l'auteur de la page"`
-   `<meta name="viewport" content="width=device-width, initial-scale=1">`: **utilisé uniquement par les terminaux mobiles**. Donne une indication de la taille du viewport. `width=device-width` définit la largeur de la zone d'affichage (viewport) en pixels.  `initial-scale=1` définit le ratio entre la taille de l'écran (device-width en mode portrait et device-height en mode paysage) et la taille de la zone d'affichage. En gros on dit que si on tourne l'appareil et que l'on passe en mode *paysage* alors la taille d'affichage doit prendre tout l'écran.

## Dans la section `body`

### Division du contenu

Ces balises sont toutes à connaître !

- `<header>` : contenu introductif, aidant à la navigation. Peut contenir le titre, logo, formulaire de recherche, section de navigation. En terme d'accessibilité, il représente un point de repère [banner](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/banner_role) dans un contexte `body`. Il est donc inutile de lui ajouter l'attribut `role='banner'`. On peut et doit l'utiliser aussi dans un contexte `article`
- `<nav>` : section de page avec des liens vers d'autres pages ou des fragments de cette page. Section destinée à la navigation (menus, table des matières, indexes, etc.)
- `<main>` : contenu principal du document (body). 
- `<aside>` : contenu à part, qui n'a rien à voir avec le contenu principal. Des encadrés, légendes, etc.
- `<article>` : composition **autonome** dans le document. Exemple: un article sur une page qui liste des articles. C'est un élément de contenu indépendant du reste de la page, qui pourrait être réutilisé dans un autre contexte. En ce sens, il peut reprendre toute la hiérarchie du body (header, main, section, footer, etc.)
- `<section>` : section générique d'un document. Elle commence par un titre. On sait quand l'tiliser si cette partie du document apparait dans le plan par exemple. `<section> <h2>Titre de la partie 1</h2><p>Le contenu de la section, etc.</p></section>`
- `<address>` : informations de contact pour une personne, une organisation, etc.
- `<h1>..<h6>` : 6 niveaux de titre. **Il ne doit y avoir qu'un seul `h1` sur un document**
- `<div>` : **aucune valeur sémantique**. Sert uniquement à la construction de la mise en page/layout !


## Valider le markup

Le HTML est un markup permissif, si vous omettez de fermer une balise il sera tout de même rendu par le navigateur.  Il est donc essentiel de valider le markup avant de le livrer. Il est en effet essentiel que le document soit [bien formé](https://www.w3.org/TR/xhtml1/#h-4.1). On peut 

- utiliser le [Markup Validation Service du W3C](https://validator.w3.org)
- utiliser le [XHTML](https://fr.wikipedia.org/wiki/Extensible_Hypertext_Markup_Language), à l'origine pensé comme le successeur du HTML (vers lequel converge HTML5), il est basé sur XML (et non SGML, la source des deux applications). Plus restrictif.

## Template

Voici un exemple de markup qui récapitule tous les éléments vus.

~~~html
<!DOCTYPE html>
<html>

<head>
  <meta lang="fr">
  <meta charset="utf-8">
  <title>Markup</title>
  <meta name="description" content="Utilisation du markup HTML  pour une bonne sémantique et une bonne accessibilité">
  <meta name="keywords" content="HTML, sémantique, accesibilité,">
  <meta name="author" content="Paul Schuhmacher">
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <link rel="stylesheet" href="style.css">
</head>

<body>

  <header>
    <h1>Titre principal</h1>
    <nav class="navbar ..."></nav>
  </header>

<main>

    <section>
        <h2>Première partie du contenu </h2>
        <p>Lore ipsum</p>
    </section>

    <section>
        <h2>Deuxième partie du contenu </h2>
        <p>Lore ipsum</p>
    </section>

<section>
    <h2>Liste des articles</h2>
    <ul>
        <li>
            <article>
                <header>
                    <h3>Titre de l'article</h3>
                    <p>Extrait de l'article</p>
                    <a href="#">Lire l'article</a>
            </header>
            <footer>Footer de l'article</footer>
        </article>
    </li>
</ul>
</section>


</main>

<aside>
Contenu qui n'a rien à voir avec le contenu de cette page
</aside>

 <footer>
  Le footer de la page
<address>Mes informations de contact</address>
</footer>

<script src="main.js" type="module"></script>
</body>

</html>
~~~

## Exercices

- Quelles sont les 2 éléments obligatoires d'un document HTML ?
- Où place-t-on généralement les scripts JS ? Pourquoi ?
- Donner les 9 éléments HTML qui permettent de sectionner sémantiquement un document HTML ? Donner brièvement la fonction de chacun d'entres eux.
- Quels sont les ARIA Roles ?
- Creer le markup de cette page (montrer image d'une page d'accueil/screenshot d'un site)
- Qu'est ce qui ne va pas dans ce markup ?

~~~html
<main>
<section>
<div>
<h2>Article 1</h2>
</div>
</section>
<section>
<div>
<h2>Article 2</h2>
</div>
</section>
</main>
~~~

## Ressources

Quand on parle de contexte `body`, on veut dire que l'ancêtre de l'élément HTML est `body`.

- [Liste des éléments HTML5](https://developer.mozilla.org/fr/docs/Web/HTML/Element)
- [balise meta](https://developer.mozilla.org/fr/docs/Web/HTML/Element/meta)
- [balise header](https://developer.mozilla.org/fr/docs/Web/HTML/Element/header)
- [balise nav](https://developer.mozilla.org/fr/docs/Web/HTML/Element/nav)
- [ARIA Roles](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles), les roles ARIA permettent d'ajouter du sens sémantique au éléments HTML et donc au contenu 


