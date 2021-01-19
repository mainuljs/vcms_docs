# Menu Bars

## showMainMenu($menu, $options='', $c_active='')
* $menu - $menu is a multidimentional associative array. It has several key like - **m_title** , **m_link** , **m_id** , **parent** , **m_alias** , **m_view** , **submenu**
* $option - $option is boolean data type. It returns `true or false`. If submenu exists then return true or return false.
* $c_active - It return uri

> This function is used to call main menu.Returns main menu.

**How to use**
```php
showMainMenu($menuArray, array('submenu'=>FALSE), segment(1));
```

**How function works**

```php
function showMainMenu($menu, $options='', $c_active=''){
									
	if($options==1){
		echo '<ul class="dropdown-menu">';
	}else{
		echo '<ul class="nav navbar-nav">';
	}
	
	foreach($menu as $i => $item){
		
		$lnk=$item['m_alias'];
		
		if($item['m_view']=='category'):
			$lnk=$item['m_link'];
		endif;
		
		if( !empty($item['submenu']) ):
			$options=1;
			echo '<li class="dropdown"><a  class="dropdown-toggle" data-toggle="dropdown" href="#">' . $item['m_title'] . ' <span class="caret"></span></a>';
		elseif($item['m_alias']=='home'):
			echo ' <li><a href="'.base_url().'">' . $item['m_title'] . '</a>';
		elseif($c_active==$item['m_alias']):
			echo ' <li class="active"><a href="'.base_url().$lnk.'">' . $item['m_title'] . '</a>';
		else:
			echo ' <li><a href="'.base_url().$lnk.'">' . $item['m_title'] . '</a>';
		endif;					
		if( !empty($item['submenu']) ){												
			showMainMenu($item['submenu'],$options, $c_active);
		}						
		echo '</li> ';
	}
	echo '</ul>';					
}
```

<br>

## showsideMenu($menu,$dropdown=FALSE)
* $menu is a multidimentional associative array
* $dropdown is a boolean data.It returns true or false.
> For side menu we need to call `showsideMenu()` function

**How to use**
```php
showsideMenu($menu,$dropdown=FALSE);
```

**How function works**
```php
function showsideMenu($menu,$dropdown=FALSE){
	echo '<ul class="footer-menu">';
	foreach($menu as $i => $item){
			echo ' <li><a href="'.base_url().$item['m_alias'].'">' . $item['m_title'] . '</a>';				
		if( !empty($item['submenu']) ){												
			showfooterMenu($item['submenu']);
		}						
		echo '</li> ';
	}
	echo '</ul>';		
}
```


## Footer Menu
> For side menu we need to call `showfooterMenu()` function

**How function works**
```php
function showfooterMenu($menu,$dropdown=FALSE){
	echo '<ul class="footer-menu">';
	foreach($menu as $i => $item){
			echo ' <li><a href="'.base_url().$item['m_alias'].'">' . $item['m_title'] . '</a>';				
		if( !empty($item['submenu']) ){												
			showfooterMenu($item['submenu']);
		}						
		echo '</li> ';
	}
	echo '</ul>';		
}
```