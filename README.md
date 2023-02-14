# wordpress-fse
Utilisation des fonctionnalités natives de "full site editing" (FSE) offertes par WordPress pour réaliser une maquette client


## Projet et maquette


**Maquette Figma à réaliser avec les blocks WordPress :**  
https://www.figma.com/file/XP5Kla9gqSkYf7XEK8py2l/BSA-Web-%2F-Telescope?node-id=0%3A1&t=7vfVYIx3k1z4VHRF-0

![Maquette](https://github.com/molokoloco/wordpress-fse/blob/main/medias/maquette.png?raw=true)

**Démo de la page demandée (en ligne un certain temps) :**  
https://wordpress.julienweb.fr 

![Page](https://github.com/molokoloco/wordpress-fse/blob/main/medias/screenshot-page.png?raw=true)

**Admin Gutenberg en FSE :**  
https://wordpress.julienweb.fr/wp-admin/site-editor.php

![Admin](https://github.com/molokoloco/wordpress-fse/blob/main/medias/screenshot-editor.png?raw=true)

**L’ensemble du site démo est téléchargeable et installable** sous forme d’archive “.wpress” :

+ https://fr.wordpress.org/plugins/all-in-one-wp-migration/ (Plugin a installer)
+ https://github.com/molokoloco/wordpress-fse/raw/main/medias/wordpress.julienweb.fr-20230214-134439-v5s7oi.wpress (Archive 50Mo)
+ Login WordPress : admin5730, password : admin5730

J'ai utilisé les fonctionnalités natives de "full site editing" (FSE) offertes par WordPress.
A cette fin j'ai installé la version en beta 6.2-beta1-55324 (https://wordpress.org/download/beta-nightly/)  
La version actuelle 6.1.1 LTS semble avoir un bug et ne pas afficher le FSE :-/

En 3h ce matin, j'ai un rendu proche de ce que vous souhaitez comme maquette : Dimensions, couleurs, polices, contenu... J’ai utilisé les blocks natifs et un simple custom CSS d’une dizaine de lignes pour tweaker les 2 ou 3 propriétés CSS manquantes dans les blocks natifs. (https://wordpress.julienweb.fr/wp-content/uploads/custom-css-js/25.css).

Il me faut plus de temps pour plusieurs points.

1) En-tête et sa navigation responsive : Adapter le responsive 
2) Bannière : c’est un élément natif WP mais il manque la propriété border-radius. J’ai utilisé un custom CSS. Autre solution, créer un custom block avec cette propriété.
3) Bloc de requête sous forme de carrousel :  c’est un élément natif WP mais il manque l'élément de pagination avant/arrière et une meilleure adaptation “responsive CSS”
4) Formulaire newsletter :  c’est un élément natif WP mais il manque la gestion dynamique de l’envoi. Solution, créer un custom block avec cette propriété.
5) Pied de page : Adapter le responsive 

Maintenant, pour finaliser, il faut savoir si je pars sur un thème enfant, je peux décliner à partir du thème natif “Twenty Twenty-Three” ou utiliser “Elementor” ou “Stackable” (Débat FSE VS Constructeur de page)

