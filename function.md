# List of function


## showMainMenu

This function is used for calling main menu

```html
<!-- main menu -->
<div class="col col-md-9 menu-col">		  		 
    <nav class="navbar navbar-expand main-menu">				  
	    <div class="collapse navbar-collapse justify-content-end top-nav">		
			<?php
				showMainMenu($menuArray, array('submenu'=>FALSE), segment(1));
			?>
	    </div>																
    </nav>
</div>
<!-- end: main menu-->
```

?>showMainMenu($menuArray, array('submenu'=>FALSE), segment(1));


<br>
<strong>Parameter</strong>

<ul>
	<li><strong>$menuArray</strong> is a multidimensional associative array</li>
	<li><strong>array(‘submenu’=>false)</strong> is also a associative array that check main menu has a submenu or not. Initially submenu assign a false value.</li>
	<li><strong>segment(n)</strong> allow to retrieve a specific segment form URI string where (n) is a segment number. Segments are numbered from left to right.</li>
</ul>


<br>
<strong>Example</strong><br>

**http://www.domainname.com/index.php/blog/language/php/function**

```php 
echo $this->uri->segment(1);       //it will print blog
```  

```php
echo $this->uri->segment(2);       //it will print language
```


<br>
<strong>How it Works</strong>

```php
function showMainMenu($menu, $options='', $c_active=''){

	if($options == 1){             /* if submenu exists then it'll open <ul> tag with .dropdown-menu or <ul> tag with .anv .navbar-nav class*/             
		echo '<ul class="dropdown-menu">'; 
	}else{                                    
		echo '<ul class="nav navbar-nav">';
	}

	foreach($menu as $i => $item){
		$lnk = $item['m_alias']; 

		if($item['m_view'] == 'category'):  //if value of m_view equals to category then m_link value will be assign in $lnk variable
			$lnk = $item['m_link'];      
		endif;

		if( !empty($item['submenu']) ):   //if submenu is not empty it'll open <li> with .dropdown and <a> with .dropdown-toggle 
			$options=1;          
			echo '<li class="dropdown"><a  class="dropdown-toggle" data-toggle="dropdown" href="#">' . $item['m_title'] . ' <span class="caret"></span></a>';

		elseif($item['m_alias'] == 'home'):    //if m-alias equals to home, then it'll open <li> and <a> tag      
			echo ' <li><a href="'.base_url().'">' . $item['m_title'] . '</a>';

		elseif($c_active == $item['m_alias']):    //if $c_item equals to $item['m_alias'] then it'll open <li> with .active and <a> tag
			echo ' <li class="active"><a href="'.base_url().$lnk.'">' . $item['m_title'] . '</a>';

		else:                             //otherwise it'll open <li> then <a> tag
			echo ' <li><a href="'.base_url().$lnk.'">' . $item['m_title'] . '</a>';
		endif;


		if( !empty($item['submenu']) ){	   //If submenu is not empty then again it calls showMainMenu() function											
			showMainMenu($item['submenu'],$options, $c_active);
		}						
		echo '</li> ';
	}
	echo '</ul>';					
}
```


## showfooterMenu

```php
/* Footer Menu */
function showfooterMenu($menu , $dropdown = FALSE){
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
/* Footer Menu */
```

?>showfooterMenu($item['submenu']);

<br>
<strong>How it works</strong>



## showsideMenu

```php
function showsideMenu($menu,$dropdown = FALSE){
	echo '<ul class="footer-menu">';
		foreach($menu as $i => $item){
				echo ' <li><a href="'.base_url().$item['m_alias'].'">' . $item['m_title'] . '</a>';				
			if( !empty($item['submenu']) ){												
				showsideMenu($item['submenu']);
			}						
			echo '</li> ';
		}
	echo '</ul>';		
}
```


## featuredimg

```php

function featuredimg($imgs, $title='', $withimgtag = TRUE, $single = TRUE){		 
	if(preg_match('/|/',$imgs)){       // if $imgs match with `|`

		$p_image = explode('|',$imgs);     //Then `|` will tranform into array
				
		if($single){        //if it is a single image, then it'll enter into next condition

			if($withimgtag){     //if image is with a tag then it'll return <img> tag with title or return no image
				return "<img title='".$title."' src='".$p_image[0]."' />"; 
			}else{
				return $p_image[0];
			}

		}else{           //If it is not a single image, then $imgs will be empty array

			$imgs='';

			foreach($p_image as $img){
				//$imgs.="<img title='".$title."' src='".$img."' />";
				$imgs.='<li><a data-image="'.$img.'" href="#"><img alt="" src="'.$img.'" /></a></li>';
			}
			return $imgs;	 //return more than one image
		}								
	}else{    // if $imgs does not match with `|`

		if($withimgtag){
			return "<img title='".$title."' src='".$imgs."' />";
		}else{
			return $imgs;
		}
	}		
}
```


