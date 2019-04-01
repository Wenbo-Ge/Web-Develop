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
