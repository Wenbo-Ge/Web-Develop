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
	
# UTM Builder with URL Shortener
	
	html:

	<h2>1) Create <abbr title="Uniform Resource Locator">URL</abbr></h2>
	Fill in the form to create your custom <abbr title="Uniform Resource Locator">URL</abbr>.

	<form action="">
	<fieldset><label for="domain"><abbr title="Uniform Resource Locator">URL</abbr><input id="domain" name="domain" type="url" value="" placeholder="Enter the link for the website" /></label>

	<label for="source">Campaign Source <strong>*Where is my link going to be?*</strong><select id="source" name="source">
	<option disabled="disabled" selected="selected">Select One</option>
	<option>A</option>
	<option>B</option>
	<option>C</option>
	<option>D</option>
	<option>E</option>
	<option>F</option>
	<option>G</option>
	<option>H</option>
	<option>I</option>
	</select>
	</label>

	<label for="medium">Campaign Medium <strong>*What medium am I using to share the link?*</strong><select id="medium" name="medium">
	<option disabled="disabled" selected="selected">Select One</option>
	<option>a</option>
	<option>b</option>
	<option>c</option>
	<option>d</option>
	</select></label>

	<label for="name">Select Campaign Name <strong>*Which campaign is this link part of?*</strong> (Optional)<select id="name" name="name">
	<option disabled="disabled" selected="selected">Select One</option>
	<option>1</option>
	<option>2</option>
	<option>3+4</option>
	<option>5 a</option>
	</select></label>

	<label for="name">Or Enter Campaign Name (Optional)<input id="name_input" name="name_input" type="text" value="" placeholder="Enter a name to identify the campaign" /></label>

	<label for="content">Campaign Content <strong>*What will the person be clicking on?*</strong>(Optional)<select id="content" name="content">
	<option disabled="disabled" selected="selected">Select One</option>
	<option>a</option>
	<option>b</option>
	<option>c</option>
	<option>d</option>
	</select></label>

	<label for="content">Campaign Content (Optional)<input id="input_content" name="input_content" type="text" value="" placeholder="Enter something to differentiate ads" /></label>

	<label for="term">Campaign Term (Optional)<input id="term" name="term" type="text" value="" placeholder="Enter the paid keyword" /></label></fieldset>
	</form>
	<h2>2) Copy and Paste</h2>
	<div id="html" class="output">

	&nbsp;

	</div>
	<h2>3) Shorten Url</h2>
	<button id="shorten" type="button">Shorten URL</button>
	<div id="html" class="output">

	<label for="url">Click in the box to copy your link<textarea id="url_short" class="auto" style="background: #f1f1f1;" placeholder="Code will appear here after click the button"></textarea></label>

	</div>

	js:

	<script>
	    function writeUtm(utm, name, html) {
		if (utm) {
		    if (html[1] == 0) {
			html[0] += '?';
		    }
		    else {
			html[0] += '&';
		    }
		    html[0] += name + '=' + encodeURIComponent(utm);
		    html[1]++;
		}
		return html;
	    }

	    function updateOutput() {
		var domain = $('#domain').val();
		var utm_source = $('#source').val();
		var utm_medium = $('#medium').val();
		var utm_term = $('#term').val();
		var utm_content = $('#content').val();
		var utm_content_input = $('#input_content').val();
		var utm_campaign = $('#name').val();
		var utm_campaign_input = $('#name_input').val();

		var html = [];
		html[0] = domain;
		html[1] = 0;

		html = writeUtm(utm_source, 'utm_source', html);
		html = writeUtm(utm_medium, 'utm_medium', html);
		html = writeUtm(utm_term, 'utm_term', html);

		if (!utm_campaign_input) {
		    html = writeUtm(utm_campaign, 'utm_campaign', html);
		} else {
		    html = writeUtm(utm_campaign_input, 'utm_campaign', html);

		}

		if (!utm_content_input) {
		    html = writeUtm(utm_content, 'utm_content', html);
		} else {
		    html = writeUtm(utm_content_input, 'utm_content', html);
		}


		if (domain) {
		    $('#url').html(html[0].replace(/&/g, "&amp;").replace(/</g, "&lt;").replace(/>/g, "&gt;"));
		} else {
		    $('#url').html('');
		}


	    }

	    $(function () {
		$("form").bind("click keyup change", function (e) {
		    updateOutput();
		});
	    });

	    function validateText(str)
	    {
	   var tarea = str;
	   if (tarea.indexOf("http://") == -1 && tarea.indexOf("https://") == -1) {
		    return 'http://'+ tarea;
		} else {
		    return tarea;
		}
	    }

	    $('#shorten').click(function (e) {
		e.preventDefault();
		var url_long = $('#url').val();
		var url_full = validateText(url_long);
		$.post('https://giatec.net/create.php',
		    {data: url_full},
		    function (data) {
			var dataUrl = JSON.parse(data);
			$('#url_short').html(dataUrl.shortUrl);

		    });
	    });

	    function copyUrl() {
		var copyText = document.getElementById("url_short");
		copyText.select();
		document.execCommand("copy");
		// alert("Copied the text: " + copyText.value);
	    }

	</script>

	see url shortener...
	
# CSS correct target:
	use dev tool to hover the class,
	div.class name.class name use space next level.class name
	
# duplicated meta descriptions and titles
	at seo -> add %%page%% at description and title will solve this problem
	
# uncaught TypeError: $(...).tooltip is not a funciton Issue:
	to solve this problem, first to find correct header.php file.
	for example, at header-sr.php, $sr2page == 'concretematuritytool'
	second, add <script src="https://code.jquery.com/ui/../jquery-ui.js"> just behind jquery.js
	
	or just delete the jquery.js(it may be called twice) 
	
# useful tools to check website:
	1.semrush
	2.Search Console
	3.gtmetrix
	4.Google Analytics
	5.https://tools.pingdom.com/

# 301 re-direct:
	/.../* => /.../.../*

# export live database to local
	live phpmyAdmin -> export
	local phpmyAdmin -> import

# SCSS and LESS syntax:
	.claseName {
	...
	&.class-name {} => parallel with last class
	&:before/after
	}
