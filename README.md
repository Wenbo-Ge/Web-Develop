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
	
# wp responsive image function:
	function awesome_acf_responsive_image($image_id,$image_size,$max_width){

	// check the image ID is not blank
	if($image_id != '') {

		// set the default src image size
		$image_src = wp_get_attachment_image_url( $image_id, $image_size );

		// set the srcset with various image sizes
		$image_srcset = wp_get_attachment_image_srcset( $image_id, $image_size );

		// generate the markup for the responsive image
		echo 'src="'.$image_src.'" srcset="'.$image_srcset.'" sizes="(max-width: '.$max_width.') 100vw, '.$max_width.'"';

	}
	}
  	and to call function in <img <?= awesome_acf_responsive_image($conten['image'][0]['id'],'thumb-640','640px'); ?>

# wp get image alt description from the uploads
	use <?php $image_alt=get_post_meta(get_post_thumbnail_id( $post->ID ), '_wp_attachment_image_alt', true) ?> to retrieve the alt information, then use alt="<?php echo !empty($image_alt) ? $image_alt : 'asjkhd'?>" to display alt description
	
# wp add custom field
	1. go to Custom Fields
	2. go to specific field groups
	3. add new field give field label
	4. field type should be tab
	5. add new field give field label and field name
	6. field type can be anything
	7. use wp function to call the data from field by using field_name
	for example: 	$post_id = get_the_ID();
			$company_logo = get_field('company_logo', $post_id);
# wp add seo to a page
	seo->search appearance->content types->choose the page need to be seo 

# wp background-image set to be responsive, call different size when in different screen size
	<?php
        $imageFull = wp_get_attachment_image_src(get_post_thumbnail_id($post_id), 'full');
        $imageLarge = wp_get_attachment_image_src(get_post_thumbnail_id($post_id), 'large');
        $imageMediumLarge = wp_get_attachment_image_src(get_post_thumbnail_id($post_id), 'medium_large');

        $imageFull = !empty($imageFull[0]) ? $imageFull[0] : 'default image';
        $imageLarge = !empty($imagelarge[0]) ? $imagelarge[0] : $imageFull;
        $imageMediumLarge = !empty($imageMediumLarge[0]) ? $imageMediumLarge[0] : $imageLarge;
        ?>
    <?php } else
    {
        $imageFull = !empty($imageFull) ? $imageFull : 'default image';
        $imageLarge = !empty($imageLarge) ? $imageLarge : 'default image';
        $imageMediumLarge = !empty($imageMediumLarge) ? $imageMediumLarge : 'default image';
    }
    ?>
    <style>
        .header {
            background-image: url(<?=$imageFull?>);
        }

        @media (max-width: 991px) {
            .header {
                background-image: url(<?=$imageLarge?>);
            }
        }

        @media (max-width: 767px) {
            .header {
                background-image: url(<?=$imageMediumLarge?>);
            }
        }
    </style>
    
  # Url Shortener
 	https://github.com/jmccartie/php-url-shortener
	1.downlkoad code from github
	2.do configuration on config.php
	3.modify connect.php, create.php, index.php, view.php
	4.if sql doesn't support, change sql into sqli
	5.upload all files to server(must include .htaccess file)
	6.type in url: A.Get Method: domin/create.php?url=...&pw=...
		       B.Post Method: ajax to do cross domain call from another the php file
	7.js call is the most important one, check utm builder js

# FTP Configuration
	1. set up ftp account in the server (Make sure the Directory is correct and identical the the phpstorm)
	2. in phpstorm, tools -> deployment -> configuration -> + add new one -> choose typy to FTP -> FTP host (should be 	      server host) -> Root path(/ or try auto detect) -> user name and password (identical to server FTP account) ->              deployment path on server(/)
	3. options: ctrl + s, automatic uploads
	
# PHP add password to page
	check view.php at domain
	
# js LinkedIn page crawler
	function JSONToCSVConvertor(JSONData, ReportTitle, ShowLabel) {
    //If JSONData is not an object then JSON.parse will parse the JSON string in an Object
    var arrData = typeof JSONData != 'object' ? JSON.parse(JSONData) : JSONData;

    var CSV = '';
    //Set Report title in first row or line


    //1st loop is to extract each row
    for (var i = 0; i < arrData.length; i++) {
        var row = "";

        //2nd loop will extract each column and convert it in string comma-seprated
        for (var index in arrData[i]) {
            row += '"' + arrData[i][index] + '",';
        }

        row.slice(0, row.length - 1);

        //add a line break after each row
        CSV += row + '\r\n';
    }

    if (CSV == '') {
        alert("Invalid data");
        return;
    }

    //Generate a file name
    var fileName = "Giatec_";
    var today = new Date();
    var date = '_' + today.getFullYear()+'_'+(today.getMonth()+1)+'_'+today.getDate()+'_';

    //this will remove the blank-spaces from the title and replace it with an underscore
    fileName += ReportTitle.replace(/ /g, "_");

    //Initialize file format you want csv or xls
    var uri = 'data:text/csv;charset=utf-8,' + escape(CSV);

    // Now the little tricky part.
    // you can use either>> window.open(uri);
    // but this will not work in some browsers
    // or you will not get the correct file extension

    //this trick will generate a temp <a /> tag
    var link = document.createElement("a");
    link.href = uri;

    //set the visibility hidden so it will not effect on your web-layout
    link.style = "visibility:hidden";
    link.download = fileName + date +".csv";

    //this part will append the anchor tag and remove it after automatic click
    document.body.appendChild(link);
    link.click();
    document.body.removeChild(link);
	}

	jQuery(function ($) {
    	var data = [], list = [];
   	 var rand = Math.round(Math.random() * (3000)) + 3000;
    	var rand2 = Math.round(Math.random() * (3000)) + 2000;
   	 list['first_name'] = 'First Name';
   	 list['last_name'] = 'Last Name';
    	list['job_title'] = 'Job Title';
    	list['company'] = 'Company';
    	list['location'] = 'Location';
    	list['domain'] = 'Domain';
   	 list['contact_name'] = 'Contact Name';
    	list['campaign'] = 'Campaign';
   	 list['rating'] = 'Rating';
    	list['country'] = 'Country';
    	list['state'] = 'State';
    	data.push(list);
    	var interval = window.setInterval(function () {
        rand = Math.round(Math.random() * (8000 - 5000)) + 3000;
        rand2 = Math.round(Math.random() * (8000 - 5000)) + 2000;
        $("html").animate({scrollTop: $(document).height() * 2}, rand2, function () {
            jQuery('.search-results__result-item').each(function (index, element) {
                list = [];
                var name = $(element).find("dt.result-lockup__name a.ember-view");
                list['first_name'] = $(name).text().split(' ')[12].trim();
                list['last_name'] = $(name).text().split(' ')[13] == undefined ? '' : $(name).text().split(' ')[13].trim();
                var job_title = $(element).find('dd.result-lockup__highlight-keyword > span:first-child');
                list['job_title'] = $(job_title).text().trim();
                var company_name = $(element).find('.horizontal-person-entity-lockup-4.result-lockup__entity.ml4 dd.result-lockup__highlight-keyword .result-lockup__position-company a > span:first-child');
                list['company'] = $(company_name).text().trim();
                var location_name = $(element).find('ul.result-lockup__misc-list li.result-lockup__misc-item');
                list['location'] = $(location_name).text().trim();
                list['domain'] = '';
                list['contact_name'] = '';
                list['campaign'] = '';
                list['rating'] = '';
                list['country'] = '';
                list['state'] = '';
                data.push(list);
            });
            if (!jQuery('button.search-results__pagination-next-button').is(':disabled')) {
                jQuery('button.search-results__pagination-next-button').trigger('click');
            } else {
                clearInterval(interval);
                JSONToCSVConvertor(data, $('.search-nav--title a').text(), false);
            }
        });
    }, rand + rand2);
	});
    
