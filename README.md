# CSS stuff
	install sass to edit .scss files 
	when new .scss is created, need to add two css files which under .scss to git

# CSS Selector
	div > p : select all p where parent is a div

# Css Position
  	position: static will put div next to the element in another div
  
# CSS and JS Cache Issue
	  .css/.js?v=1:1, add <?= rand() ?> to the stylesheet link<> to clear the cache
  
# CSS Responsive
	@media (min-width:991) {
  	.mobile_display {
    	display:none
  	}
	}
	screen size larger than 991px will display none
	main, 991px, 767px must include the same class name to do style at different width.

# CSS responsive image
	php hard code, use http://www.responsivebreakpoints.com/ to generate responsive image
	<img
									sizes="(max-width: 728px) 100vw, 728px"
									srcset="
	<?php echo get_template_directory_uri(); ?>/.../../...,w_200.jpg 200w,
	<?php echo get_template_directory_uri(); ?>/.../../...,w_392.jpg 392w,
	<?php echo get_template_directory_uri(); ?>/.../../...,w_542.jpg 542w,
	<?php echo get_template_directory_uri(); ?>/.../../...,w_661.jpg 661w,
	<?php echo get_template_directory_uri(); ?>/.../../...,w_728.jpg 728w"
									src="<?php echo get_template_directory_uri(); ?>/.../../...,w_728.jpg"
									alt="...">


# JS 遍历+查找
	<script>

	   jQuery(document).ready(function(){


		jQuery('.A').each(function(){
		    var highestBox = 0;
		    jQuery(this).find('.B .C').each(function () {
			    if (jQuery(this).height() > highestBox) {
				highestBox = jQuery(this).height();
			    }
			}).height(highestBox);
		});
	});

	</script>
# JS responsive change height and resize
	+<script>
	+
	+function call(){
	+    var w = jQuery(window).width();
	+    if(w > 767) {
	+
	+        jQuery('.A').each(function(){
	+
	+            // Cache the highest
	+
	+            var highestBox = 0;
	+
	+            // Select and loop the elements you want to equalise
	+            jQuery(this).find('.B').each(function(){
	+                jQuery(this).removeAttr('style');
	+                // If this box is higher than the cached highest then store it
	+                if(jQuery(this).height() > highestBox) {
	+                    highestBox = jQuery(this).height();
	+                }
	+
	+            }).height(highestBox);
	+        });
	+
	+        // Select and loop the container element of the elements you want to equalise
	+
	+
	+
	+    }else{
	+        jQuery('.A .B').removeAttr('style');
	+
	+    }
	+}
	+            jQuery(document).ready(function(){
	+                call();
	+
	+                jQuery(window).resize(function() {
	+                   call();
	+            });
	+            });
	+
	+
	+</script>
	+

# CSS stylesheet/js in PHP
	PHP: $AA = get_template_directory_uri() . '/.../..';
	example:
	<link rel="stylesheet" href="<?php echo $AA ?>/.../../xxx.css"/>

# CSS Selector
	<li ><a href="<?php echo site_url(); ?>/..."><span class="breadcrumb-item active" aria-current="page">AAA</span></a></li>
	span.breadcrumb-item.active {
		   color: #368e47;
	       }
       
# CSS extend img to full width in a div
    width: 100vw;
    position: relative;
    left: 50%;
    margin-left: -50vw;
    right: 50%;
    margin-right: -50vw;
    
# PHP put meta to html header:
	put in the header.php
	 <?php
	    $postType = "aaa-bbb";
	    switch ($postType) {
		case "aaa-bbb":
		    $meta = 'akfjhdfhkjadflfadkjlfjk';
		    break;
		case "aaa":
		    $meta = '';
		    break;
		case "bbb":
		    $meta = '';
		    break;
	    }
	    ?>
	    <meta name="description" content="<?php echo $meta ?>"/>
      or 
      <?php
         $variable = wp_title('',FALSE);
         if (strpos($variable, 'Aaa bbb') !== false) {
             echo '<meta name="description" content="adlkjakljdlkajkdla. '.(($paged>1)?' page '.$paged:'').'"/>';
         }
         ?>
	 
# GIT of BitBucket(on PHP storm)
	1. create new branch: 
	   a. check out local dev branch
	   b. git->fetch from remote master branch
	   c. merge remote master branch to local dev to make it up-to-date
	   d. create new branch based on local dev
	2.git process:
	  a.git commit(before commit, need to manully add css file under newly created scss file)
	  b.git push
	3. create pull resquest, push to live, check PUSH DEV TO LIVE!

# CSS 
	use min-width to avoid the line jump to second page when shrinks the screen size
