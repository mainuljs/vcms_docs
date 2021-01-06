# Layouts

## Header

### Top Header

```html
<!-- top header -->
<section class="container-fluid top-header-two">
	<div class="container">
		<div class="row">
			<div class="col-4 col-md-3 head-icon">
				<a href="#"><span class="fa fa-facebook"> </span> </a>
				<a href="#"><span class="fa fa-twitter"> </span> </a>
				<a href="#"><span class="fa fa-linkedin"> </span> </a>
			</div>
		    <div class="col-8 col-md-9 last pl-0">
				<span class="fa fa-phone"></span><a class="" href="tel:2123865575"> 212 386 5575</a>&nbsp;&nbsp;&nbsp;
				<span class="fa fa-envelope"> </span> admin@email.com
			</div>
		</div>
	</div>
</section>
<!-- end: top header --->
```

### Main Header

#### Main Menu

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

#### Search Box

```html
<!-- top search -->
<div class="col col-md-1 search-col">		
    <div class="top-search">
		<a href="#"><span class="material-icons">search</span></a>
		<div class="search-box">
			<form action="<?php echo base_url('search'); ?>" method="post" class="form-inline">
				<div class="input-group flex-fill">
					<input type="text" name="key_word" class="form-control" placeHolder="Your Keyword" />				
					<div class="input-group-append">
					    <button class="btn btn-info" type="submit">Go</button>
					</div>	
				</div>				
			</form>													
		</div>
	</div>		  
</div>
<!-- end: top search-->
```



## Footer

### Footer Top

#### Site map

```html
<div class="col-md-4">             			
	<h3><i class="fa fa-sitemap" aria-hidden="true"></i> Sitemap</h3>
	<ul class="footer-menu"> 		
		<li><a href="<?php echo base_url(); ?>business-studies">Home </a></li> 
		<li><a href="<?php echo base_url(); ?>computer-science">Service</a></li>  
		<li><a href="<?php echo base_url(); ?>medical-Health-science">Blog</a></li>
		<li><a href="<?php echo base_url(); ?>medical-Health-science">Contact</a></li>
	</ul>  
</div>
```

#### Newsletter

```html
<div class="col-md-4">  
	<h3><i class="material-icons">email</i> Newsletter</h3>										
	<div class="pmgs"></div>
	<div class="subscribe"></div>	
</div> 
```

#### Contact

```html
<div class="col-md-4">
	<h3> <i class="material-icons">explore</i> Stay in Touch</h3>
    <ul class="footer-menu"> 
		<li><i class="fa fa-home"></i> Medico Bibendum auctor, nisi elit consequat ipsum, nec sagittis sem</li>			
		<li> <i class="fa fa-map-marker"></i> Medicom Ltd, Manhattan 1258, New York, USA Lahore</li>							
		<li> <i class="fa fa-mobile"></i> (+1) 234 567 8901</li>
    </ul>
	<div class="social-icons">		  
	    <a href=""><i class="fa fa-twitter fa-lg"></i></a>
	    <a href=""><i class="fa fa-facebook-square fa-lg"></i></a>
	    <a href=""><i class="fa fa-linkedin-square fa-lg"></i></a>
	    <a href=""><i class="fa fa-google-plus-square fa-lg"></i></a>
	    <a href=""><i class="fa fa-vimeo-square fa-lg"></i></a>
	    <a href=""><i class="fa fa-youtube fa-lg"></i></a>
	</div>
</div>
```

### Footer bottom

```html
<div class="col-md-12 copyright">									   
	<span>&copy; <?php echo YEAR; ?> <a href="<?php echo base_url(); ?>"> <?php echo $siteUrl; ?> </a> All Rights Reserved.</span> </p>	
</div>
```

## Carousel

