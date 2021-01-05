
```php
function showMainMenu($menu, $options='', $c_active=''){

    /*
      * This condition checks whether the submenu exists or not.
      * if submenu exists then it'll open <ul> tag with dropdown-menu class
      * otherwise it'll open <ul> tag with nav navbar-nav class
    */							
	if($options == 1){                           
		echo '<ul class="dropdown-menu">'; 
	}else{                                    
		echo '<ul class="nav navbar-nav">';
	}
	
	
	/* foreach loop is mainly used for looping through the $i => $item of $menu */
	foreach($menu as $i => $item){
		
		$lnk = $item['m_alias'];       
		
       /* if $item[m_view] is equals to category then it assgin $item['m_link'] value to the $lnk variable */

		if($item['m_view'] == 'category'):  
			$lnk = $item['m_link'];      
		endif;

		/*
            * if $item['submenu'] is not empty then $option will be true means 1.
            * then it'll open <li> tag with `dropdown` class and <a> tag with `dropdown-toggle` class and print $item['m_title']

            * if again $item['m_alias'] equals to home, then it'll open <li> and <a> tag and print $item['m_title']

            * if again $c_active equals to  $item['m_alias'], then it'll open <li> with active class and <a> tag and print $item['m_title']

            * otherwise it'll open <li> and <a> tag and print $item['m_title']
		*/
		
		if( !empty($item['submenu']) ):  
			$options=1;          

			echo '<li class="dropdown"><a  class="dropdown-toggle" data-toggle="dropdown" href="#">' . $item['m_title'] . ' <span class="caret"></span></a>';

		elseif($item['m_alias'] == 'home'):      
			echo ' <li><a href="'.base_url().'">' . $item['m_title'] . '</a>';

		elseif($c_active == $item['m_alias']):    
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