# Imac signature issue
	https://www.daretothink.co.uk/html-email-signature-in-apple-mail/

# pdf share broken link at blog
	wordpress post editor check <img width: 50 px> extra space causes this problem
	
# hubspot form issue:
	<h3>Internal Lead Submission</h3>
	[/vc_column_text][vc_column_text]
	<div class="hubspot_internal hbspt-form"></div>
	<!-- [if lte IE 8]>
	<script charset="utf-8" type="text/javascript" src="//js.hsforms.net/forms/v2-legacy.js"></script>
	<![endif]--> <script charset="utf-8" type="text/javascript" src="//js.hsforms.net/forms/v2.js"></script>
	<script>
	  hbspt.forms.create({
		portalId: "something",
		formId: "something",
		target: ".hubspot_internal",
	});
	</script>[/vc_column_text][/vc_column][vc_column width="1/4"][/vc_column][/vc_row]

# screen width capture issue
	use Math.round($(document).width()) instead of Math.round($(window).width()) to capture the width of the screen, 	 this is more accurate
	
# backlink:
	对于搜尋引擎最佳化（SEO）而言，反向链接能够使网站获得好的排名，所以，反向链接的好坏直接影响网站的整体权重和流量。
	在论坛签名檔内加上网站名，发言时就会带上网站链接
	创建博客，在更新的文章内加上网址
	到各个相关门户投稿，并加上网站链接
	在别人博客留言
	在社交媒体上发帖子，在上面建立反向链接
	和其他网站交换友情链接

# cookie script
	https://cookieconsent.insites.com/

# array to string convertion ISSUE
	check the function defination and usage,for example:
	get_the_terms (int|object, string);
	wp_get_post_terms(int,string|array);
	use second function can solve the problem