**Code custom da la page (à coller dans la home de Gutenberg) :**
```html
<!-- wp:template-part {"slug":"header","theme":"twentytwentythree","tagName":"header"} /-->

<!-- wp:spacer {"height":"80px"} -->
<div style="height:80px" aria-hidden="true" class="wp-block-spacer"></div>
<!-- /wp:spacer -->

<!-- wp:group {"tagName":"main","style":{"spacing":{"margin":{"top":"0","bottom":"0"}}},"layout":{"type":"constrained","contentSize":"80%","wideSize":"100%"}} -->
<main class="wp-block-group" style="margin-top:0;margin-bottom:0"><!-- wp:cover {"url":"http://wordpress.julienweb.fr/wp-content/uploads/2023/02/Capture-decran-2023-02-13-155555636.png","id":28,"dimRatio":40,"minHeight":570,"customGradient":"linear-gradient(135deg,rgb(7,19,53) 0%,rgb(24,56,152) 100%)","className":"wp-block-file__button","style":{"spacing":{"padding":{"top":"var:preset|spacing|70","right":"var:preset|spacing|70","bottom":"var:preset|spacing|70","left":"var:preset|spacing|70"}}}} -->
<div class="wp-block-cover wp-block-file__button" style="padding-top:var(--wp--preset--spacing--70);padding-right:var(--wp--preset--spacing--70);padding-bottom:var(--wp--preset--spacing--70);padding-left:var(--wp--preset--spacing--70);min-height:570px"><span aria-hidden="true" class="wp-block-cover__background has-background-dim-40 has-background-dim wp-block-cover__gradient-background has-background-gradient" style="background:linear-gradient(135deg,rgb(7,19,53) 0%,rgb(24,56,152) 100%)"></span><img class="wp-block-cover__image-background wp-image-28" alt="" src="http://wordpress.julienweb.fr/wp-content/uploads/2023/02/Capture-decran-2023-02-13-155555636.png" data-object-fit="cover"/><div class="wp-block-cover__inner-container"><!-- wp:group {"style":{"spacing":{"blockGap":"27px"}},"textColor":"base","layout":{"type":"flex","orientation":"vertical","justifyContent":"center"}} -->
<div class="wp-block-group has-base-color has-text-color"><!-- wp:heading {"textAlign":"center"} -->
<h2 class="wp-block-heading has-text-align-center">Visez la lune.</h2>
<!-- /wp:heading -->

<!-- wp:paragraph {"align":"center","fontSize":"medium"} -->
<p class="has-text-align-center has-medium-font-size">Lorem ipsum dolor sit amet justo hendrerit vivamus pulvinar nulla tellus morbi do cursus. Curabitur eiusmod sagittis ultricies laoreet fermentum augue iaculis lacinia bibendum aenean eiusmod lobortis.</p>
<!-- /wp:paragraph -->

<!-- wp:buttons {"layout":{"type":"flex","justifyContent":"center"}} -->
<div class="wp-block-buttons"><!-- wp:button {"style":{"border":{"radius":"100px"}},"className":"is-style-outline"} -->
<div class="wp-block-button is-style-outline"><a class="wp-block-button__link wp-element-button" style="border-radius:100px">En savoir plus</a></div>
<!-- /wp:button --></div>
<!-- /wp:buttons --></div>
<!-- /wp:group --></div></div>
<!-- /wp:cover --></main>
<!-- /wp:group -->

<!-- wp:spacer {"height":"80px"} -->
<div style="height:80px" aria-hidden="true" class="wp-block-spacer"></div>
<!-- /wp:spacer -->

<!-- wp:group {"style":{"spacing":{"blockGap":"var:preset|spacing|40"}},"layout":{"type":"constrained","contentSize":"70%"}} -->
<div class="wp-block-group"><!-- wp:heading {"style":{"typography":{"fontSize":"36px"}}} -->
<h2 class="wp-block-heading" style="font-size:36px">Toutes les infos <br>dont vous avez besoin</h2>
<!-- /wp:heading -->

<!-- wp:query {"queryId":56,"query":{"perPage":6,"pages":0,"offset":0,"postType":"post","order":"desc","orderBy":"date","author":"","search":"","exclude":[],"sticky":"","inherit":true,"parents":[]},"displayLayout":{"type":"flex","columns":3},"layout":{"type":"constrained","contentSize":"100%"}} -->
<div class="wp-block-query"><!-- wp:post-template -->
<!-- wp:group {"style":{"spacing":{"blockGap":"10px"}},"layout":{"inherit":false}} -->
<div class="wp-block-group"><!-- wp:post-featured-image /-->

<!-- wp:post-title {"level":4,"isLink":true} /-->

<!-- wp:post-date {"format":"d M. Y","isLink":true,"style":{"color":{"text":"#71717a"}}} /--></div>
<!-- /wp:group -->
<!-- /wp:post-template --></div>
<!-- /wp:query -->

<!-- wp:query-pagination {"paginationArrow":"chevron","layout":{"type":"flex","justifyContent":"right"}} -->
<!-- wp:query-pagination-previous /-->

<!-- wp:query-pagination-next /-->
<!-- /wp:query-pagination --></div>
<!-- /wp:group -->

<!-- wp:spacer {"height":"80px"} -->
<div style="height:80px" aria-hidden="true" class="wp-block-spacer"></div>
<!-- /wp:spacer -->

<!-- wp:cover {"dimRatio":0,"customOverlayColor":"#ffffff","minHeightUnit":"vh","contentPosition":"center center","isDark":false,"align":"full"} -->
<div class="wp-block-cover alignfull is-light"><span aria-hidden="true" class="wp-block-cover__background has-background-dim-0 has-background-dim" style="background-color:#ffffff"></span><div class="wp-block-cover__inner-container"><!-- wp:media-text {"mediaId":69,"mediaLink":"https://wordpress.julienweb.fr/capture-decran-2023-02-14-113423/","mediaType":"image","verticalAlignment":"center","imageFill":true} -->
<div class="wp-block-media-text alignwide is-stacked-on-mobile is-vertically-aligned-center is-image-fill"><figure class="wp-block-media-text__media" style="background-image:url(https://wordpress.julienweb.fr/wp-content/uploads/2023/02/Capture-decran-2023-02-14-113423.png);background-position:50% 50%"><img src="https://wordpress.julienweb.fr/wp-content/uploads/2023/02/Capture-decran-2023-02-14-113423.png" alt="" class="wp-image-69 size-full"/></figure><div class="wp-block-media-text__content"><!-- wp:spacer {"height":"120px"} -->
<div style="height:120px" aria-hidden="true" class="wp-block-spacer"></div>
<!-- /wp:spacer -->

<!-- wp:heading {"textAlign":"center","style":{"typography":{"fontSize":"48px"},"color":{"text":"#000000"}}} -->
<h2 class="wp-block-heading has-text-align-center has-text-color" style="color:#000000;font-size:48px"><strong>Prêts à faire passer votre business au niveau supérieur ?</strong></h2>
<!-- /wp:heading -->

<!-- wp:buttons {"layout":{"type":"flex","justifyContent":"center"}} -->
<div class="wp-block-buttons"><!-- wp:button {"textColor":"base","style":{"color":{"background":"#1d4ed8"},"border":{"radius":"100px"}},"className":"is-style-fill"} -->
<div class="wp-block-button is-style-fill"><a class="wp-block-button__link has-base-color has-text-color has-background wp-element-button" style="border-radius:100px;background-color:#1d4ed8">Bisous, je m’envole !</a></div>
<!-- /wp:button --></div>
<!-- /wp:buttons -->

<!-- wp:spacer {"height":"120px"} -->
<div style="height:120px" aria-hidden="true" class="wp-block-spacer"></div>
<!-- /wp:spacer --></div></div>
<!-- /wp:media-text --></div></div>
<!-- /wp:cover -->

<!-- wp:spacer {"height":"80px"} -->
<div style="height:80px" aria-hidden="true" class="wp-block-spacer"></div>
<!-- /wp:spacer -->

<!-- wp:group {"align":"wide","layout":{"type":"constrained","wideSize":"60%"}} -->
<div class="wp-block-group alignwide"><!-- wp:heading {"textAlign":"center","level":4,"style":{"typography":{"fontSize":"30px","fontStyle":"normal","fontWeight":"600"}}} -->
<h4 class="wp-block-heading has-text-align-center" style="font-size:30px;font-style:normal;font-weight:600"><strong>Telescope, dans votre boîte mail.</strong></h4>
<!-- /wp:heading -->

<!-- wp:paragraph {"align":"center","style":{"spacing":{"margin":{"top":"var:preset|spacing|30","right":"var:preset|spacing|30","bottom":"var:preset|spacing|30","left":"var:preset|spacing|30"}}},"fontSize":"small"} -->
<p class="has-text-align-center has-small-font-size" style="margin-top:var(--wp--preset--spacing--30);margin-right:var(--wp--preset--spacing--30);margin-bottom:var(--wp--preset--spacing--30);margin-left:var(--wp--preset--spacing--30)">Lorem ipsum dolor sit amet, consectetur adipiscing elit. Morbi eros quam, convallis ac ullamcorper vel, tempor non nibh. Aenean eget lobortis odio. Nullam maximus vestibulum mauris non faucibus.</p>
<!-- /wp:paragraph -->

<!-- wp:group {"align":"wide","layout":{"type":"constrained","wideSize":"60%"}} -->
<div class="wp-block-group alignwide"><!-- wp:search {"label":"Search","showLabel":false,"placeholder":"Votre e-mail","width":100,"widthUnit":"%","buttonText":"Je m'inscris","buttonPosition":"button-inside","style":{"border":{"radius":"100px","color":"#71717a","width":"1px"},"color":{"background":"#1d4ed8"}},"textColor":"base","fontSize":"medium"} /--></div>
<!-- /wp:group --></div>
<!-- /wp:group -->

<!-- wp:spacer {"height":"80px"} -->
<div style="height:80px" aria-hidden="true" class="wp-block-spacer"></div>
<!-- /wp:spacer -->

<!-- wp:separator {"style":{"color":{"background":"#f4f4f5"}},"className":"is-style-wide"} -->
<hr class="wp-block-separator has-text-color has-alpha-channel-opacity has-background is-style-wide" style="background-color:#f4f4f5;color:#f4f4f5"/>
<!-- /wp:separator -->

<!-- wp:group {"align":"full","style":{"spacing":{"padding":{"top":"4em","bottom":"0em"}},"elements":{"link":{"color":{"text":"var:preset|color|contrast"}}}},"backgroundColor":"base","textColor":"contrast","className":"full-border","layout":{"type":"default"}} -->
<div class="wp-block-group alignfull full-border has-contrast-color has-base-background-color has-text-color has-background has-link-color" style="padding-top:4em;padding-bottom:0em"><!-- wp:columns -->
<div class="wp-block-columns"><!-- wp:column {"width":"413px","style":{"spacing":{"padding":{"top":"0","right":"0","bottom":"0","left":"0"}}}} -->
<div class="wp-block-column" style="padding-top:0;padding-right:0;padding-bottom:0;padding-left:0;flex-basis:413px"><!-- wp:site-logo {"width":200} /--></div>
<!-- /wp:column -->

<!-- wp:column -->
<div class="wp-block-column"><!-- wp:paragraph {"style":{"typography":{"fontSize":"18px"}}} -->
<p style="font-size:18px"><strong>A propos</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><a href="#"><a href="#">Facebook</a><br><a href="#">Instagram</a><br><a href="#">Twitter</a><br>Contact</a></p>
<!-- /wp:paragraph --></div>
<!-- /wp:column -->

<!-- wp:column -->
<div class="wp-block-column"><!-- wp:paragraph {"style":{"typography":{"fontSize":"18px"}}} -->
<p style="font-size:18px"><strong>Produit</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><a href="#">Facebook</a><br><a href="#">Instagram</a><br><a href="#">Twitter</a><br>Contact</p>
<!-- /wp:paragraph --></div>
<!-- /wp:column -->

<!-- wp:column -->
<div class="wp-block-column"><!-- wp:paragraph {"style":{"typography":{"fontSize":"18px"}}} -->
<p style="font-size:18px"><strong>Ressources</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><a href="#">Facebook</a><br><a href="#">Instagram</a><br><a href="#">Twitter</a><br>Contact</p>
<!-- /wp:paragraph --></div>
<!-- /wp:column -->

<!-- wp:column -->
<div class="wp-block-column"><!-- wp:paragraph {"style":{"typography":{"fontSize":"18px"}}} -->
<p style="font-size:18px"><strong>Suivez-nous</strong></p>
<!-- /wp:paragraph -->

<!-- wp:social-links {"iconColor":"contrast","iconColorValue":"#000000","size":"has-normal-icon-size","className":"is-style-logos-only","layout":{"type":"flex","justifyContent":"left"}} -->
<ul class="wp-block-social-links has-normal-icon-size has-icon-color is-style-logos-only"><!-- wp:social-link {"url":"https://wordpress.julienweb.fr/","service":"facebook"} /-->

<!-- wp:social-link {"url":"https://wordpress.julienweb.fr/","service":"instagram"} /-->

<!-- wp:social-link {"url":"https://wordpress.julienweb.fr/","service":"twitter"} /-->

<!-- wp:social-link {"url":"https://wordpress.julienweb.fr/","service":"twitch"} /--></ul>
<!-- /wp:social-links --></div>
<!-- /wp:column --></div>
<!-- /wp:columns -->

<!-- wp:group {"align":"full","style":{"spacing":{"padding":{"top":"2.4em","bottom":"2em"}}},"layout":{"inherit":false}} -->
<div class="wp-block-group alignfull" style="padding-top:2.4em;padding-bottom:2em"><!-- wp:paragraph {"align":"center","style":{"elements":{"link":{"color":{"text":"var:preset|color|cyan-bluish-gray"}}}},"textColor":"cyan-bluish-gray","fontSize":"small"} -->
<p class="has-text-align-center has-cyan-bluish-gray-color has-text-color has-link-color has-small-font-size">Proudly powered by <a href="https://wordpress.org">WordPress</a> &amp; <strong><a rel="noreferrer noopener" href="https://julienweb.fr/" target="_blank">julienweb.fr</a></strong> Work in progress... 13/02/2023</p>
<!-- /wp:paragraph --></div>
<!-- /wp:group --></div>
<!-- /wp:group -->
```

