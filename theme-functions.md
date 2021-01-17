## Theme Functions.
 * [Menu Bars](theme-functions.md#menu)
 * [Images](theme-functions.md)


## Menu

### showMainMenu($menu, $option, $active )
 * @param {array} $menu - formatted multidimentional associative array.
 * @param {string | array | optional} $option - any defined option.
 * @param {string | optional} $active - current menu to set active menu style.

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
