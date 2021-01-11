# Sliders

``` html
<?php if($home && isset($slider_cat) && !empty($slider_cat)): ?>
<div class="container-fluid slider-one">
    <div class="row">
        <div id="carousel" class="carousel slide carousel-fade" data-ride="true" data-interval="false" >
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