```html
<?php if($home && isset($slider_cat) && !empty($slider_cat)): ?>
<div class="container-fluid slider-one">
    <div class="row">
        <div id="carousel" class="carousel slide carousel-fade" data-ride="true" data-interval="false" style="width: 100%;">
            <ol class="carousel-indicators">
				<?php 
				   	$i = 0;
				   	foreach($slider_cat[0] as $slide ):
						if($i == 0):
							echo '<li data-target="#carousel" data-slide-to="'.$i.'" class="active"></li>';		
						else:
						 	echo '<li data-target="#carousel" data-slide-to="'.$i.'"></li>';
						endif;
						$i++;
					endforeach;
				?>		
             </ol>
	  
	        <div class="carousel-inner">         
				<?php 
				 	count($slider_cat);
				 		
					foreach($slider_cat as $slide ):
					$cnt_slide = 1;
					$cnt_slide1 = 1;
					if( is_array($slide) ):
						foreach($slide as $sld):
							if($cnt_slide == 1):
								echo '<div class="carousel-item active">';
							else:
								echo '<div class="carousel-item">';
							endif;
							
							echo '<img class="d-block" src="'.$sld['featuredimg'].'" alt="'.$sld['title'].'" />';

							echo '<div class="carousel-caption d-md-block"><h3 class="animate__animated animate__slideInDown">'.$sld['title'].'</h3><p>'.$sld['introtext'].'</p><br />';

							echo '<a class="btn btn-default animate__animated animate__slideInUp" href="'.base_url($sld['alias']).'">View <i class="material-icons">keyboard_arrow_right</i></a></div>';								
							
							echo '</div>';
									
							$cnt_slide++;	
																		
						endforeach;	
					 endif;
					endforeach;
				?> 
            </div>
                                                
		    <a class="carousel-control-prev" href="#carousel" role="button"  data-slide="prev">
		        <span class="fa fa-chevron-left" aria-hidden="true"></span>
		        <span class="sr-only">Previous</span>
		    </a>
		    <a class="carousel-control-next" href="#carousel" role="button"  data-slide="next">
		        <span class="fa fa-chevron-right" aria-hidden="true"></span>
		        <span class="sr-only">Next</span>
		    </a>
        </div>
	</div>
</div>

<?php endif; ?>  
```


## blog

```php
<div class="container-fluid" style="margin-top:20px">
	<div class="container">
		<div class="row">
				<!--<h2 class="section-title">From The Blog</h2>-->				
				<?php  																			
					  if(isset($blog_cat) && !empty($blog_cat) ):	
					 	$s=1;
						foreach($blog_cat as $item):
							
							$string = $item['created_at'];
							$timestamp = strtotime($string);
							
							echo '<div class="col-md-4"><article class="blog-item"><div class="blog-thumbnail">';

							echo featuredimg($item['featuredimg'],$item['title']);

							echo '<div class="blog-date"> <p class="day">'.date("d", $timestamp).'</p><p class="monthyear">'.date("M", $timestamp).' '.date("Y", $timestamp).'</p></div></div>';

							echo '<div class="blog-content"><h4 class="blog-title"><a href="'.base_url('blog/'.$item['alias']).'">'.$item['title'].'</a></h4>';

							//echo '<p class="blog-meta">By: <a href="#">admin</a> | Tags: <a href="#">Graphic</a>, <a href="#">illustration</a>, <a href="#">Logo</a></p>';

							echo '<p>'.text_num($item['introtext'], 120).'</p>';
							echo '<a href="'.base_url('blog/'.$item['alias']).'" class="btn btn-default btn-mini">READ MORE &nbsp;<i class="fa fa-angle-right"></i></a></div></article></div>';
																											
							$s++;		  			  
						endforeach;
						
					endif;	
				?>					
	    </div>
    </div>
</div>
```

<br>
<strong>variables</strong>

<li>$blog_cat</li>

```php
[0] => Array
        (
            [title] => Creative Team
            [introtext] => 
            [created_at] => 2020-11-25 06:11:00
            [cat_title] => Blog
            [catlead] => 0
            [featuredimg] => http://localhost:8080/images/banner/banner1.jpg
            [alias] => team
            [cat_alias] => blog
        )
```