# certain webpage is slow
	1.turn on the debug at wp.config,(some functions will still work and won't response the error message when debug is off); 
	2.check function in that page, might have kind of array to string convertion issues that will slow down the page speed.
	3.when debug is on, error message will appear even though the function is working but slowdown the speed.
	
# use url to filter the contents
	hardcoded: 
	<script>
    $(document).ready(function () {
        if ($(location).attr('href').indexOf("?filter=wp-slug") != -1) {
            $('button[data-filter=".wp-slug"]').trigger('click');
        } else {
            if ($(location).attr('href').indexOf("?filter=wp-slug") != -1) {
                $('button[data-filter=".wp-slug"]').trigger('click');
            } else {
                $('button[data-filter="all"]').trigger('click');
            }
        }
    });
	</script>
	
	function 1: customize function
	<script>
	 $(function () {
       var filter = getParameterByName('filter');
        if (filter)
           $('button[data-filter=".' + filter + '"]').trigger('click');
     });
     </script>
     
     getParameterByName('name') this function coded like this:
     function getParameterByName(name) {
	name = name.replace(/[\[]/, "\\[").replace(/[\]]/, "\\]");
	var regex = new RegExp("[\\?&]" + name + "=([^&#]*)"),
		results = regex.exec(location.search);
	return results === null ? "" : decodeURIComponent(results[1].replace(/\+/g, " "));
	}
			
	function 2: use js filter library build in function (library can be found at https://www.kunkalabs.com/tutorials/filtering-with-mixitup/) 
	<script>
    $(function () {
        var filter = getParameterByName('filter');
        if (filter) {
            var mixer = mixitup('.mix-container');
            mixer.filter('.' + filter);
        }
    });
	</script>

# Css Cursor:
	cursor: grab;
	cursor: point;
	cursor: move;

# CSS Background :
	background-position: can be top right; center; or 80% 90%

# detect noscript(if browser turns off the javascript)
	https://webdesign.tutsplus.com/tutorials/quick-tip-dont-forget-the-noscript-element--cms-25498
	
 # Url Shortener
 	https://github.com/jmccartie/php-url-shortener
	1.downlkoad code from github
	2.do configuration on config.php
	3.modify connect.php, create.php, index.php, view.php
	4.if sql doesn't support, change sql into sqli
	5.upload all files to server(must include .htaccess file)
	6.type in url: A.Get Method: domin/create.php?url=...&pw=...
		       B.Post Method: ajax to do cross domain call from another the php file
	7.js call is the most important one, check utm builder js

# FTP Configuration
	1. set up ftp account in the server (Make sure the Directory is correct and identical the the phpstorm)
	2. in phpstorm, tools -> deployment -> configuration -> + add new one -> choose typy to FTP -> FTP host (should be 	      server host) -> Root path(/ or try auto detect) -> user name and password (identical to server FTP account) ->              deployment path on server(/)
	3. options: ctrl + s, automatic uploads
	
# PHP add password to page
	check view.php at url shortener package
	
# js LinkedIn page crawler
	function JSONToCSVConvertor(JSONData, ReportTitle, ShowLabel) {
    //If JSONData is not an object then JSON.parse will parse the JSON string in an Object
    var arrData = typeof JSONData != 'object' ? JSON.parse(JSONData) : JSONData;

    var CSV = '';
    //Set Report title in first row or line


    //1st loop is to extract each row
    for (var i = 0; i < arrData.length; i++) {
        var row = "";

        //2nd loop will extract each column and convert it in string comma-seprated
        for (var index in arrData[i]) {
            row += '"' + arrData[i][index] + '",';
        }

        row.slice(0, row.length - 1);

        //add a line break after each row
        CSV += row + '\r\n';
    }

    if (CSV == '') {
        alert("Invalid data");
        return;
    }

    //Generate a file name
    var fileName = "Giatec_";
    var today = new Date();
    var date = '_' + today.getFullYear()+'_'+(today.getMonth()+1)+'_'+today.getDate()+'_';

    //this will remove the blank-spaces from the title and replace it with an underscore
    fileName += ReportTitle.replace(/ /g, "_");

    //Initialize file format you want csv or xls
    var uri = 'data:text/csv;charset=utf-8,' + escape(CSV);

    // Now the little tricky part.
    // you can use either>> window.open(uri);
    // but this will not work in some browsers
    // or you will not get the correct file extension

    //this trick will generate a temp <a /> tag
    var link = document.createElement("a");
    link.href = uri;

    //set the visibility hidden so it will not effect on your web-layout
    link.style = "visibility:hidden";
    link.download = fileName + date +".csv";

    //this part will append the anchor tag and remove it after automatic click
    document.body.appendChild(link);
    link.click();
    document.body.removeChild(link);
	}

	jQuery(function ($) {
    	var data = [], list = [];
   	 var rand = Math.round(Math.random() * (3000)) + 3000;
    	var rand2 = Math.round(Math.random() * (3000)) + 2000;
   	 list['first_name'] = 'First Name';
   	 list['last_name'] = 'Last Name';
    	list['job_title'] = 'Job Title';
    	list['company'] = 'Company';
    	list['location'] = 'Location';
    	list['domain'] = 'Domain';
   	 list['contact_name'] = 'Contact Name';
    	list['campaign'] = 'Campaign';
   	 list['rating'] = 'Rating';
    	list['country'] = 'Country';
    	list['state'] = 'State';
    	data.push(list);
    	var interval = window.setInterval(function () {
        rand = Math.round(Math.random() * (8000 - 5000)) + 3000;
        rand2 = Math.round(Math.random() * (8000 - 5000)) + 2000;
        $("html").animate({scrollTop: $(document).height() * 2}, rand2, function () {
            jQuery('.search-results__result-item').each(function (index, element) {
                list = [];
                var name = $(element).find("dt.result-lockup__name a.ember-view");
                list['first_name'] = $(name).text().split(' ')[12].trim();
                list['last_name'] = $(name).text().split(' ')[13] == undefined ? '' : $(name).text().split(' ')[13].trim();
                var job_title = $(element).find('dd.result-lockup__highlight-keyword > span:first-child');
                list['job_title'] = $(job_title).text().trim();
                var company_name = $(element).find('.horizontal-person-entity-lockup-4.result-lockup__entity.ml4 dd.result-lockup__highlight-keyword .result-lockup__position-company a > span:first-child');
                list['company'] = $(company_name).text().trim();
                var location_name = $(element).find('ul.result-lockup__misc-list li.result-lockup__misc-item');
                list['location'] = $(location_name).text().trim();
                list['domain'] = '';
                list['contact_name'] = '';
                list['campaign'] = '';
                list['rating'] = '';
                list['country'] = '';
                list['state'] = '';
                data.push(list);
            });
            if (!jQuery('button.search-results__pagination-next-button').is(':disabled')) {
                jQuery('button.search-results__pagination-next-button').trigger('click');
            } else {
                clearInterval(interval);
                JSONToCSVConvertor(data, $('.search-nav--title a').text(), false);
            }
        });
    }, rand + rand2);
	});

# Imac signature issue
	https://www.daretothink.co.uk/html-email-signature-in-apple-mail/

# pdf share broken link at blog
	wordpress post editor check <img width: 50 px> extra space causes this problem
	
# hubspot form issue:
	<h3>Internal Lead Submission</h3>
	[/vc_column_text][vc_column_text]
	<div class="hubspot_internal hbspt-form"></div>
	<!-- [if lte IE 8]>
	<script charset="utf-8" type="text/javascript" src="//js.hsforms.net/forms/v2-legacy.js"></script>
	<![endif]--> <script charset="utf-8" type="text/javascript" src="//js.hsforms.net/forms/v2.js"></script>
	<script>
	  hbspt.forms.create({
		portalId: "something",
		formId: "something",
		target: ".hubspot_internal",
	});
	</script>[/vc_column_text][/vc_column][vc_column width="1/4"][/vc_column][/vc_row]

# screen width capture issue
	use Math.round($(document).width()) instead of Math.round($(window).width()) to capture the width of the screen, 	 this is more accurate
	
# backlink:
	对于搜尋引擎最佳化（SEO）而言，反向链接能够使网站获得好的排名，所以，反向链接的好坏直接影响网站的整体权重和流量。
	在论坛签名檔内加上网站名，发言时就会带上网站链接
	创建博客，在更新的文章内加上网址
	到各个相关门户投稿，并加上网站链接
	在别人博客留言
	在社交媒体上发帖子，在上面建立反向链接
	和其他网站交换友情链接

# cookie script
	https://cookieconsent.insites.com/

# array to string convertion ISSUE
	check the function defination and usage,for example:
	get_the_terms (int|object, string);
	wp_get_post_terms(int,string|array);
	use second function can solve the problem

# certain webpage is slow
	1.turn on the debug at wp.config,(some functions will still work and won't response the error message when debug is off); 
	2.check function in that page, might have kind of array to string convertion issues that will slow down the page speed.
	3.when debug is on, error message will appear even though the function is working but slowdown the speed.
	
# de-index page in robot.txt
	User-agent: *
	Disallow: /fetch-tweets.php
	then, sss.com/fetch-tweets.php will be de-index.
	
# change url without refresh the page
	js: history.pushState(null, '' , '?filter=asda');
	then ?filter=asda will be right after the url	
	
# js hardcode to "smart code"  (and how to select data-attribute in jquery)
	hardcode:
	$('[data-filter="all"]').click(function () {
        $('.product_name').replaceWith('<span class="txt product_name">Products</span>');
        $('.project_type_name').replaceWith('<span class="txt project_type_name">Project Types</span>');
       history.pushState(null, '', '?filter=.all');
  	 });

    $('[data-filter=".smart-concrete"]').click(function () {
       $('.product_name').replaceWith('<span class="txt product_name">Product: aaa bbb</span>');
       $('.project_type_name').replaceWith('<span class="txt project_type_name">Project Types</span>');
        history.pushState(null, '', '?filter=aaa-bbb');
   	});

	
	smart code: 
	$('.show_buttons button').click(function () {
            var filter = $(this).data('filter');
            var text = $(this).html();
            $('.dropdown-filter .txt').each(function () {
                $(this).html($(this).data('title'));
            });
            if(filter !== 'all') {
                var prefix = $(this).parent().parent().find('.txt').data('prefix');
                $(this).parent().parent().find('.txt').html(prefix+text);
                history.pushState(null, '', '?filter=' + filter);
            }else {
                history.pushState(null,'', '');

            }
        });
	
	
	
# jQuery to check input check box
	var value='';
	jQuery("input:checkbox[value='" + value + "']").prop("checked", true);
	
# jQuery auto run script when page loaded
	function call () {
		alert('aaa');
		};
	jQuery(document).ready(function () {
		call()
	});
	
# jQuery click to scroll down 
	jQuery(document).ready(function( $ ) {
    $('.searchbychar').click(function () {
        var thisHeight = $('aaa').height();
        var height = srnavHeight + $('sss').height();

        var divID = '#' + this.getAttribute('data-target');
		if(thisHeight>50)
			height = height+70;
            $('html, body').animate({
                scrollTop: $(divID).offset().top - height
            }, 1000);
    });
	});
 	
# CSS Target IE and EDGE
	https://gist.github.com/zunairmushtaq/aeaa48432d51cad0eb1c
	ie : @media screen and (-ms-high-contrast: active), (-ms-high-contrast: none) {
	.selector { property:value; }
	}
	edge: @supports (-ms-ime-align:auto) { 
		.selector { property:value; }
	}
	
# PHP Arg to query custom field group (True/False type)
	https://www.billerickson.net/code/wp_query-arguments/
	https://www.advancedcustomfields.com/resources/true-false/
	'meta_value' => '1' (true);
	'meta_value' => '0' (false);
	
# lazyload image
	http://jquery.eisbehr.de/lazy/
	
# html url is long that is out of screen when screen size is small
	use css word-break: break-word,
	then url will break into second line
	
# bootstrap grid issue
	if class name contains col-md-6 these kind of attributes,
	need to add 'row' in parent div,
	or before current class name;
	EX: <div class="row">
		<div class="col-md-6"></div>
	    </div>
	if missing "row", will have some issues to target in css.
	
	to make a whole div into different rows:
	<div class="row">
		<div class="container">
			<div class="row row_1">
				<div class="col-lg-6 col-md-6"></div>
			</div>
			<div class="row row_2">
				<div class="col-lg-6 col-md-6"></div>
			</div>
		</div>
	</div>
	<div class="row">
		<div class="container">
			<div class="row row_1">
				<div class="col-lg-6 col-md-6"></div>
			</div>
			<div class="row row_2">
				<div class="col-lg-6 col-md-6"></div>
			</div>
		</div>
	</div>
	
	
# Use custom field to controll form
	build custom field to caputure form id,
	use differnet id to call form to avoid hardcode.
	
# put php in js
	<script>
	var form_id = '<?= !empty($stickyButtons[$key]['form_id']) ? $stickyButtons[$key]['form_id'] : "other else"?>';
	target: form_id,
	</script>
# backgroud has two differnt color 
	https://www.w3schools.com/colors/colors_gradient.asp
	
# if dev appears at google search page
	1. robots.txt: 
		User-agent: *
		Disallow: / or *
	2. check url of appeared dev,
		delete that index.html from server side
		
# Css dialogue box
	.dialogue-box {
      position: relative;
      max-width: 600px;
      height: auto;
      border: 2px solid #ffffff;
      //margin: 100px auto;
      padding: 15px;
      box-sizing: border-box;
	}


	.dialogue-box:after {
    content: "";
     position: absolute;
      width: 30px;
      height: 30px;
      border-top: 0px solid #ffffff;
      border-right: 2px solid #ffffff;
      border-bottom: 2px solid #ffffff;
      border-left: 0px solid #ffffff;
      top:106%;
      left: 70%;
      margin-left: -25px;
      content: '';
      transform: rotate(45deg);
      margin-top: -25px;
      background: #0b9444;
	}

# CSS change for svg
	Can dirctly add in-line style to svg tag:
	<svg style="color: green"></svg>
	
# CSS hover en-large effect 
	use transform: scale(1.1);
	add large width and height will have some bad effect.
	
# CSS fancy hover effect library
	http://ianlunn.github.io/Hover/
	
# CSS responsive @media min
	@media (min-width:1200px) {}, then @media (min-width: 991px) {}

# fancy box library
	https://fancyapps.com/fancybox/3/	
	
	
# vertical align middle method:
	1. padding: 20px 0;
	2.<div style="display: table">
		<div style="display: table-cell; vertical-algin:middle;">
		</div>
	  </div>
	3. display: block; line-height:1.5; vertical-align: middle;
	4. at outter div: display: flex; align-items: center;
	
	
# slider inside slider, to make one slider section swipe-able
	https://jsfiddle.net/WALKMAN5/0smp3kst/14/
	
# Remove links from sitemap in wordpress
	wp-admin: -> SEO search sppearance ->taxonomies -> Find the category -> set to no, hide
	
# change toolbar color for mobile browser
	<meta name="theme-color" content="#007A3E"> in header
 
# php file call
	require 'jazzAPI/jazz.php' use this path if they are in same dirctory
	require './jazzAPI/jazz.php' need to find another dirctory

# wordpress function calls:
	when calling the query_posts(), should end up with wp_reset_query()
	
# Anchor Scorll Down:
	https://codepen.io/jooleearr/pen/gpooKj
	
# External link target="_blank"
	if open a new tab for an external link, should add rel="noopener" to the a tag like <a href="..." target="_blank" rel="noopener"></a>
	
# CSS Background Blur
	  filter: blur(8px);
  	  -webkit-filter: blur(8px);	

# Css z-index
	must use with position which is not static, otherwise, z-index won't work
	
# HTML table
	<th colspan=""> colspan can take whole row in the table.

# hubspot form customizations:
	Use JS to controll forms: check this page- https://developers.hubspot.com/docs/methods/forms/advanced_form_options
	
# Css Center a whole div when it doesn't have full width:
	display: block;
	float: none;
	Margin: 0 auto;

# PHP GET method:
	in JS Post: 
	jQuery.post("/wp-admin/admin-ajax.php?action=roi&step=1",
                        {
                            pv: jQuery('#pv').val(),
                            unit: jQuery('#unit').val(),
                            pn: jQuery('#pn').val(),
                            first: jQuery('#first').val(),
                            last: jQuery('#last').val(),
                            email: jQuery('#email').val()
                        },
			....);
	JQuery uses http GET.
	In PHP, $_GET["step"]....
	
	
# Bootstrap Grid
	Order of the responsiveness(from large to small):
	col-lg-12(width: >1200px) col-md-12(width: less than 1200px) col-sm-12(width: less than 991px) 
	
# Bugs fix after server is upgraded to php 7.2
	1. create_function
	   	a.custome_function.php
	   	b.server=>wp-filebase->wp-filebase.php
	2. each
		a.server=>JS-composer-> class-vc-mapper.php
	3. private login
	
	fixes: 1. add_filter("gform_confirmation_anchor", function() {return false;});

		2. {
        		return function($cl,$fnc) {$p=func_get_args(); return wpfb_call("' . $cl . '","' . $fnc . 				'",$p,true);};
    		}

	3. foreach( $this->init_activity as $object => $params)  {
			list( $object, $method, $params ) = $params[1];


	4. if(function_exists('pg_user_logged')) { }

# push Dev to live
     PHP:
	1. Checkout origin/master as new local_master
	2. Checkout local_master
	3. Git pull
	4. Merge other local branch to this local_master branch
	5. ctrl+shift+k to push local_master
     
     Terminal:
     	1. ssh admin@xx.xx.xxx.xxx (password: need password for server)
	2. cd /home/admin/web/giatecscientific.com/public-html/wp_content/themes/twentyeleven
	3. git branch to check if this head is at master branch
	4. git pull (password for pull);
	
# validation before form submission
	function validationCheck() {
                            var phone_number = jQuery('inputID').val();
                            jQuery.get(
                                'http://apilayer.net/api/validate?access_key=....&number=' + phone_number, function (data) {
                                    console.log(data.valid);
                                    if (data.valid === false) {
                                        alert('Your Phone Number is not valid!');
                                    } else {
                                        jQuery('formID')[0].submit();
                                    }
                                });
                        }
                        jQuery('body').on('click', 'formID input[type="submit"]', function (e) {
                                        e.preventDefault();
                                        validationCheck();
                        });

# CSS selector (1,3,5; 2,4,6)

	.class_name:nth-child(2n-1) {}
	.class_name:nth-child(2n) {}
	nth-child(): regardless type;
	nth-of-type(): regard type
	
# jQuery Error Issue (... is not function):
	
	for example: jQuery('..')[1].val() has error -> val is not function,
	solution: try to use jQuery('')[1].value will solve the issue.
	
	
# jQuery UI Drag and Drop
	
	https://codepen.io/benkalsky/pen/ByJawa
	
	
# Image Zoom in And Out With Mouse Move
	
	https://codepen.io/ccrch/pen/yyaraz

	<div class="tiles">
                                <div width="711" height="378" class="tile"
                                     data-image="<?php $url = wp_get_attachment_image_src(get_post_thumbnail_id($post->ID), 		'xxxxx');
                                     echo $url[0]; ?>" data-scale="2.4" alt="<?php the_title(); ?>">
                                </div>
                            </div>

    <style>
        .tiles {
            position: relative;
            top: 0;
            left: 0;
            width: 100%;
            height: 300px;
            display: block;
        }

        .tile {
            position: relative;
            width: 100%;
            height: 100%;
            overflow: hidden;
        }

        .photo {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-repeat: no-repeat;
            background-position: center;
            background-size: cover;
            transition: transform .5s ease-out;
        }
    </style>
    <script>
        jQuery(document).ready(function ($) {
            $('.tile')
            // tile mouse actions
                .on('mouseover', function () {
                    $(this).children('.photo').css({'transform': 'scale(' + $(this).attr('data-scale') + ')'});
                })
                .on('mouseout', function () {
                    $(this).children('.photo').css({'transform': 'scale(1)'});
                })
                .on('mousemove', function (e) {
                    $(this).children('.photo').css({'transform-origin': ((e.pageX - $(this).offset().left) / $(this).width()) * 100 + '% ' + ((e.pageY - $(this).offset().top) / $(this).height()) * 100 + '%'});
                })
                // tiles set up
                .each(function () {
                    $(this)
                    // add a photo container
                        .append('<div class="photo"></div>')
                        // set up a background image for each tile based on data-image attribute
                        .children('.photo').css({'background-image': 'url(' + $(this).attr('data-image') + ')'});
                })
        });

    </script>

	https://stackoverflow.com/questions/33811041/javascript-zoom-in-on-mouseover-without-jquery-or-plugins
	
# Background Size
	background-size: 100% 80% to customize the coverage of background
	
# Differnet image size to set equal height without changing image size ratio:
	max-width: 100%;
	height: specifc height(64px).
	
# Css stylesheet idea
	1. Put pre-setup at the beginning.
	2. for example: 
	* {
  	font-family: interstate, Arial, sans-serif;
	  	font-weight: 500;
	text-rendering: optimizeLegibility;
	font-feature-settings: "kern";
	-webkit-font-feature-settings: "kern";
	-moz-font-feature-settings: "kern";
	-moz-font-feature-settings: "kern=1";
	-webkit-font-smoothing: antialiased;
	-moz-osx-font-smoothing: grayscale;
	font-smoothing: antialiased;
	text-shadow: 1px 1px 1px rgba(0, 0, 0, 0.004);

	}

	h1, h2, h3, h4, h5 {
	font-family: sofia-pro, sans-serif;

	line-height: 1;
	color: #161616;
	}

	h1 {
	margin-top: 0;
	font-size: 4.769em;
	}
	h2 {
	font-size: 3.052em;
	}
	h3 {
	font-size: 2.441em; line-height: 1.05;
	}
	h4, p.large-par {font-size: 1.953em;font-family: sofia-pro, sans-serif;}
	p {
	font-size: 1.25em;
	}

	a {
	font-family: sofia-pro, sans-serif;
	font-size: 1em;
	}
	
	
# JS call date(month and day) :

 	var months    = ['Jan','Feb','Mar','Apr','May','Jun','Jul','Aug','Sept','Oct','Nov','Dec'];
	var now       = new Date();
	var thisMonth = months[now.getMonth()]; // getMonth method returns the month of the date (0-January :: 11-December)
	var thisDay = now.getDate();
	var output1 = document.getElementById('mt');
	var output2 = document.getElementById('d');

    	output1.innerText = thisMonth;
    	output2.innerText = thisDay;

# Slider in effect

	https://codepen.io/blondersholmvik/pen/BLKxZE
	
# Use URL to jump to certain section
	https://css-tricks.com/hash-tag-links-padding/

	html: <span id="test">&nbsp;</span>
	css: #test {
		      margin-top: -300px;        /* Size of fixed header */
		      padding-bottom: 300px;
		      display: block;
		}

	url: ../../#test will jump to test section

	 or use JS:
	html: <li class="col-lg-4"><a href="#skills_section" class="anchor_link"><div><span>My Skills</span></div></a></li>
				<li class="col-lg-4"><a href="#experience_section" class="anchor_link"><div><span>My Experience</span></div></a></li>
				<li class="col-lg-4"><a href="#demos_section" class="anchor_link"><div><span>Demos & Projects</span></div></a></li>

	$( ".anchor_link" ).click(function( event ) {
		    event.preventDefault();
		    $("html, body").animate({ scrollTop: $($(this).attr("href")).offset().top }, 500);
		});
	

# Equalise the height

	var highestBox = 0;
        jQuery('.outter').find('.inner').each(function () {

					jQuery(this).removeAttr('style');
					// If this box is higher than the cached highest then store it
					if (jQuery(this).height() > highestBox) {
						highestBox = jQuery(this).height();
					}

				}).height(highestBox);
	
# Slick Slider Customization

	1. If slick arrow color cant be changed, try to change opacity, set opacity to 1.
	2. slick slider last slider half fade effect: 
		![screenshot from 2019-01-29 14-56-01](https://user-images.githubusercontent.com/36894305/51936485-4b036d00-23d6-11e9-91f9-07e0887a83ea.png)
		code: 
		.sensor_slider {
			.slick-list {
				padding:0 15% 0 0;
        			margin-right: -10%;
			}
		}
		.sensor_slider:after {
      			content: "";
  			position: absolute;
 			z-index: 1;
 			width: 300px;
  			top: 0;
  			height: 100%;
  			pointer-events: none;
	    		}
    		.sensor_slider:after {
  			right: -120px;
			background: linear-gradient(to left, #F2F2F2, transparent);
			}
		
	
	3. slick slider two sides fade:
	![screenshot from 2019-02-25 09-35-28](https://user-images.githubusercontent.com/36894305/53344496-cfb3af00-38e0-11e9-8316-aadcfad7920a.png)
		html:

	<div class="col-lg-12 col-md-12 col-sm-12 display_img">
            <div class="slider">
                <img src="<?php echo get_template_directory_uri(); ?>/.../../.." alt="">
	<!--                  <div class="overlay">-->
	<!--    <div class="text">Sarah D on Jobsite, Ottawa</div>-->
	<!--  </div>-->
           	 </div>
            	<div class="slider">
                <img src="<?php echo get_template_directory_uri(); ?>/.../../.." alt="">
            </div>
            <div class="slider">
                <img src="<?php echo get_template_directory_uri(); ?>/.../../.." alt="">
            </div>
            <div class="slider">
                <img src="<?php echo get_template_directory_uri(); ?>/.../../.." alt="">
            </div>
            <div class="slider">
                <img src="<?php echo get_template_directory_uri(); ?>/.../../.." alt="">
            </div>
        </div>


	css:

      .display_img:after {
      content: "";
  	position: absolute;
 	 z-index: 1;
 	 width: 100%;
  	top: 0;
  	height: 100%;
 	 pointer-events: none;
    }
    .display_img:after {
  	background: linear-gradient(to left, white, transparent 10%, transparent 90%, white 100%);
	}

	js:

	$('.display_img').slick({
  		dots: false,
        infinite: true,
        speed: 300,
        centerMode: true,
        centerPadding: '60px',
        autoplay: false,
        autoplaySpeed: 3000,
        slidesToShow: 3,
        arrows: true,
        responsive: [
            {
                breakpoint: 991,
                settings: {
                    arrows: false,
                    centerMode: true,
                    centerPadding: '100px',
                    slidesToShow: 1
                }
            },
            {
                breakpoint: 480,
                settings: {
                    arrows: false,
                    centerMode: true,
                    centerPadding: '30px',
                    slidesToShow: 1
                }
            }
        ]
	});
	
	4. If slick slider box-shadow is missing:
		solution: .slick-list {
			padding: 25px 0;
		}
		give a padding to slick list that will make shadow visible again

# Slide in effect from outside of screen:
	html:
	side div that wanted to be slided in:

			<div class="footer_quote_form">
				<div class="scroller">
					<div class="form_title">
						TEST
						<i class="material-icons close_form right">&times;</i>
					</div>
					<div class="hubspot_quote_request hbspt-form">
					</div>
				</div>
			</div>

	css:

	body .footer_quote_form {
    	display: none;
   	width: 100%;
   	max-width: 331px;
    	position: fixed;
    	top: 0;
    	right: -767px;
    	z-index: 9999999999;
    	background: #fff;
    	height: 100%;
    	font-family: open sans;
    	-webkit-box-shadow: 0 0 4px 0 rgba(0,0,0,.6);
    	-moz-box-shadow: 0 0 4px 0 rgba(0,0,0,.6);
    	box-shadow: 0 0 4px 0 rgba(0,0,0,.6);
    	overflow: scroll;
    	-webkit-overflow-scrolling: touch;
	}

	body .footer_quote_form div.scroller {
    	position: absolute;
    	left: 0;
    	right: 0;
	}

	body .footer_quote_form .form_title {
   	background: #f48513;
    	color: white;
    	text-align: center;
    	font-size: 20px;
    	padding: 16px 0;
    	font-weight: 600;
	}


	JS:

	<script>
  	function startQuote() {
				jQuery('.footer_quote_form .scroller').css('bottom', 'auto');
				jQuery('body').addClass('show-form');
				jQuery('.footer_quote_form').stop().show().animate({"right": "0px"}, "slow", function () {
					jQuery(window).scrollTop(0);
				});

			}
  
  	function removeQuote() {
				jQuery('body').removeClass('show-form');
				jQuery('.footer_quote_form').stop().animate({"right": "-767px"}, "slow", function () {
					jQuery('.footer_quote_form').hide();
				});
			}
  
  
  	jQuery('.close_form').click(function () {
					removeQuote();
				});
				jQuery('button').click(function () {
						startQuote();
				});
	</script>
	
# Phone slider with bullet points
	html: 
	<div class="col-lg-4 col-md-4 col-sm-6 right_img">
            <div class="app_iphone">
              <div class="app_iphone_screen iphone_slide_1">
                  <div class="screen_item slide-1" data-slide-title="Live Overview">
                      <img src="<?php echo get_stylesheet_directory_uri(); ?>/.../../.." alt="/>
                  </div>
                  <div class="screen_item slide-2" data-slide-title="Mix Calibrations">
                      <img src="<?php echo get_stylesheet_directory_uri(); ?>/.../../.." alt=""/>
                  </div>
                  <div class="screen_item slide-3" data-slide-title="Project Management">
                      <img src="<?php echo get_stylesheet_directory_uri(); ?>/.../../.." alt=""/>
                  </div>

                  <div class="screen_item slide-4" data-slide-title="Data History">
                      <img src="<?php echo get_stylesheet_directory_uri(); ?>/.../../.." alt=""/>
                  </div>
              </div>
              <div class="app_iphone_device"></div>
          </div>
        </div>
        <div class="col-lg-2 col-md-2 col-sm-4 bottom_txt app_features">
            <p class="app_item active" data-slideindex="0">a</p>
            <p class="app_item" data-slideindex="1">b</p>
            <p class="app_item" data-slideindex="2">c</p>
            <p class="app_item" data-slideindex="3">d</p>
        </div>
	
	css: 
          .right_img {
          .app_iphone_device {
            width: 397px;
            height: 808px;
            background: url(../../images/../iphone.png) no-repeat;
	  background-size: contain;
	  z-index: 9;
	  position: absolute;
	  pointer-events: none;
	  top: 50%;
	  left: 50%;
	  transform: translate(-50%, -50%)
	  }

	.app_iphone {
	    width: 397px;
	    height: 808px;
	  }

	  .app_iphone_screen {
	    position: absolute;
	    top: 94px;
	    left: 21px;
	    width: 348px;
	    height: 619px
	  }

	 .screen_item {
	    width: 348px;
	    height: 619px;
	    display: inline-block
	  }
	    }
	    .bottom_txt {
	      padding-top: 50%;
	      color: #1f8a5c;;
	      position: relative;
	      left: 50px;

	      .app_item {
	  opacity: .5;
	  -webkit-transition: all .3s;
	  transition: all .3s;
	  -ms-transform: scale(.9);
	  -webkit-transform: scale(.9);
	  -webkit-transform-origin-x: 0;
	  transform-origin-x: 0;
	  -ms-transform-origin-x: 0;
	  transform: scale(.9);
	  text-align: left;
	  cursor: context-menu;
	   display: list-item;
	  list-style-type: none;
	  list-style-position: outside;
	}
	.app_item:hover {
	  opacity: .8
	}

	.app_item.active {
	  opacity: 1;
	  -ms-transform: scale(1);
	  -webkit-transform: scale(1);
	  transform: scale(1);
	  //&:before {
	  //  content: '• ';
	  //}
	  list-style-type: disc;
	}
	    }

	js:
	$('.iphone_slide_1').slick({
		  centerMode: true,
		  centerPadding: '0%',
		  slidesToShow: 1,
		   dots: false,
		   waitForAnimate: false,
		   arrows: false,
		   speed:400,
		   variableWidth: true,
		   autoplay: true,
		   autoplaySpeed: 4000,
		    responsive: [
			    {
			      breakpoint: 992,
			      settings: {
			        dots: false,
		   			arrows: false,
		   			slidesToShow: 3
			      }
			    }
			  ]
		});


	assignSiblingClasses($(".slick-current"));
    $(".app_iphone_screen").on("beforeChange", function(event, slick, currentSlide, nextSlide) {
        $('.app_item.active').removeClass('active');
        $(".app_features").find("[data-slideindex='" + nextSlide + "']").addClass('active');
    });
    $(".app_iphone_screen").on("afterChange", function() {
        if ($(".slick-cloned").hasClass("current-slide")) $(".slick-cloned").removeClass("current-slide")
    });


	$('.app_item').mouseover(function(){
		$('.app_item.active').removeClass('active');
		$(this).addClass('active');
		var index = $(this).data('slideindex');
		$('.app_iphone_screen').slick('slickGoTo',parseInt(index));
	});


	function assignSiblingClasses(target) {
		var previousSlide = target.prev(".screen_item");
		var nextSlide = target.next(".screen_item");
		var outlierPreviousSlide = previousSlide.prev(".screen_item");
		var outlierNextSlide = nextSlide.next(".screen_item");
		var allPositionClasses = "current-slide sibling-slide outlier-slide slide-position-1";
		target.removeClass(allPositionClasses).addClass("current-slide");
		previousSlide.removeClass(allPositionClasses).addClass("sibling-slide");
		nextSlide.removeClass(allPositionClasses).addClass("sibling-slide");
		outlierPreviousSlide.removeClass(allPositionClasses).addClass("outlier-slide");
		outlierNextSlide.removeClass(allPositionClasses).addClass("outlier-slide")
		}

# Sync JazzHR posts to wordpress custom field:
	JazzHR api library:
	https://github.com/jordanandree/jazz-api
	
	
	function fetchCareer ()
	{//Get job posts from jazzHR API
    require "jazzAPI/jazz.php";
    $jazz = new Jazz("apiKEY");
    $jazz->cache['ENABLED'] = false;
    $subdomain = "domain"; // subdomain for you company jazz domain
    $jobs = $jazz->getJobs(array(
        "status" => "open", // open jobs
    ));
    foreach ($jobs as $job) {
        if (!empty($job->id)) {
            $argsCareer = [
                        'meta_key' => 'position_id',
                        'meta_value' => $job->board_code,
                        'post_type' => 'career',
                        ];
            $the_query = new WP_Query($argsCareer);
            if (!empty($the_query->posts)) {
                foreach ($the_query->posts as $post) {
                    $value_career = get_field('position_id', $post->ID);
                    if ($value_career == $job->board_code) {
                        $args = [
                            'ID' => $the_query->post->ID,
                            'post_title' => $job->title,
                            'post_content' => $job->description,
                            'post_status' => 'publish',
                            'post_author' => 1,
                            'post_type' => 'career',
                            'post_date' => $job->original_open_date
                        ];
                        $post_id_update = wp_update_post($args);
                        if (!is_wp_error($post_id_update)) {
                            update_field('position_type', $job->department, $post_id_update);
                            update_field('position_title', $job->title, $post_id_update);
                            update_field('position_location', $job->city . ', ' . $job->state, $post_id_update);
                            update_field('position_link', 'http://' . $subdomain . $job->board_code, $post_id_update);
                            update_field('position_id', $job->board_code, $post_id_update);
                        } else {
                            echo $post_id_update->get_error_message();
                        }
                    } else {
                        $args = [
                            'post_title' => $job->title,
                            'post_content' => $job->description,
                            'post_status' => 'publish',
                            'post_author' => 1,
                            'post_type' => 'career',
                            'post_date' => $job->original_open_date
                        ];
                        $post_id_insert = wp_insert_post($args);
                        if (!is_wp_error($post_id_insert)) {
                            update_field('position_type', $job->department, $post_id_insert);
                            update_field('position_title', $job->title, $post_id_insert);
                            update_field('position_location', $job->city . ', ' . $job->state, $post_id_insert);
                            update_field('position_link', 'http://' . $subdomain . $job->board_code, $post_id_insert);
                            update_field('position_id', $job->board_code, $post_id_insert);
                        } else {
                            echo $post_id_insert->get_error_message();
                        }
                    }
                }
            } else {
                $args = [
                    'post_title' => $job->title,
                    'post_content' => $job->description,
                    'post_status' => 'publish',
                    'post_author' => 1,
                    'post_type' => 'career',
                    'post_date' => $job->original_open_date
                ];
                $post_id_insert = wp_insert_post($args);
                print_r($post_id_insert);
                if (!is_wp_error($post_id_insert)) {
                    update_field('position_type', $job->department, $post_id_insert);
                            update_field('position_title', $job->title, $post_id_insert);
                            update_field('position_location', $job->city . ', ' . $job->state, $post_id_insert);
                            update_field('position_link', 'http://' . $subdomain . $job->board_code, $post_id_insert);
                            update_field('position_id', $job->board_code, $post_id_insert);
                } else {
                    echo $post_id_insert->get_error_message();
                }
            }
            wp_reset_postdata();
        }
    }
	}
	


				
	
# FileZilla to connect to server:
	Use SFTP:
	1. host: should be ip address;
	2. Username: should be username of the server;
	3. Password: should be password of the server;
	4. Port: 22
	and then connect to server;
	5. Choose local site which want to store the downloaded files and choose the remote site in the server.

# Clone bitbucket repository to php storm and configure the deployment:

	1. In Bitbucket: clone the repository(clone the link).
	2. In phpstorm: menu->vcs->checkout from verson control->git->paste BB url(Dirctory: /phpstomProjects)
	3. Menu: Tools->Deployment->configuration,
		 type SFTP,
		 SFTP host: server ip, port:22
		 Root Path: /home/giatec/web/wenbo.giatecscientific.com/public_html/landingpage  (this is put under wordpress package)
		 user name: namefor server
		 password: name for password
		 mappings: deployment path:/
	4. Tools->Deployment->options->ctrl+s/upload external changes
	5. upload local file to server

# Server Knowledge:
	1. Setup Server:
		a.setup aws account
		b.follow this link (https://www.nginx.com/blog/setting-up-nginx/#open-web-page) to setup ubuntu instance in 			the server;
		c.install vestacp to the ubuntu instance in server: follow this link (https://www.clickittech.com/control-			panels/install-vestacp-aws/)(https://vestacp.com/install/)
		d.configure vestacp: edit USER, set password
		e.use filezilla to upload file to server (ip:xx.xx.xxx.xx; username:admin; password:xxx)
		
# AWS how to increase volumn:
	https://stackoverflow.com/questions/6151695/ec2-instance-on-amazon-and-i-am-greeted-with-no-space-left-on-the-disk
	
# migrate all items from server to server:

	1. ssh to the server that wants to store all items:
		ssh to aws server
		a. aws instance connection
		b. after installl vestacp, terminal ssh admin@xx.xxx.xxx.xx
	2. use scp to migrate all files from original server to new server:
		sudo scp admin@xx.xx.xxx.xx:/backup/admin.2019-03-04_05-18-05.tar /backup


	3. restore all items in new server: 
		sudo /usr/local/vesta/bin/v-restore-user admin admin.2019-03-05_05-21-51.tar

	4. configure domain: a. add new web in vesta
			     b. move all files under public_html to new web's public_html
				sudo mv /home/admin/web/wenboge.ca/public_html/* /home/admin/web/xxxxx/public_html
			     c. update DB password
	5. point domain to new IP:
		a. In vestacp: the domain should be identical to godaddy domain
			for example: domain in vestacp: wenboge.ca;
				     domain in godaddy: wenboge.ca;
		b. Pointing domain name to ip in godaddy:
		https://gethelp.wildapricot.com/en/articles/549-changing-your-dns-settings-to-point-to-a-different-ip-address

# Ubuntu low space on disk
	1. sudo du -hx --max-depth=1/
	2. sudo ls -la /root/.local/share/Trash/files
	3. sudo rm -rf /root/.local/share/Trash
	
	   To clear the backup files in Ubuntu
	1. Terminal: cd /
	2. cd backup
	3. ls
	4. sudo rm -r *
