## Theme Functions.
 * [Menu Bars](theme-functions.md#menu)
 * [Images](theme-functions.md)


## Menu

### showMainMenu($menu, $option, $active )
 * $menu {array} - formatted multidimentional associative array.
 * $option { string | array | optional }  - any defined option.
 * $active { string | optional } - current menu to set active menu style.

It is a theme function.

```html
<nav class="navbar navbar-expand main-menu">				  
	<div class="collapse navbar-collapse justify-content-end top-nav">		
		<?php 
			showMainMenu($menuArray, array('submenu'=> FALSE), segment(1) );
		?>
	</div>																
</nav>
```

## Image

### featuredimg($images, $title, $withimgtag, $single)
 * $images {string} - 
 * $title {string} (Optional) - 
 * $withimgtag {string} (Optional) - 
 * $single {string} (Optional) - 
 
 