## share

```php
 function share($content){				
	if(count($content) == 1 ):
		
	echo '<a href="http://twitter.com/share?text='.$content[0]['title'].'&url='.base_url().'a/'.$content[0]['alias'].'" target="_blank"><i class="fa fa-twitter fa-lg"></i></a>

		<a href="http://www.facebook.com/sharer.php?u='.base_url().'a/'.$content[0]['alias'].'" target="_blank"><i class="fa fa-facebook-square fa-lg"></i></a>

		<a href="https://www.linkedin.com/shareArticle?mini=true&url='.base_url().'term/'.$content[0]['alias'].'&title='.$content[0]['title'].'" target="_blank"><i class="fa fa-linkedin-square fa-lg"></i></a>

		<a href="https://plus.google.com/share?url='.base_url().'a/'.$content[0]['alias'].'" target="_blank"><i class="fa fa-google-plus-square fa-lg"></i></a>';

	endif;
}
```


## index

```php
function index($content, $menucheck, $cat_list='', $breadcrumb='', $content_type='', $rating=''){
    $cnt=1;
	$cnt_1=1;
	$ac="active";		
	
	if(count($content)>0):			
	
	if(count($content) == 1 && $content_type!='multi'):
		echo '<article id="article-post"><div class="head-image thumb-wrap relative">';
		echo "<header>";
			content_util();
		echo "<div class=breadcrumb>".$breadcrumb."</div>";			
		echo '<span itemscope= itemtype="http://schema.org/WebPage">'; // SEO			
		echo '<h1 itemprop="name">'.$content[0]['title'].'</h1>';						
		echo '<span itemprop="starRating" itemscope itemtype="http://schema.org/Rating">'; //SEO
		echo "<div class='show-rate' style='clear:both; height:30px;'>".$rating."</div>";
		echo '</span></span>';
				
		//echo '<div style="width:100%; height:90px; background:#f7f7f7; margin-bottom:10px">Ads</div>';
		
		echo '</header>';
		
		if(!empty($content[0]['featuredimg'])):
        echo '<a href="'.base_url().$content[0]['cat_alias'].'/'.$content[0]['alias'].'"><img src="'.$content[0]['featuredimg'].'" alt="'.$content[0]['title'].'" class="img-responsive" /></a>';			          
		endif;			
					
		echo '<div class="fulltext">'.$content[0]['fulltexts'].'</div>';					
													
		echo "</article>";		
		
	 endif;
				
		
	else:
		echo '<p class="alert alert-warning"><i class="fa fa-exclamation-triangle"></i> Sorry There is no item under this category!</p>';
	endif;	
}
```

## isset() 

Check whether a variable is empty. Also check whether the variable is set/declared



## form_open()

<h4>Parameters</h4>

**$action (string)** – Form action/target URI string (action=” http://localhost:8080/search”)

**$attributes (mixed)** – HTML attributes, as an array or escaped string (id, class, style)

**$hidden (array)** – An array of hidden fields’ definitions

<h4>Returns</h4>
An HTML form opening tag 



## form_input()

<h4>Parameters</h4>

**$data (array)** – Field attributes data

**$value (string)** – Field value

**$extra (mixed)** – Extra attributes to be added to the tag either as an array or a literal string

**$type (string)** – The type of input field. i.e. ‘text’, ‘email’, ‘number’, etc.

<h4>Returns</h4>
An HTML text input field tag



## form_dropdown()  

<h4>Parameters</h4>

**$name (string)** – Field name

**$options (array)** – An associative array of options to be listed

**$selected (array)** – List of fields to mark with the selected attribute

**$extra (mixed)** – Extra attributes to be added to the tag either as an array or a literal string

<h4>Returns</h4>
An HTML dropdown select field tag



## set_value()

<h5>Parameters</h5>

**$field (string)** – Field name

**$default (string)** – Default value

**$html_escape (bool)** – Whether to turn off HTML escaping of the value

<h5>Returns</h5> 
Field value


## listError() 

Returns an array of all the errors logged in the system




