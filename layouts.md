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


## blog


