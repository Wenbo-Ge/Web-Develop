# CSS stuff
install sass to edit .scss files 
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
# CSS responsive image
php hard code, use http://www.responsivebreakpoints.com/ to generate responsive image
<img
								sizes="(max-width: 728px) 100vw, 728px"
								srcset="
<?php echo get_template_directory_uri(); ?>/templates-giatec/images/product_smartrock_sz08nl_c_scale,w_200.jpg 200w,
<?php echo get_template_directory_uri(); ?>/templates-giatec/images/product_smartrock_sz08nl_c_scale,w_392.jpg 392w,
<?php echo get_template_directory_uri(); ?>/templates-giatec/images/product_smartrock_sz08nl_c_scale,w_542.jpg 542w,
<?php echo get_template_directory_uri(); ?>/templates-giatec/images/product_smartrock_sz08nl_c_scale,w_661.jpg 661w,
<?php echo get_template_directory_uri(); ?>/templates-giatec/images/product_smartrock_sz08nl_c_scale,w_728.jpg 728w"
								src="<?php echo get_template_directory_uri(); ?>/templates-giatec/images/product_smartrock_sz08nl_c_scale,w_728.jpg"
								alt="SmartRock2&trade;">

# JS
to keep same height of each div, write js to calculate the height and use the largest height.
# JS 遍历+查找
<script>

   jQuery(document).ready(function(){


        jQuery('.bg_image').each(function(){
            var highestBox = 0;
            jQuery(this).find('.post .post_content').each(function () {
                    if (jQuery(this).height() > highestBox) {
                        highestBox = jQuery(this).height();
                    }
                }).height(highestBox);
        });
});

</script>
# CSS stylesheet
wordpress: <?php echo get_css_directory(); ?>
example:
<link rel="stylesheet" href="<?php echo get_css_directory(); ?>/sr2/animate.css?v=july272018348pm"/>