**Code de l’entête de nav-bar (FSE) :**

```html
<!-- wp:group {"layout":{"type":"constrained","wideSize":"100%","contentSize":"80%"}} -->
<div class="wp-block-group"><!-- wp:columns {"style":{"spacing":{"padding":{"top":"0","right":"0","bottom":"0","left":"0"}}},"fontSize":"medium"} -->
<div class="wp-block-columns has-medium-font-size" style="padding-top:0;padding-right:0;padding-bottom:0;padding-left:0"><!-- wp:column {"verticalAlignment":"center","width":"25%"} -->
<div class="wp-block-column is-vertically-aligned-center" style="flex-basis:25%"><!-- wp:site-logo {"width":175,"shouldSyncIcon":true,"align":"left"} /--></div>
<!-- /wp:column -->

<!-- wp:column {"verticalAlignment":"center","width":"50%"} -->
<div class="wp-block-column is-vertically-aligned-center" style="flex-basis:50%"><!-- wp:navigation {"ref":14,"layout":{"type":"flex","justifyContent":"center"}} /--></div>
<!-- /wp:column -->

<!-- wp:column {"width":"25%"} -->
<div class="wp-block-column" style="flex-basis:25%"><!-- wp:buttons {"layout":{"type":"flex","justifyContent":"right","flexWrap":"nowrap"}} -->
<div class="wp-block-buttons"><!-- wp:button {"textColor":"base","width":75,"style":{"color":{"background":"#1d4ed8"},"border":{"radius":"100px"}},"fontSize":"small"} -->
<div class="wp-block-button has-custom-width wp-block-button__width-75 has-custom-font-size has-small-font-size"><a class="wp-block-button__link has-base-color has-text-color has-background wp-element-button" style="border-radius:100px;background-color:#1d4ed8">Contact</a></div>
<!-- /wp:button --></div>
<!-- /wp:buttons --></div>
<!-- /wp:column --></div>
<!-- /wp:columns --></div>
<!-- /wp:group -->
```

**Custom CSS :**
https://fr.wordpress.org/plugins/custom-css-js/ 

```css
@import url('https://fonts.googleapis.com/css2?family=Inter:wght@400;600&family=Work+Sans:wght@500;600&display=swap');

*, p { font-family: 'Inter', sans-serif; }

.wp-block-cover .wp-block-cover__image-background,
.wp-block-cover video.wp-block-cover__video-background,
.wp-block-cover-image .wp-block-cover__image-background,
.wp-block-cover-image video.wp-block-cover__video-background,
.wp-block-cover .has-background-dim.has-background-gradient,
.wp-block-cover-image .has-background-dim.has-background-gradient {
    border-radius: 20px;
}

time a {
	color:#71717A;
}

.wp-site-blocks > hr {
    max-width: 100%;
    margin: auto;
}

.wp-block-search__inside-wrapper {
	line-height: 100%;
}

h2 {
    font-family: 'Work Sans', sans-serif;
	font-weight: 600!important;
	font-size: 36px;
	line-height: 56px;
}

h4, h4 a {
	font-weight: 600!important;
	font-size: 20px;
	line-height: 23px;
}

.wp-site-blocks > * {
    max-width: 1280px;
    margin: auto;
}

.full-border a {
	text-decoration: none;
}
```

**Liste de ressources dont je me sers pour développer :**

 + CORE1 https://github.com/WordPress/gutenberg
 + CORE2 https://github.com/WordPress/gutenberg/tree/HEAD/packages/block-library/src
 + LIST https://wordpress.org/plugins/browse/block/
 + PATTERNS https://wordpress.org/patterns/ + https://wordpress.org/patterns/new-pattern/
 + PATERNS DOC https://learn.wordpress.org/lesson-plan/how-to-use-wordpress-block-patterns/
 + REUSABLE https://wordpress.org/documentation/article/reusable-blocks/
 + GROUP https://wordpress.org/documentation/article/group-block/  
 + DEV https://github.com/Automattic/block-experiments
 + STORYBOOK https://wordpress.github.io/gutenberg/?path=/story/docs-introduction--page
 + TUTO https://github.com/WordPress/gutenberg/blob/trunk/docs/getting-started/create-block/README.md  
 + INFO https://wordpress.org/gutenberg/
 + DOC1 https://developer.wordpress.org/block-editor/
 + DOC2 https://github.com/WordPress/gutenberg/tree/trunk/docs/how-to-guides/block-tutorial
 + DOC3 https://developer.wordpress.org/block-editor/how-to-guides/javascript/js-build-setup/
 + DOC4 https://github.com/WordPress/gutenberg/blob/trunk/docs/getting-started/create-block/README.md  
 + VALIDATE https://wordpress.org/plugins/developers/block-plugin-validator/
 + ADD https://make.wordpress.org/plugins/2020/07/11/you-can-now-add-your-own-plugins-to-the-block-directory/