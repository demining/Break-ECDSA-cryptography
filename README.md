<!DOCTYPE html>
<!-- saved from url=(0051)https://cryptodeeptech.ru/break-ecdsa-cryptography/ -->
<html lang="ru-RU"><head><meta http-equiv="Content-Type" content="text/html; charset=UTF-8">
	
	<meta name="viewport" content="width=device-width, initial-scale=1">
	<link rel="profile" href="https://gmpg.org/xfn/11">

	<meta name="robots" content="index, follow, max-image-preview:large, max-snippet:-1, max-video-preview:-1">

	<!-- This site is optimized with the Yoast SEO plugin v19.2 - https://yoast.com/wordpress/plugins/seo/ -->
	<style type="text/css"></style><title>The very first serious vulnerability in Blockchain and how to get the public key Bitcoin ECDSA RSZ value from the RawTX file - «CRYPTO DEEP TECH»</title>
	<meta name="description" content="Let&#39;s remember the very first serious vulnerability in the Blockchain transaction and find out how to get the public key Bitcoin ECDSA value RSZ">
	<link rel="canonical" href="https://cryptodeeptech.ru/break-ecdsa-cryptography/">
	<meta property="og:locale" content="ru_RU">
	<meta property="og:type" content="article">
	<meta property="og:title" content="The very first serious vulnerability in Blockchain and how to get the public key Bitcoin ECDSA RSZ value from the RawTX file - «CRYPTO DEEP TECH»">
	<meta property="og:description" content="Let&#39;s remember the very first serious vulnerability in the Blockchain transaction and find out how to get the public key Bitcoin ECDSA value RSZ">
	<meta property="og:url" content="https://cryptodeeptech.ru/break-ecdsa-cryptography/">
	<meta property="og:site_name" content="«CRYPTO DEEP TECH»">
	<meta property="article:published_time" content="2022-07-04T18:53:38+00:00">
	<meta property="article:modified_time" content="2022-08-25T19:19:27+00:00">
	<meta property="og:image" content="https://habrastorage.org/r/w1560/getpro/habr/upload_files/20d/674/8c4/20d6748c4bdd5e28ada4e9d06b9e8d35.png">
	<meta name="author" content="Crypto Deep Tech">
	<meta name="twitter:card" content="summary_large_image">
	<meta name="twitter:label1" content="Написано автором">
	<meta name="twitter:data1" content="Crypto Deep Tech">
	<meta name="twitter:label2" content="Примерное время для чтения">
	<meta name="twitter:data2" content="7 минут">
	<script async="" src="./The very first serious vulnerability in Blockchain and how to get the public key Bitcoin ECDSA RSZ value from the RawTX file - «CRYPTO DEEP TECH»_files/tag.js"></script><script type="application/ld+json" class="yoast-schema-graph">{"@context":"https://schema.org","@graph":[{"@type":"WebSite","@id":"https://cryptodeeptech.ru/#website","url":"https://cryptodeeptech.ru/","name":"«CRYPTO DEEP TECH»","description":"Cryptanalysis and data financial security services","potentialAction":[{"@type":"SearchAction","target":{"@type":"EntryPoint","urlTemplate":"https://cryptodeeptech.ru/?s={search_term_string}"},"query-input":"required name=search_term_string"}],"inLanguage":"ru-RU"},{"@type":"ImageObject","inLanguage":"ru-RU","@id":"https://cryptodeeptech.ru/break-ecdsa-cryptography/#primaryimage","url":"https://habrastorage.org/r/w1560/getpro/habr/upload_files/20d/674/8c4/20d6748c4bdd5e28ada4e9d06b9e8d35.png","contentUrl":"https://habrastorage.org/r/w1560/getpro/habr/upload_files/20d/674/8c4/20d6748c4bdd5e28ada4e9d06b9e8d35.png"},{"@type":"WebPage","@id":"https://cryptodeeptech.ru/break-ecdsa-cryptography/#webpage","url":"https://cryptodeeptech.ru/break-ecdsa-cryptography/","name":"The very first serious vulnerability in Blockchain and how to get the public key Bitcoin ECDSA RSZ value from the RawTX file - «CRYPTO DEEP TECH»","isPartOf":{"@id":"https://cryptodeeptech.ru/#website"},"primaryImageOfPage":{"@id":"https://cryptodeeptech.ru/break-ecdsa-cryptography/#primaryimage"},"datePublished":"2022-07-04T18:53:38+00:00","dateModified":"2022-08-25T19:19:27+00:00","author":{"@id":"https://cryptodeeptech.ru/#/schema/person/0ef8ac0f63991970628a3a6587f9e6c0"},"description":"Let's remember the very first serious vulnerability in the Blockchain transaction and find out how to get the public key Bitcoin ECDSA value RSZ","breadcrumb":{"@id":"https://cryptodeeptech.ru/break-ecdsa-cryptography/#breadcrumb"},"inLanguage":"ru-RU","potentialAction":[{"@type":"ReadAction","target":["https://cryptodeeptech.ru/break-ecdsa-cryptography/"]}]},{"@type":"BreadcrumbList","@id":"https://cryptodeeptech.ru/break-ecdsa-cryptography/#breadcrumb","itemListElement":[{"@type":"ListItem","position":1,"name":"Главная страница","item":"https://cryptodeeptech.ru/"},{"@type":"ListItem","position":2,"name":"The very first serious vulnerability in Blockchain and how to get the public key Bitcoin ECDSA RSZ value from the RawTX file"}]},{"@type":"Person","@id":"https://cryptodeeptech.ru/#/schema/person/0ef8ac0f63991970628a3a6587f9e6c0","name":"Crypto Deep Tech","sameAs":["https://cryptodeeptech.ru","https://www.youtube.com/channel/UCd8W6qtRSiBn0Q0wy6HuNkQ/"],"url":"https://cryptodeeptech.ru/author/cryptodeeptech/"}]}</script>
	<!-- / Yoast SEO plugin. -->


<link rel="dns-prefetch" href="https://fonts.googleapis.com/">
<link rel="alternate" type="application/rss+xml" title="«CRYPTO DEEP TECH» » Лента" href="https://cryptodeeptech.ru/feed/">
<link rel="alternate" type="application/rss+xml" title="«CRYPTO DEEP TECH» » Лента комментариев" href="https://cryptodeeptech.ru/comments/feed/">
<link rel="alternate" type="application/rss+xml" title="«CRYPTO DEEP TECH» » Лента комментариев к «The very first serious vulnerability in Blockchain and how to get the public key Bitcoin ECDSA RSZ value from the RawTX file»" href="https://cryptodeeptech.ru/break-ecdsa-cryptography/feed/">
<link rel="stylesheet" id="itng-block-style-css" href="./The very first serious vulnerability in Blockchain and how to get the public key Bitcoin ECDSA RSZ value from the RawTX file - «CRYPTO DEEP TECH»_files/wmac_single_8f426a1779caff96bb3f2afbcff86bc9.css" media="all">
<link rel="stylesheet" id="wp-block-library-css" href="./The very first serious vulnerability in Blockchain and how to get the public key Bitcoin ECDSA RSZ value from the RawTX file - «CRYPTO DEEP TECH»_files/style.min.css" media="all">
<style id="global-styles-inline-css">
body{--wp--preset--color--black: #000000;--wp--preset--color--cyan-bluish-gray: #abb8c3;--wp--preset--color--white: #ffffff;--wp--preset--color--pale-pink: #f78da7;--wp--preset--color--vivid-red: #cf2e2e;--wp--preset--color--luminous-vivid-orange: #ff6900;--wp--preset--color--luminous-vivid-amber: #fcb900;--wp--preset--color--light-green-cyan: #7bdcb5;--wp--preset--color--vivid-green-cyan: #00d084;--wp--preset--color--pale-cyan-blue: #8ed1fc;--wp--preset--color--vivid-cyan-blue: #0693e3;--wp--preset--color--vivid-purple: #9b51e0;--wp--preset--gradient--vivid-cyan-blue-to-vivid-purple: linear-gradient(135deg,rgba(6,147,227,1) 0%,rgb(155,81,224) 100%);--wp--preset--gradient--light-green-cyan-to-vivid-green-cyan: linear-gradient(135deg,rgb(122,220,180) 0%,rgb(0,208,130) 100%);--wp--preset--gradient--luminous-vivid-amber-to-luminous-vivid-orange: linear-gradient(135deg,rgba(252,185,0,1) 0%,rgba(255,105,0,1) 100%);--wp--preset--gradient--luminous-vivid-orange-to-vivid-red: linear-gradient(135deg,rgba(255,105,0,1) 0%,rgb(207,46,46) 100%);--wp--preset--gradient--very-light-gray-to-cyan-bluish-gray: linear-gradient(135deg,rgb(238,238,238) 0%,rgb(169,184,195) 100%);--wp--preset--gradient--cool-to-warm-spectrum: linear-gradient(135deg,rgb(74,234,220) 0%,rgb(151,120,209) 20%,rgb(207,42,186) 40%,rgb(238,44,130) 60%,rgb(251,105,98) 80%,rgb(254,248,76) 100%);--wp--preset--gradient--blush-light-purple: linear-gradient(135deg,rgb(255,206,236) 0%,rgb(152,150,240) 100%);--wp--preset--gradient--blush-bordeaux: linear-gradient(135deg,rgb(254,205,165) 0%,rgb(254,45,45) 50%,rgb(107,0,62) 100%);--wp--preset--gradient--luminous-dusk: linear-gradient(135deg,rgb(255,203,112) 0%,rgb(199,81,192) 50%,rgb(65,88,208) 100%);--wp--preset--gradient--pale-ocean: linear-gradient(135deg,rgb(255,245,203) 0%,rgb(182,227,212) 50%,rgb(51,167,181) 100%);--wp--preset--gradient--electric-grass: linear-gradient(135deg,rgb(202,248,128) 0%,rgb(113,206,126) 100%);--wp--preset--gradient--midnight: linear-gradient(135deg,rgb(2,3,129) 0%,rgb(40,116,252) 100%);--wp--preset--duotone--dark-grayscale: url('#wp-duotone-dark-grayscale');--wp--preset--duotone--grayscale: url('#wp-duotone-grayscale');--wp--preset--duotone--purple-yellow: url('#wp-duotone-purple-yellow');--wp--preset--duotone--blue-red: url('#wp-duotone-blue-red');--wp--preset--duotone--midnight: url('#wp-duotone-midnight');--wp--preset--duotone--magenta-yellow: url('#wp-duotone-magenta-yellow');--wp--preset--duotone--purple-green: url('#wp-duotone-purple-green');--wp--preset--duotone--blue-orange: url('#wp-duotone-blue-orange');--wp--preset--font-size--small: 13px;--wp--preset--font-size--medium: 20px;--wp--preset--font-size--large: 36px;--wp--preset--font-size--x-large: 42px;}.has-black-color{color: var(--wp--preset--color--black) !important;}.has-cyan-bluish-gray-color{color: var(--wp--preset--color--cyan-bluish-gray) !important;}.has-white-color{color: var(--wp--preset--color--white) !important;}.has-pale-pink-color{color: var(--wp--preset--color--pale-pink) !important;}.has-vivid-red-color{color: var(--wp--preset--color--vivid-red) !important;}.has-luminous-vivid-orange-color{color: var(--wp--preset--color--luminous-vivid-orange) !important;}.has-luminous-vivid-amber-color{color: var(--wp--preset--color--luminous-vivid-amber) !important;}.has-light-green-cyan-color{color: var(--wp--preset--color--light-green-cyan) !important;}.has-vivid-green-cyan-color{color: var(--wp--preset--color--vivid-green-cyan) !important;}.has-pale-cyan-blue-color{color: var(--wp--preset--color--pale-cyan-blue) !important;}.has-vivid-cyan-blue-color{color: var(--wp--preset--color--vivid-cyan-blue) !important;}.has-vivid-purple-color{color: var(--wp--preset--color--vivid-purple) !important;}.has-black-background-color{background-color: var(--wp--preset--color--black) !important;}.has-cyan-bluish-gray-background-color{background-color: var(--wp--preset--color--cyan-bluish-gray) !important;}.has-white-background-color{background-color: var(--wp--preset--color--white) !important;}.has-pale-pink-background-color{background-color: var(--wp--preset--color--pale-pink) !important;}.has-vivid-red-background-color{background-color: var(--wp--preset--color--vivid-red) !important;}.has-luminous-vivid-orange-background-color{background-color: var(--wp--preset--color--luminous-vivid-orange) !important;}.has-luminous-vivid-amber-background-color{background-color: var(--wp--preset--color--luminous-vivid-amber) !important;}.has-light-green-cyan-background-color{background-color: var(--wp--preset--color--light-green-cyan) !important;}.has-vivid-green-cyan-background-color{background-color: var(--wp--preset--color--vivid-green-cyan) !important;}.has-pale-cyan-blue-background-color{background-color: var(--wp--preset--color--pale-cyan-blue) !important;}.has-vivid-cyan-blue-background-color{background-color: var(--wp--preset--color--vivid-cyan-blue) !important;}.has-vivid-purple-background-color{background-color: var(--wp--preset--color--vivid-purple) !important;}.has-black-border-color{border-color: var(--wp--preset--color--black) !important;}.has-cyan-bluish-gray-border-color{border-color: var(--wp--preset--color--cyan-bluish-gray) !important;}.has-white-border-color{border-color: var(--wp--preset--color--white) !important;}.has-pale-pink-border-color{border-color: var(--wp--preset--color--pale-pink) !important;}.has-vivid-red-border-color{border-color: var(--wp--preset--color--vivid-red) !important;}.has-luminous-vivid-orange-border-color{border-color: var(--wp--preset--color--luminous-vivid-orange) !important;}.has-luminous-vivid-amber-border-color{border-color: var(--wp--preset--color--luminous-vivid-amber) !important;}.has-light-green-cyan-border-color{border-color: var(--wp--preset--color--light-green-cyan) !important;}.has-vivid-green-cyan-border-color{border-color: var(--wp--preset--color--vivid-green-cyan) !important;}.has-pale-cyan-blue-border-color{border-color: var(--wp--preset--color--pale-cyan-blue) !important;}.has-vivid-cyan-blue-border-color{border-color: var(--wp--preset--color--vivid-cyan-blue) !important;}.has-vivid-purple-border-color{border-color: var(--wp--preset--color--vivid-purple) !important;}.has-vivid-cyan-blue-to-vivid-purple-gradient-background{background: var(--wp--preset--gradient--vivid-cyan-blue-to-vivid-purple) !important;}.has-light-green-cyan-to-vivid-green-cyan-gradient-background{background: var(--wp--preset--gradient--light-green-cyan-to-vivid-green-cyan) !important;}.has-luminous-vivid-amber-to-luminous-vivid-orange-gradient-background{background: var(--wp--preset--gradient--luminous-vivid-amber-to-luminous-vivid-orange) !important;}.has-luminous-vivid-orange-to-vivid-red-gradient-background{background: var(--wp--preset--gradient--luminous-vivid-orange-to-vivid-red) !important;}.has-very-light-gray-to-cyan-bluish-gray-gradient-background{background: var(--wp--preset--gradient--very-light-gray-to-cyan-bluish-gray) !important;}.has-cool-to-warm-spectrum-gradient-background{background: var(--wp--preset--gradient--cool-to-warm-spectrum) !important;}.has-blush-light-purple-gradient-background{background: var(--wp--preset--gradient--blush-light-purple) !important;}.has-blush-bordeaux-gradient-background{background: var(--wp--preset--gradient--blush-bordeaux) !important;}.has-luminous-dusk-gradient-background{background: var(--wp--preset--gradient--luminous-dusk) !important;}.has-pale-ocean-gradient-background{background: var(--wp--preset--gradient--pale-ocean) !important;}.has-electric-grass-gradient-background{background: var(--wp--preset--gradient--electric-grass) !important;}.has-midnight-gradient-background{background: var(--wp--preset--gradient--midnight) !important;}.has-small-font-size{font-size: var(--wp--preset--font-size--small) !important;}.has-medium-font-size{font-size: var(--wp--preset--font-size--medium) !important;}.has-large-font-size{font-size: var(--wp--preset--font-size--large) !important;}.has-x-large-font-size{font-size: var(--wp--preset--font-size--x-large) !important;}
</style>
<link rel="stylesheet" id="wp-date-remover-css" href="./The very first serious vulnerability in Blockchain and how to get the public key Bitcoin ECDSA RSZ value from the RawTX file - «CRYPTO DEEP TECH»_files/wmac_single_e6094661d8923e95b233019ebff7c8f0.css" media="all">
<link rel="stylesheet" id="itng-fonts-css" href="./The very first serious vulnerability in Blockchain and how to get the public key Bitcoin ECDSA RSZ value from the RawTX file - «CRYPTO DEEP TECH»_files/css" media="all">
<link rel="stylesheet" id="itng-style-css" href="./The very first serious vulnerability in Blockchain and how to get the public key Bitcoin ECDSA RSZ value from the RawTX file - «CRYPTO DEEP TECH»_files/wmac_single_8de4505c66a21eefd3c1c98b6400e4e1.css" media="all">
<link rel="stylesheet" id="itng-main-style-css" href="./The very first serious vulnerability in Blockchain and how to get the public key Bitcoin ECDSA RSZ value from the RawTX file - «CRYPTO DEEP TECH»_files/wmac_single_d1cf6f49400112d539e59eee9b75e10d.css" media="all">
<style id="itng-main-style-inline-css">
.custom-logo-link img {width: 400px;}@media screen and (min-width: 992px) {#header-image .header-overlay {
            opacity: 0.01;
        }}
ins,
	.nav-wrapper,
	#menu,
	.main-navigation ul#menu-desktop ul,
	#itng-featured-news .slider-post-wrapper .posted-on a,
	#itng-featured-news #itng-featured-news-list-container .posted-on a,
	#itng-featured-posts .itng-featured-post-date,
	#itng-featured-news #itng-featured-news-carousel-container .posted-on a,
	#colophon,
	[class^=itng-search] form,
	#itng-featured-cat .featured-cat-thumb h2,
	#itng-featured-cat .featured-cat-thumb h3
	{background-color: #008bca}article .entry-meta a,
	article .blog-footer,
	article .blog-footer a,
	.widget a,
	.nav-links a,
	.itng-pagination .nav-links > a,
	.itng-pagination .dots
	{color: #008bca !important}blockquote,
	#itng-content-title span
	{border-color: #008bca}button.top-menu-mobile
	{background-color: #43bdf2 !important}#footer-sidebar .widget-title
	{color: #43bdf2 !important}
</style>
<link rel="stylesheet" id="bootstrap-css" href="./The very first serious vulnerability in Blockchain and how to get the public key Bitcoin ECDSA RSZ value from the RawTX file - «CRYPTO DEEP TECH»_files/wmac_single_d26191bd0380b0cf97525a613b8b566c.css" media="all">
<link rel="stylesheet" id="owl-css" href="./The very first serious vulnerability in Blockchain and how to get the public key Bitcoin ECDSA RSZ value from the RawTX file - «CRYPTO DEEP TECH»_files/wmac_single_c8322bd5bffc8e2856f2cbcd03c61d18.css" media="all">
<link rel="stylesheet" id="mag-popup-css" href="./The very first serious vulnerability in Blockchain and how to get the public key Bitcoin ECDSA RSZ value from the RawTX file - «CRYPTO DEEP TECH»_files/wmac_single_30b593b71d7672658f89bfea0ab360c9.css" media="all">
<link rel="stylesheet" id="font-awesome-css" href="./The very first serious vulnerability in Blockchain and how to get the public key Bitcoin ECDSA RSZ value from the RawTX file - «CRYPTO DEEP TECH»_files/wmac_single_c495654869785bc3df60216616814ad1.css" media="all">
<script src="./The very first serious vulnerability in Blockchain and how to get the public key Bitcoin ECDSA RSZ value from the RawTX file - «CRYPTO DEEP TECH»_files/jquery.min.js" id="jquery-core-js"></script>
<script src="./The very first serious vulnerability in Blockchain and how to get the public key Bitcoin ECDSA RSZ value from the RawTX file - «CRYPTO DEEP TECH»_files/jquery-migrate.min.js" id="jquery-migrate-js"></script>
<script src="./The very first serious vulnerability in Blockchain and how to get the public key Bitcoin ECDSA RSZ value from the RawTX file - «CRYPTO DEEP TECH»_files/wmac_single_49cea0a781874a962879c2caca9bc322.js" id="wp-date-remover-js"></script>
<link rel="https://api.w.org/" href="https://cryptodeeptech.ru/wp-json/"><link rel="alternate" type="application/json" href="https://cryptodeeptech.ru/wp-json/wp/v2/posts/112"><meta name="generator" content="WordPress 6.0.1">
<link rel="alternate" type="application/json+oembed" href="https://cryptodeeptech.ru/wp-json/oembed/1.0/embed?url=https%3A%2F%2Fcryptodeeptech.ru%2Fbreak-ecdsa-cryptography%2F">
<link rel="alternate" type="text/xml+oembed" href="https://cryptodeeptech.ru/wp-json/oembed/1.0/embed?url=https%3A%2F%2Fcryptodeeptech.ru%2Fbreak-ecdsa-cryptography%2F&amp;format=xml">
<link rel="pingback" href="https://cryptodeeptech.ru/xmlrpc.php">		<style type="text/css">
						#header-image {
						background-image: url(https://cryptodeeptech.ru/wp-content/uploads/2022/07/header3.jpg);
						background-size: cover;
						background-repeat: repeat;
						background-position: center center;
				}
							.site-title, .site-description {
				display: none;
				position: absolute;
				clip: rect(1px, 1px, 1px, 1px);
				}
					</style>
		<style id="custom-background-css">
body.custom-background { background-color: #eff3fd; }
</style>
	<link rel="icon" href="https://cryptodeeptech.ru/wp-content/uploads/2022/07/cropped-favicon7-32x32.png" sizes="32x32">
<link rel="icon" href="https://cryptodeeptech.ru/wp-content/uploads/2022/07/cropped-favicon7-192x192.png" sizes="192x192">
<link rel="apple-touch-icon" href="https://cryptodeeptech.ru/wp-content/uploads/2022/07/cropped-favicon7-180x180.png">
<meta name="msapplication-TileImage" content="https://cryptodeeptech.ru/wp-content/uploads/2022/07/cropped-favicon7-270x270.png">
</head>

<body data-rsssl="1" class="post-template-default single single-post postid-112 single-format-standard custom-background wp-custom-logo no-sidebar">
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 0 0" width="0" height="0" focusable="false" role="none" style="visibility: hidden; position: absolute; left: -9999px; overflow: hidden;"><defs><filter id="wp-duotone-dark-grayscale"><fecolormatrix color-interpolation-filters="sRGB" type="matrix" values=" .299 .587 .114 0 0 .299 .587 .114 0 0 .299 .587 .114 0 0 .299 .587 .114 0 0 "></fecolormatrix><fecomponenttransfer color-interpolation-filters="sRGB"><fefuncr type="table" tableValues="0 0.49803921568627"></fefuncr><fefuncg type="table" tableValues="0 0.49803921568627"></fefuncg><fefuncb type="table" tableValues="0 0.49803921568627"></fefuncb><fefunca type="table" tableValues="1 1"></fefunca></fecomponenttransfer><fecomposite in2="SourceGraphic" operator="in"></fecomposite></filter></defs></svg><svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 0 0" width="0" height="0" focusable="false" role="none" style="visibility: hidden; position: absolute; left: -9999px; overflow: hidden;"><defs><filter id="wp-duotone-grayscale"><fecolormatrix color-interpolation-filters="sRGB" type="matrix" values=" .299 .587 .114 0 0 .299 .587 .114 0 0 .299 .587 .114 0 0 .299 .587 .114 0 0 "></fecolormatrix><fecomponenttransfer color-interpolation-filters="sRGB"><fefuncr type="table" tableValues="0 1"></fefuncr><fefuncg type="table" tableValues="0 1"></fefuncg><fefuncb type="table" tableValues="0 1"></fefuncb><fefunca type="table" tableValues="1 1"></fefunca></fecomponenttransfer><fecomposite in2="SourceGraphic" operator="in"></fecomposite></filter></defs></svg><svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 0 0" width="0" height="0" focusable="false" role="none" style="visibility: hidden; position: absolute; left: -9999px; overflow: hidden;"><defs><filter id="wp-duotone-purple-yellow"><fecolormatrix color-interpolation-filters="sRGB" type="matrix" values=" .299 .587 .114 0 0 .299 .587 .114 0 0 .299 .587 .114 0 0 .299 .587 .114 0 0 "></fecolormatrix><fecomponenttransfer color-interpolation-filters="sRGB"><fefuncr type="table" tableValues="0.54901960784314 0.98823529411765"></fefuncr><fefuncg type="table" tableValues="0 1"></fefuncg><fefuncb type="table" tableValues="0.71764705882353 0.25490196078431"></fefuncb><fefunca type="table" tableValues="1 1"></fefunca></fecomponenttransfer><fecomposite in2="SourceGraphic" operator="in"></fecomposite></filter></defs></svg><svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 0 0" width="0" height="0" focusable="false" role="none" style="visibility: hidden; position: absolute; left: -9999px; overflow: hidden;"><defs><filter id="wp-duotone-blue-red"><fecolormatrix color-interpolation-filters="sRGB" type="matrix" values=" .299 .587 .114 0 0 .299 .587 .114 0 0 .299 .587 .114 0 0 .299 .587 .114 0 0 "></fecolormatrix><fecomponenttransfer color-interpolation-filters="sRGB"><fefuncr type="table" tableValues="0 1"></fefuncr><fefuncg type="table" tableValues="0 0.27843137254902"></fefuncg><fefuncb type="table" tableValues="0.5921568627451 0.27843137254902"></fefuncb><fefunca type="table" tableValues="1 1"></fefunca></fecomponenttransfer><fecomposite in2="SourceGraphic" operator="in"></fecomposite></filter></defs></svg><svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 0 0" width="0" height="0" focusable="false" role="none" style="visibility: hidden; position: absolute; left: -9999px; overflow: hidden;"><defs><filter id="wp-duotone-midnight"><fecolormatrix color-interpolation-filters="sRGB" type="matrix" values=" .299 .587 .114 0 0 .299 .587 .114 0 0 .299 .587 .114 0 0 .299 .587 .114 0 0 "></fecolormatrix><fecomponenttransfer color-interpolation-filters="sRGB"><fefuncr type="table" tableValues="0 0"></fefuncr><fefuncg type="table" tableValues="0 0.64705882352941"></fefuncg><fefuncb type="table" tableValues="0 1"></fefuncb><fefunca type="table" tableValues="1 1"></fefunca></fecomponenttransfer><fecomposite in2="SourceGraphic" operator="in"></fecomposite></filter></defs></svg><svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 0 0" width="0" height="0" focusable="false" role="none" style="visibility: hidden; position: absolute; left: -9999px; overflow: hidden;"><defs><filter id="wp-duotone-magenta-yellow"><fecolormatrix color-interpolation-filters="sRGB" type="matrix" values=" .299 .587 .114 0 0 .299 .587 .114 0 0 .299 .587 .114 0 0 .299 .587 .114 0 0 "></fecolormatrix><fecomponenttransfer color-interpolation-filters="sRGB"><fefuncr type="table" tableValues="0.78039215686275 1"></fefuncr><fefuncg type="table" tableValues="0 0.94901960784314"></fefuncg><fefuncb type="table" tableValues="0.35294117647059 0.47058823529412"></fefuncb><fefunca type="table" tableValues="1 1"></fefunca></fecomponenttransfer><fecomposite in2="SourceGraphic" operator="in"></fecomposite></filter></defs></svg><svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 0 0" width="0" height="0" focusable="false" role="none" style="visibility: hidden; position: absolute; left: -9999px; overflow: hidden;"><defs><filter id="wp-duotone-purple-green"><fecolormatrix color-interpolation-filters="sRGB" type="matrix" values=" .299 .587 .114 0 0 .299 .587 .114 0 0 .299 .587 .114 0 0 .299 .587 .114 0 0 "></fecolormatrix><fecomponenttransfer color-interpolation-filters="sRGB"><fefuncr type="table" tableValues="0.65098039215686 0.40392156862745"></fefuncr><fefuncg type="table" tableValues="0 1"></fefuncg><fefuncb type="table" tableValues="0.44705882352941 0.4"></fefuncb><fefunca type="table" tableValues="1 1"></fefunca></fecomponenttransfer><fecomposite in2="SourceGraphic" operator="in"></fecomposite></filter></defs></svg><svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 0 0" width="0" height="0" focusable="false" role="none" style="visibility: hidden; position: absolute; left: -9999px; overflow: hidden;"><defs><filter id="wp-duotone-blue-orange"><fecolormatrix color-interpolation-filters="sRGB" type="matrix" values=" .299 .587 .114 0 0 .299 .587 .114 0 0 .299 .587 .114 0 0 .299 .587 .114 0 0 "></fecolormatrix><fecomponenttransfer color-interpolation-filters="sRGB"><fefuncr type="table" tableValues="0.098039215686275 1"></fefuncr><fefuncg type="table" tableValues="0 0.66274509803922"></fefuncg><fefuncb type="table" tableValues="0.84705882352941 0.41960784313725"></fefuncb><fefunca type="table" tableValues="1 1"></fefunca></fecomponenttransfer><fecomposite in2="SourceGraphic" operator="in"></fecomposite></filter></defs></svg><div id="page" class="site">
	<a class="skip-link screen-reader-text" href="https://cryptodeeptech.ru/break-ecdsa-cryptography/#primary">Skip to content</a>

	
	    <header id="masthead" class="site-header style-1">

		    
	        <div id="header-image">
		        <div class="site-branding">
					<a href="https://cryptodeeptech.ru/" class="custom-logo-link" rel="home"><img width="1279" height="319" src="./The very first serious vulnerability in Blockchain and how to get the public key Bitcoin ECDSA RSZ value from the RawTX file - «CRYPTO DEEP TECH»_files/cropped-header4.png" class="custom-logo" alt="«CRYPTO DEEP TECH»" srcset="https://cryptodeeptech.ru/wp-content/uploads/2022/07/cropped-header4.png 1279w, https://cryptodeeptech.ru/wp-content/uploads/2022/07/cropped-header4-300x75.png 300w, https://cryptodeeptech.ru/wp-content/uploads/2022/07/cropped-header4-1024x255.png 1024w, https://cryptodeeptech.ru/wp-content/uploads/2022/07/cropped-header4-768x192.png 768w" sizes="(max-width: 1279px) 100vw, 1279px" title="The very first serious vulnerability in Blockchain and how to get the public key Bitcoin ECDSA RSZ value from the RawTX file"></a>	<h2 class="site-title"><a href="https://cryptodeeptech.ru/" rel="home">«CRYPTO DEEP TECH»</a></h2>
		<p class="site-description">Cryptanalysis and data financial security services</p>
	        	</div>
				<div class="header-overlay"></div>
	        </div>

			<div class="nav-wrapper">
				 <div class="container">
					 <div class="d-flex">

						<div id="site-navigation" class="main-navigation col-lg-11" role="navigation">
							<ul id="menu-desktop" class="menu"><li id="menu-item-229" class="menu-item menu-item-type-custom menu-item-object-custom menu-item-home menu-item-229"><a href="https://cryptodeeptech.ru/">HOME</a></li>
<li id="menu-item-225" class="menu-item menu-item-type-post_type menu-item-object-page menu-item-225"><a href="https://cryptodeeptech.ru/publication/">PUBLICATIONS</a></li>
<li id="menu-item-226" class="menu-item menu-item-type-post_type menu-item-object-page menu-item-226"><a href="https://cryptodeeptech.ru/study/">STUDY</a></li>
<li id="menu-item-227" class="menu-item menu-item-type-post_type menu-item-object-page menu-item-227"><a href="https://cryptodeeptech.ru/resources/">RESOURCES</a></li>
<li id="menu-item-228" class="menu-item menu-item-type-post_type menu-item-object-page menu-item-228"><a href="https://cryptodeeptech.ru/contacts/">CONTACTS</a></li>
<li id="menu-item-240" class="menu-item menu-item-type-post_type menu-item-object-post menu-item-240"><a href="https://cryptodeeptech.ru/lattice-attack/">BLOG</a></li>
</ul>						</div>

						<button href="#menu" class="menu-link mobile-nav-btn col-auto"><i class="fa fa-bars" aria-hidden="true"></i></button>

						<div id="search-wrapper" class="ml-auto col-auto d-flex">
							<button type="button" id="go-to-field" tabindex="-1"></button>
					    	<button class="search-btn-main"><i class="fa fa-search"></i></button>
					    	
<div class="itng-search-main">
	<form role="search" method="get" class="search-form" action="https://cryptodeeptech.ru/">
				<label>
					<span class="screen-reader-text">Найти:</span>
					<input type="search" class="search-field" placeholder="Поиск…" value="" name="s">
				</label>
				<input type="submit" class="search-submit" value="Поиск">
			</form>	<button type="button" id="go-to-btn" tabindex="-1"></button>
</div>
						</div>
					</div>
				</div>
			</div>

		</header><!-- #masthead -->
			<div id="content-wrapper" class="container row">
		
	<main id="primary" class="site-main container order-1">

		
<article id="post-112" class="post-112 post type-post status-publish format-standard hentry category-1">
	
	<header class="entry-header">
		<h1 class="entry-title">The very first serious vulnerability in Blockchain and how to get the public key Bitcoin ECDSA RSZ value from the RawTX file</h1>	</header><!-- .entry-header -->
	
	
	
			<div class="entry-meta">
			<span class="posted-on" style="display: none;"><a href="https://cryptodeeptech.ru/break-ecdsa-cryptography/" rel="bookmark"><time class="entry-date published" datetime="" style="display: none;"></time><time class="updated" datetime=""></time></a></span><span class="byline"> <span class="author vcard"><a class="url fn n" href="https://cryptodeeptech.ru/author/cryptodeeptech/">Crypto Deep Tech</a></span></span>		</div><!-- .entry-meta -->
		
	
	<div class="entry-content">
		<div class="entry-meta"></div>
<div class="entry-content">
<p class="has-text-align-center"><iframe title="Youtube video player" src="./The very first serious vulnerability in Blockchain and how to get the public key Bitcoin ECDSA RSZ value from the RawTX file - «CRYPTO DEEP TECH»_files/BYd-cuFRZmM.html" width="560" height="315" frameborder="0" allowfullscreen="allowfullscreen" data-mce-fragment="1"></iframe></p>
<p>In this article, we will talk about extracting signature values&nbsp;&nbsp;<code>ECDSA R, S, Z</code>&nbsp;​​from the Bitcoin blockchain, but first, let’s remember the very first serious vulnerability in the blockchain transaction that was discovered by&nbsp;&nbsp;Niels&nbsp;<a href="https://github.com/tcatm" target="_blank" rel="noreferrer noopener">Schneider</a>&nbsp;&nbsp;(&nbsp;<code>Nils Schneider</code>&nbsp;<em>aka</em>&nbsp;&nbsp;tcatm&nbsp;&nbsp;<a href="https://github.com/tcatm" target="_blank" rel="noreferrer noopener"><strong>)</strong></a></p>
<p>Bitcoin developer and owner&nbsp;&nbsp;<em>of «BitcoinWatch»</em>&nbsp;&nbsp;&amp;&nbsp;&nbsp;<em>«BitcoinCharts».</em></p>
<figure class="wp-block-image"><img title="4.1 History of dangerous random attacks on Bitcoin" src="./The very first serious vulnerability in Blockchain and how to get the public key Bitcoin ECDSA RSZ value from the RawTX file - «CRYPTO DEEP TECH»_files/20d6748c4bdd5e28ada4e9d06b9e8d35.png" alt="4.1 History of dangerous random attacks on Bitcoin"><figcaption>4.1 History of dangerous random attacks on Bitcoin</figcaption></figure>
<blockquote class="wp-block-quote"><p>Document&nbsp;&nbsp;<code>[PDF]</code>:&nbsp;<a href="https://eprint.iacr.org/2014/848.pdf" target="_blank" rel="noreferrer noopener"><em>Private Key Recovery Combination Attacks: On Extreme Fragility of Popular Bitcoin Key Management, Wallet and Cold Storage Solutions in Presence of Poor RNG Events</em></a><a href="https://eprint.iacr.org/2014/848.pdf" target="_blank" rel="noreferrer noopener">&nbsp;</a></p></blockquote>
<p><em>On December 25, 2012,</em>&nbsp;&nbsp;Nils discovered a potential weakness in some Bitcoin blockchain transactions.</p>
<p><strong>Look at this transaction:</strong></p>
<p><code>transaction:</code>&nbsp;<a href="https://www.blockchain.com/btc/tx/9ec4bc49e828d924af1d1029cacf709431abbde46d59554b62bc270e3b29c4b1" target="_blank" rel="noreferrer noopener">9ec4bc49e828d924af1d1029cacf709431abbde46d59554b62bc270e3b29c4b1</a></p>
<hr class="wp-block-separator has-alpha-channel-opacity">
<figure class="wp-block-image"><img src="./The very first serious vulnerability in Blockchain and how to get the public key Bitcoin ECDSA RSZ value from the RawTX file - «CRYPTO DEEP TECH»_files/cc32e294aa0e77019d1581ce61893349.png" alt="The very first serious vulnerability in Blockchain and how to get the public key Bitcoin ECDSA RSZ value from the RawTX file"></figure>
<hr class="wp-block-separator has-alpha-channel-opacity">
<pre class="wp-block-code"><code>input script 1:
30440220d47ce4c025c35ec440bc81d99834a624875161a26bf56ef7fdc0f5d52f843ad1022044e1ff2dfd8102cf7a47c21d5c9fd5701610d04953c6836596b4fe9dd2f53e3e0104dbd0c61532279cf72981c3584fc32216e0127699635c2789f549e0730c059b81ae133016a69c21e23f1859a95f06d52b7bf149a8f2fe4e8535c8a829b449c5ff

input script 2:
30440220d47ce4c025c35ec440bc81d99834a624875161a26bf56ef7fdc0f5d52f843ad102209a5f1c75e461d7ceb1cf3cab9013eb2dc85b6d0da8c3c6e27e3a5a5b3faa5bab0104dbd0c61532279cf72981c3584fc32216e0127699635c2789f549e0730c059b81ae133016a69c21e23f1859a95f06d52b7bf149a8f2fe4e8535c8a829b449c5ff</code></pre>
<p>This transaction has two inputs and one output.<br>
If you look closely at the two input scripts, you will notice that there are quite a few identical bytes at the beginning and at the end.<br>
Those bytes at the end are the hex encoded public key of the address the coins are being spent on, so there’s nothing wrong with that.<br>
However, the first half of the script is the actual signature&nbsp;&nbsp;<code>(r, s)</code>:</p>
<pre class="wp-block-code"><code>r1: d47ce4c025c35ec440bc81d99834a624875161a26bf56ef7fdc0f5d52f843ad1
r2: d47ce4c025c35ec440bc81d99834a624875161a26bf56ef7fdc0f5d52f843ad1

s1: 44e1ff2dfd8102cf7a47c21d5c9fd5701610d04953c6836596b4fe9dd2f53e3e
s2: 9a5f1c75e461d7ceb1cf3cab9013eb2dc85b6d0da8c3c6e27e3a5a5b3faa5bab</code></pre>
<blockquote class="wp-block-quote"><p>As you can see,&nbsp; it’s&nbsp;<code>r1</code>&nbsp;the same&nbsp;&nbsp;<code>r2</code>.&nbsp;<em>This is&nbsp;&nbsp;</em><strong><em><u>a huge problem</u></em></strong><em>&nbsp;.</em></p></blockquote>
<blockquote class="wp-block-quote"><p>We can restore the&nbsp;&nbsp;<strong><u>private key</u></strong>&nbsp;&nbsp;to this public key:</p>
<p><code>04dbd0c61532279cf72981c3584fc32216e0127699635c2789f549e0730c059b81ae133016a69c21e23f1859a95f06d52b7bf149a8f2fe4e8535c8a829b449c5ff</code></p></blockquote>
<p>To do this, we can use a simple formula from school algebra 😉</p>
<pre class="wp-block-code"><code>private key = (<strong>z1*s2</strong> - z2*s1)/(<strong>r*</strong>(<strong>s1-s2</strong>))</code></pre>
<p>We just need to find&nbsp;&nbsp;<code>z1</code>&nbsp;and&nbsp;<code>z2</code></p>
<p>These are&nbsp;&nbsp;<code>хэши</code>&nbsp;the outputs that need to be signed.&nbsp;Let’s get the output transactions and count them (computed by&nbsp;&nbsp;<code>OP_CHECKSIG</code>):</p>
<pre class="wp-block-code"><code>z1: c0e2d0a89a348de88fda08211c70d1d7e52ccef2eb9459911bf977d587784c6e
z2: 17b0f41c8c337ac1e18c98759e83a8cccbc368dd9d89e5f03cb633c265fd0ddc</code></pre>
<p>Next, we pack all these values ​​​​in one&nbsp;&nbsp;<em>Python</em>&nbsp;—&nbsp;<em>script:&nbsp;</em>&nbsp;<a href="https://github.com/demining/CryptoDeepTools/blob/main/02BreakECDSAcryptography/vulnerabilityR.py" target="_blank" rel="noreferrer noopener">vulnerabilityR.py</a></p>
<figure class="wp-block-image"><img title="Python script: vulnerabilityR.py" src="./The very first serious vulnerability in Blockchain and how to get the public key Bitcoin ECDSA RSZ value from the RawTX file - «CRYPTO DEEP TECH»_files/c5f301358b79c833d7701b7c883235a7.png" alt="Python script: vulnerabilityR.py"><figcaption>Python script: vulnerabilityR.py</figcaption></figure>
<p><code>p</code>&nbsp;is just an order&nbsp; of magnitude&nbsp;<code>G</code>, a parameter of the curve&nbsp;&nbsp;<code>secp256k1</code>used by Bitcoin.</p>
<p>Let’s create a field for our calculations:</p>
<pre class="wp-block-code"><code>K = GF(<strong>p</strong>)</code></pre>
<pre class="wp-block-code"><code>K((<strong>z1*s2</strong> - z2*s1)/(<strong>r*</strong>(<strong>s1-s2</strong>)))</code></pre>
<p>Let’s run the script:&nbsp;<code>python3 vulnerabilityR.py</code></p>
<p>Next, our script:&nbsp;&nbsp;<a href="https://github.com/demining/CryptoDeepTools/blob/main/02BreakECDSAcryptography/vulnerabilityR.py" target="_blank" rel="noreferrer noopener">vulnerabilityR.py</a>&nbsp;will &nbsp;calculate&nbsp;&nbsp;<strong><u>the private key</u></strong>&nbsp;&nbsp;in this field:</p>
<pre class="wp-block-code"><code>ADDR: 1BFhrfTTZP3Nw4BNy4eX4KFLsn9ZeijcMm
WIF:  5KJp7KEffR7HHFWSFYjiCUAntRSTY69LAQEX1AUzaSBHHFdKEpQ
hex:  c477f9f65c22cce20657faa5b2d1d8122336f851a508a1ed04e479c34985bf96</code></pre>
<figure class="wp-block-image"><img title="Checking the private key on the bitaddress website" src="./The very first serious vulnerability in Blockchain and how to get the public key Bitcoin ECDSA RSZ value from the RawTX file - «CRYPTO DEEP TECH»_files/a69992dcf93bacd0324c9a06722be9b5.png" alt="Checking the private key on the bitaddress website"><figcaption>Checking the private key on the bitaddress website</figcaption></figure>
<p><em><u>Private key found!</u></em></p>
<p><a href="https://www.blockchain.com/btc/address/1BFhrfTTZP3Nw4BNy4eX4KFLsn9ZeijcMm" target="_blank" rel="noreferrer noopener">https://www.blockchain.com/btc/address/1BFhrfTTZP3Nw4BNy4eX4KFLsn9ZeijcMm</a></p>
<figure class="wp-block-image"><img title="
0.1638109 BTC" src="./The very first serious vulnerability in Blockchain and how to get the public key Bitcoin ECDSA RSZ value from the RawTX file - «CRYPTO DEEP TECH»_files/049126899d0dc2b84a30b18fc496c258.png" alt="
0.1638109 BTC"><figcaption>0.1638109 BTC</figcaption></figure>
<blockquote class="wp-block-quote"><p>Of course, the developers of Bitcoin fixed this vulnerability by introducing deterministic functions.</p>
<p>This feature&nbsp;&nbsp;<code>RFC 6979</code>&nbsp;introduces an element of randomness into the Bitcoin signature, which enhances the cryptographic strength of the transaction.&nbsp;<code>ECDSA</code></p></blockquote>
<p>Document&nbsp;&nbsp;<code>[PDF]</code>:&nbsp;<a href="https://datatracker.ietf.org/doc/html/rfc6979" target="_blank" rel="noreferrer noopener"><em>RFC 6979: Deterministic Usage of the Digital Signature Algorithm (DSA) and Elliptic Curve Digital Signature Algorithm (ECDSA)</em></a><a href="https://eprint.iacr.org/2014/848.pdf">&nbsp;</a></p>
<hr class="wp-block-separator has-alpha-channel-opacity">
<h2>As we know in practice, there are completely different vulnerable transactions in the Bitcoin blockchain.</h2>
<blockquote class="wp-block-quote"><p>We previously posted&nbsp;&nbsp;<code>статью</code>:&nbsp;&nbsp;<a href="https://cryptodeep.ru/lattice-attack/" target="_blank" rel="noreferrer noopener"><em>“One weak transaction in ECDSA on the Bitcoin blockchain and with the help of Lattice Attack we received a Private Key to BTC coins”</em></a></p></blockquote>
<div class="wp-block-image">
<figure class="aligncenter is-resized"><a href="https://cryptodeep.ru/lattice-attack/" target="_blank" rel="noreferrer noopener"><img loading="lazy" title="https://habr.com/ru/post/671932/" src="./The very first serious vulnerability in Blockchain and how to get the public key Bitcoin ECDSA RSZ value from the RawTX file - «CRYPTO DEEP TECH»_files/6b872307d4a4dc3a74386c2b83d133a2.png" alt="https://habr.com/ru/post/671932/" width="562" height="77"></a></figure>
</div>
<p>Now let’s get the public key&nbsp;&nbsp;<code>Bitcoin</code>&nbsp;<code>ECDSA</code>&nbsp;and value&nbsp; ourselves&nbsp;<code>R, S, Z</code>from the&nbsp;&nbsp;<a href="https://github.com/demining/CryptoDeepTools/blob/main/02BreakECDSAcryptography/RawTX.json" target="_blank" rel="noreferrer noopener">«RawTX.json»</a>&nbsp;file &nbsp;(which we got in&nbsp;&nbsp;<a href="https://github.com/demining/CryptoDeepTools/tree/main/01BlockchainGoogleDrive" target="_blank" rel="noreferrer noopener"><strong>01BlockchainGoogleDrive</strong></a>&nbsp;&nbsp;)</p>
<ul>
<li>To do this, use the Terminal for Google Colab&nbsp;&nbsp;<a href="https://github.com/demining/TerminalGoogleColab" target="_blank" rel="noreferrer noopener">[&nbsp;<strong>TerminalGoogleColab]</strong></a></li>
<li>Earlier I recorded a video:&nbsp;&nbsp;<a href="https://www.youtube.com/watch?v=S2D7PI6dK08" target="_blank" rel="noreferrer noopener"><strong>«TERMINAL in Google Colab creating all the conveniences for working in GITHUB»</strong></a></li>
<li>Let’s go through the&nbsp;&nbsp;<a href="https://github.com/demining/CryptoDeepTools/blob/main/02BreakECDSAcryptography" target="_blank" rel="noreferrer noopener"><strong>«CryptoDeepTools»</strong></a>&nbsp;repository &nbsp;for a detailed cryptanalysis and take a closer look at how the&nbsp;&nbsp;<em>Bash script</em>&nbsp;works :&nbsp;&nbsp;<a href="https://github.com/demining/CryptoDeepTools/blob/main/02BreakECDSAcryptography/getsign.sh" target="_blank" rel="noreferrer noopener">getsign.sh</a></li>
</ul>
<figure class="wp-block-image"><img title="Teams" src="./The very first serious vulnerability in Blockchain and how to get the public key Bitcoin ECDSA RSZ value from the RawTX file - «CRYPTO DEEP TECH»_files/7d1bdc190149e6da8505d21155f14bbd.png" alt="Teams"><figcaption>Teams</figcaption></figure>
<figure class="wp-block-image"><img title="Files" src="./The very first serious vulnerability in Blockchain and how to get the public key Bitcoin ECDSA RSZ value from the RawTX file - «CRYPTO DEEP TECH»_files/9bfc350c715272db79f6bd5c6039e924.png" alt="Files"><figcaption>Files</figcaption></figure>
<figure class="wp-block-image"><img title="Our Bash script code: getsign.sh" src="./The very first serious vulnerability in Blockchain and how to get the public key Bitcoin ECDSA RSZ value from the RawTX file - «CRYPTO DEEP TECH»_files/5f0cf56f00c897f69fab24e8a3073588.png" alt="Our Bash script code: getsign.sh"><figcaption>Our Bash script code: getsign.sh</figcaption></figure>
<blockquote class="wp-block-quote"><p>And so let’s take a look at the whole work&nbsp; of the&nbsp;<em>Bash script</em>&nbsp;in detail :&nbsp;&nbsp;<a href="https://github.com/demining/CryptoDeepTools/blob/main/02BreakECDSAcryptography/getsign.sh" target="_blank" rel="noreferrer noopener">getsign.sh</a></p></blockquote>
<pre class="wp-block-code"><code>cat RawTX.json &gt; index.json</code></pre>
<p>Making a copy of a file&nbsp;&nbsp;<code>RawTX.json</code>&nbsp;into a new file&nbsp;<code>index.json</code></p>
<pre class="wp-block-code"><code><strong>for</strong> run <strong>in</strong> {1..4}; <strong>do</strong></code></pre>
<p>We open&nbsp; it because&nbsp;&nbsp;we take&nbsp;&nbsp;<em>4 lines</em><code>ЦИКЛ</code>&nbsp;&nbsp;in the file&nbsp;<code>index.json</code>&nbsp;<code>{1..4}</code></p>
<pre class="wp-block-code"><code>export LINE=1 ; sed -n "${LINE}p" index.json &gt; index2.json</code></pre>
<p>The utility&nbsp;&nbsp;<code>export</code>&nbsp;takes&nbsp;&nbsp;<em>line #1</em>&nbsp;&nbsp;and saves it in a new file&nbsp;<code>index2.json</code></p>
<pre class="wp-block-code"><code>sed -i '1d' index.json</code></pre>
<p>The utility&nbsp;&nbsp;<code>sed</code>&nbsp;removes&nbsp;&nbsp;<em>line #1&nbsp;</em>&nbsp;from the file&nbsp;<code>index.json</code></p>
<figure class="wp-block-image"><img title="The echo utility creates a Python script for us fileopen.py" src="./The very first serious vulnerability in Blockchain and how to get the public key Bitcoin ECDSA RSZ value from the RawTX file - «CRYPTO DEEP TECH»_files/972d1b5554e84191da57b16415061198.png" alt="The echo utility creates a Python script for us fileopen.py"><figcaption>The echo utility creates a Python script for us fileopen.py</figcaption></figure>
<pre class="wp-block-code"><code>python3 fileopen.py</code></pre>
<p>We run&nbsp;&nbsp;<em>the Python script</em>&nbsp;<code>fileopen.py</code>&nbsp;&nbsp;and successfully creates a new&nbsp;&nbsp;<em>Bash script</em>&nbsp;:&nbsp;<code>signscript.sh</code></p>
<pre class="wp-block-code"><code>chmod +x signscript.sh
./signscript.sh</code></pre>
<p>We get the rights to the&nbsp;&nbsp;<em>Bash script</em>&nbsp;: signscript.sh</p>
<blockquote class="wp-block-quote"><p>As a result,&nbsp; the&nbsp;<a href="https://github.com/demining/CryptoDeepTools/blob/main/02BreakECDSAcryptography/breakECDSA.py" target="_blank" rel="noreferrer noopener">breakECDSA.py&nbsp;</a><em>Python script</em>&nbsp;&nbsp;is launched, &nbsp;which eventually extracts the&nbsp;&nbsp;value&nbsp;&nbsp;&nbsp;and public key of Bitcoin from<code>RawTX</code><code>R, S, Z</code></p>
<p>All this is saved to a file:&nbsp;<code>"signatures.json"</code></p></blockquote>
<figure class="wp-block-image"><img title="file: &quot;signatures.json&quot; Bitcoin public key and R, S, Z value" src="./The very first serious vulnerability in Blockchain and how to get the public key Bitcoin ECDSA RSZ value from the RawTX file - «CRYPTO DEEP TECH»_files/2e19dfc270a6f0bc6bd2ea9123215442.png" alt="file: &quot;signatures.json&quot; Bitcoin public key and R, S, Z value"><figcaption>file: «signatures.json» Bitcoin public key and R, S, Z value</figcaption></figure>
<pre class="wp-block-code"><code><strong>rm</strong> <strong>signscript</strong>.sh
<strong>rm</strong> <strong>fileopen</strong>.py</code></pre>
<p>The utility&nbsp;&nbsp;<code>rm</code>&nbsp;removes&nbsp;&nbsp;<em>the Python script</em>&nbsp;<code>fileopen.py</code>&nbsp;&nbsp;and successfully creates a new&nbsp;&nbsp;<em>Bash script</em>&nbsp;:&nbsp;<code>signscript.sh</code></p>
<pre class="wp-block-code"><code><strong>done</strong></code></pre>
<p>As a result, everything will end after&nbsp;<em>&nbsp;4 cycles</em></p>
<pre class="wp-block-code"><code>rm <strong>index</strong>.json</code></pre>
<p>The cycle closes and the utility&nbsp;&nbsp;<code>rm</code>&nbsp;deletes&nbsp;<code>index.json</code></p>
<p><em>Bash script</em>&nbsp;:&nbsp;&nbsp;<a href="https://github.com/demining/CryptoDeepTools/blob/main/02BreakECDSAcryptography/getsign.sh" target="_blank" rel="noreferrer noopener">getsign.sh</a>&nbsp;<code>Завершает работу!</code></p>
<h2>Now we have learned:</h2>
<ul>
<li>Get public key&nbsp;&nbsp;<code>Bitcoin&nbsp;</code>from<code>&nbsp;ECDSA</code></li>
<li>Get value&nbsp;&nbsp;<code>R, S, Z</code>&nbsp;from<code>&nbsp;ECDSA</code></li>
<li>Apply it for&nbsp;<code>криптоанализа</code></li>
</ul>
<p class="has-vivid-cyan-blue-color has-text-color"><strong>Source code:&nbsp;&nbsp;<a href="https://github.com/demining/CryptoDeepTools/blob/main/02BreakECDSAcryptography" target="_blank" rel="noreferrer noopener">https://github.com/demining/CryptoDeepTools/blob/main/02BreakECDSAcryptography</a></strong></p>
<p class="has-vivid-cyan-blue-color has-text-color"><strong>Telegram:&nbsp;&nbsp;<a href="https://t.me/cryptodeeptech" target="_blank" rel="noreferrer noopener">https://t.me/cryptodeeptech</a></strong></p>
<p class="has-vivid-cyan-blue-color has-text-color"><strong>Video:&nbsp;&nbsp;<a href="https://youtu.be/BYd-cuFRZmM" target="_blank" rel="noreferrer noopener">https://youtu.be/BYd-cuFRZmM</a></strong></p>
<p><strong><a href="https://cryptodeeptech.ru/break-ecdsa-cryptography">Source: https://cryptodeeptech.ru/break-ecdsa-cryptography</a></strong></p>
<p><iframe title="Youtube video player" src="./The very first serious vulnerability in Blockchain and how to get the public key Bitcoin ECDSA RSZ value from the RawTX file - «CRYPTO DEEP TECH»_files/BYd-cuFRZmM(1).html" width="560" height="315" frameborder="0" allowfullscreen="allowfullscreen" data-mce-fragment="1"></iframe></p>
</div>
<footer class="entry-footer">
<div class="cat-links"></div>
</footer>
	</div><!-- .entry-content -->

	<footer class="entry-footer">
		<div class="cat-links"><i class="fa fa-folder-open" aria-hidden="true"></i> <a href="https://cryptodeeptech.ru/category/%d0%b1%d0%b5%d0%b7-%d1%80%d1%83%d0%b1%d1%80%d0%b8%d0%ba%d0%b8/" rel="category tag">Без рубрики</a></div>	</footer><!-- .entry-footer -->
</article><!-- #post-112 -->

	<nav class="navigation post-navigation" aria-label="Записи">
		<h2 class="screen-reader-text">Навигация по записям</h2>
		<div class="nav-links"><div class="nav-previous"><a href="https://cryptodeeptech.ru/blockchain-google-drive/" rel="prev">How to Parse Blockchain Transactions to a Google Drive Folder</a></div><div class="nav-next"><a href="https://cryptodeeptech.ru/check-bitcoin-address-balance/" rel="next">How to Convert Bitcoin-PUBKEY HEX Public Keys to Base58 Bitcoin Address and Check Balance for BTC Coins</a></div></div>
	</nav>		<div id="itng_related_posts_wrapper">
			<h3 id="itng_related_posts_title">Related Posts</h3>
			<div class="itng-related-posts row">
				<article id="post-127" class="itng-blog col-md-6 col-lg-4 post-127 post type-post status-publish format-standard hentry category-1">
		<div class="itng-card-wrapper">
			<div class="itng-thumb">
							</div>
			
			<div class="itng-card-content">
				<div class="entry-meta">
					<a href="https://cryptodeeptech.ru/check-bitcoin-address-balance/"></a>
					<span class="byline"> <span class="author vcard"><a class="url fn n" href="https://cryptodeeptech.ru/author/cryptodeeptech/">Crypto Deep Tech</a></span></span>				</div><!-- .entry-meta -->
				
				<header class="entry-header">
					<h2 class="entry-title"><a href="https://cryptodeeptech.ru/check-bitcoin-address-balance/">How to Convert Bitcoin-PUBKEY HEX Public Keys to Base58 Bitcoin Address and Check Balance for BTC Coins</a></h2>				</header><!-- .entry-header -->
				
				<div class="itng_excerpt">
					In this article, we will learn how to check the balance of Bitcoin coins in a large amount of data using the bitcoin-checker.py Python script for&nbsp;&nbsp;this&nbsp;. The result of checking the Python script bitcoin-checker.py We will also learn how to convert the public key of Bitcoin&nbsp;&nbsp;PUBKEY (HEX)&nbsp;to Bitcoin Address&nbsp;&nbsp;(Base58)&nbsp;All this big work is done&nbsp;&nbsp;by the Python script&nbsp;&nbsp;pubtoaddr.py…				</div>
				
				<div class="blog-footer">
					<div class="itng_cats">
						<a href="https://cryptodeeptech.ru/category/%d0%b1%d0%b5%d0%b7-%d1%80%d1%83%d0%b1%d1%80%d0%b8%d0%ba%d0%b8/" rel="category tag">Без рубрики</a>					</div>
					<div class="blog-comments">
						0					</div>
				</div>
			</div>
		</div>
</article><!-- #post-127 --><article id="post-372" class="itng-blog col-md-6 col-lg-4 post-372 post type-post status-publish format-standard hentry category-1">
		<div class="itng-card-wrapper">
			<div class="itng-thumb">
							</div>
			
			<div class="itng-card-content">
				<div class="entry-meta">
					<a href="https://cryptodeeptech.ru/shortest-ecdsa-signature/"></a>
					<span class="byline"> <span class="author vcard"><a class="url fn n" href="https://cryptodeeptech.ru/author/cryptodeeptech/">Crypto Deep Tech</a></span></span>				</div><!-- .entry-meta -->
				
				<header class="entry-header">
					<h2 class="entry-title"><a href="https://cryptodeeptech.ru/shortest-ecdsa-signature/">Bitcoin Wallet Recovery via ECDSA Short Signatures</a></h2>				</header><!-- .entry-header -->
				
				<div class="itng_excerpt">
					We all know that the disclosure of the secret key in the ECDSA signature can lead to the complete recovery of the Bitcoin Wallet.&nbsp;In our earlier articles, we looked at&nbsp;weaknesses and vulnerabilities&nbsp;in blockchain transactions, but there are also ECDSA short signatures that also lead to the full recovery of a Bitcoin Wallet. Why are these ECDSA signatures…				</div>
				
				<div class="blog-footer">
					<div class="itng_cats">
						<a href="https://cryptodeeptech.ru/category/%d0%b1%d0%b5%d0%b7-%d1%80%d1%83%d0%b1%d1%80%d0%b8%d0%ba%d0%b8/" rel="category tag">Без рубрики</a>					</div>
					<div class="blog-comments">
						0					</div>
				</div>
			</div>
		</div>
</article><!-- #post-372 --><article id="post-294" class="itng-blog col-md-6 col-lg-4 post-294 post type-post status-publish format-standard hentry category-1">
		<div class="itng-card-wrapper">
			<div class="itng-thumb">
							</div>
			
			<div class="itng-card-content">
				<div class="entry-meta">
					<a href="https://cryptodeeptech.ru/vulnerable-openssl/"></a>
					<span class="byline"> <span class="author vcard"><a class="url fn n" href="https://cryptodeeptech.ru/author/cryptodeeptech/">Crypto Deep Tech</a></span></span>				</div><!-- .entry-meta -->
				
				<header class="entry-header">
					<h2 class="entry-title"><a href="https://cryptodeeptech.ru/vulnerable-openssl/">Search for BTC coins on earlier versions of Bitcoin Core with critical vulnerability OpenSSL 0.9.8 CVE-2008-0166</a></h2>				</header><!-- .entry-header -->
				
				<div class="itng_excerpt">
					In this article, we will create a tool that will generate Bitcoin Addresses (P2PKH) using the CVE-2008-0166 vulnerability.&nbsp;This is a research project to find BTC coins on earlier versions of the Bitcoin Core software client. Random number generator&nbsp;that generates&nbsp;&nbsp;predictable numbers&nbsp;&nbsp;CVE-2008-0166 VAIM-OpenSSL 0.9.8/1.0.0 Detected The critical vulnerability version&nbsp;&nbsp;OpenSSL 0.9.8&nbsp;CVE-2008-0166 was&nbsp;&nbsp;populated with process ID only.&nbsp;Due to differences between endianness…				</div>
				
				<div class="blog-footer">
					<div class="itng_cats">
						<a href="https://cryptodeeptech.ru/category/%d0%b1%d0%b5%d0%b7-%d1%80%d1%83%d0%b1%d1%80%d0%b8%d0%ba%d0%b8/" rel="category tag">Без рубрики</a>					</div>
					<div class="blog-comments">
						0					</div>
				</div>
			</div>
		</div>
</article><!-- #post-294 -->			</div>
		</div>
			<div id="author_box" class="row no-gutters">
			<div class="author_avatar col-2">
							</div>
			<div class="author_info col-10">
				<h4 class="author_name title-font">
					Crypto Deep Tech				</h4>
				<div class="author_bio">
									</div>
			</div>
		</div>
	
<div id="comments" class="comments-area">

		<div id="respond" class="comment-respond">
		<h3 id="reply-title" class="comment-reply-title">Добавить комментарий</h3><form action="https://cryptodeeptech.ru/wp-comments-post.php" method="post" id="commentform" class="comment-form" novalidate=""><p class="comment-notes"><span id="email-notes">Ваш адрес email не будет опубликован.</span> <span class="required-field-message" aria-hidden="true">Обязательные поля помечены <span class="required" aria-hidden="true">*</span></span></p><p class="comment-form-comment"><label for="comment">Комментарий <span class="required" aria-hidden="true">*</span></label> <textarea id="comment" name="comment" cols="45" rows="8" maxlength="65525" required=""></textarea></p><p class="comment-form-author"><label for="author">Имя</label> <input id="author" name="author" type="text" value="" size="30" maxlength="245"></p>
<p class="comment-form-email"><label for="email">Email</label> <input id="email" name="email" type="email" value="" size="30" maxlength="100" aria-describedby="email-notes"></p>
<p class="comment-form-url"><label for="url">Сайт</label> <input id="url" name="url" type="url" value="" size="30" maxlength="200"></p>
<p class="form-submit"><input name="submit" type="submit" id="submit" class="submit" value="Отправить комментарий"> <input type="hidden" name="comment_post_ID" value="112" id="comment_post_ID">
<input type="hidden" name="comment_parent" id="comment_parent" value="0">
</p><p style="display: none !important;"><label>Δ<textarea name="ak_hp_textarea" cols="45" rows="8" maxlength="100"></textarea></label><input type="hidden" id="ak_js_1" name="ak_js" value="1661458530896"><script>document.getElementById( "ak_js_1" ).setAttribute( "value", ( new Date() ).getTime() );</script></p></form>	</div><!-- #respond -->
	
</div><!-- #comments -->

	</main><!-- #main -->

<!--WCLEARFY_PAGE_TYPE_post--><!--WCLEARFY_FOOTER_START--></div><!-- #content-wrapper -->


 <div id="footer-sidebar" class="widget-area">
    <div class="container">
        <div class="row">
                    </div>
    </div>
</div>
	<footer id="colophon" class="site-footer">
		<div class="container">
			<div class="site-info">
				Donation Address: <a href="https://www.blockchain.com/btc/address/1Lw2kh9WzCActXSGHxyypGLkqQZfxDpw8v" target="_blank">♥  BTC: 1Lw2kh9WzCActXSGHxyypGLkqQZfxDpw8v</a>				<span class="sep"> | </span>
					Copyright © 2022 «CRYPTO DEEP TECH». 			</div><!-- .site-info -->
		</div>
	</footer><!-- #colophon -->
</div><!-- #page -->

<nav id="menu" class="panel" role="navigation" style="position: fixed; top: 0px; bottom: 0px; height: 100%; left: -15.625em; width: 15.625em;">
	<div class="menu-overlay"></div>
	<div id="panel-top-bar">
		<button class="go-to-bottom"></button>
		<button id="close-menu" class="menu-link"><i class="fa fa-chevron-left" aria-hidden="true"></i></button>
	</div>

	<ul id="menu-main" class="menu"><li class="page_item page-item-53"><a href="https://cryptodeeptech.ru/contacts/">CONTACTS</a></li>
<li class="page_item page-item-43"><a href="https://cryptodeeptech.ru/publication/">PUBLICATIONS</a></li>
<li class="page_item page-item-55"><a href="https://cryptodeeptech.ru/resources/">RESOURCES</a></li>
<li class="page_item page-item-49"><a href="https://cryptodeeptech.ru/study/">STUDY</a></li>
</ul>

	<button class="go-to-top"></button>
</nav>

<div id="sticky-navigation">
	<div class="nav-wrapper">
		 <div class="container">

			 <div class="row justify-content-end align-items-center justify-content-between no-gutters">


				<div class="main-navigation col-lg-9" role="navigation">
					<ul id="menu-desktop" class="menu"><li class="menu-item menu-item-type-custom menu-item-object-custom menu-item-home menu-item-229"><a href="https://cryptodeeptech.ru/">HOME</a></li>
<li class="menu-item menu-item-type-post_type menu-item-object-page menu-item-225"><a href="https://cryptodeeptech.ru/publication/">PUBLICATIONS</a></li>
<li class="menu-item menu-item-type-post_type menu-item-object-page menu-item-226"><a href="https://cryptodeeptech.ru/study/">STUDY</a></li>
<li class="menu-item menu-item-type-post_type menu-item-object-page menu-item-227"><a href="https://cryptodeeptech.ru/resources/">RESOURCES</a></li>
<li class="menu-item menu-item-type-post_type menu-item-object-page menu-item-228"><a href="https://cryptodeeptech.ru/contacts/">CONTACTS</a></li>
<li class="menu-item menu-item-type-post_type menu-item-object-post menu-item-240"><a href="https://cryptodeeptech.ru/lattice-attack/">BLOG</a></li>
</ul>				</div>

				<button href="#menu" class="menu-link mobile-nav-btn"><i class="fa fa-bars" aria-hidden="true"></i></button>

				<button type="button" id="go-to-field" tabindex="-1"></button>

				<button class="search-btn-sticky ml-auto col-auto"><i class="fa fa-search"></i></button>
				
<div class="itng-search-sticky">
	<form role="search" method="get" class="search-form" action="https://cryptodeeptech.ru/">
				<label>
					<span class="screen-reader-text">Найти:</span>
					<input type="search" class="search-field" placeholder="Поиск…" value="" name="s">
				</label>
				<input type="submit" class="search-submit" value="Поиск">
			</form>	<button type="button" id="go-to-btn" tabindex="-1"></button>
</div>

			</div>
		</div>
	</div>
</div>

<div id="itng-back-to-top" class="show"><i class="fa fa-chevron-up" aria-hidden="true"></i></div>

		<script type="text/javascript">
							jQuery("#post-112 .entry-meta .date").css("display","none");
					jQuery("#post-112 .entry-date").css("display","none");
					jQuery("#post-112 .posted-on").css("display","none");
							jQuery("#post-127 .entry-meta .date").css("display","none");
					jQuery("#post-127 .entry-date").css("display","none");
					jQuery("#post-127 .posted-on").css("display","none");
							jQuery("#post-372 .entry-meta .date").css("display","none");
					jQuery("#post-372 .entry-date").css("display","none");
					jQuery("#post-372 .posted-on").css("display","none");
							jQuery("#post-294 .entry-meta .date").css("display","none");
					jQuery("#post-294 .entry-date").css("display","none");
					jQuery("#post-294 .posted-on").css("display","none");
				</script>
	<script src="./The very first serious vulnerability in Blockchain and how to get the public key Bitcoin ECDSA RSZ value from the RawTX file - «CRYPTO DEEP TECH»_files/wmac_single_2b1ae4cca3cc8d12c39be42768565308.js" id="big-slide-js"></script>
<script src="./The very first serious vulnerability in Blockchain and how to get the public key Bitcoin ECDSA RSZ value from the RawTX file - «CRYPTO DEEP TECH»_files/wmac_single_ccdf893e7d8b26933af0c336bcc3943e.js" id="owl-js-js"></script>
<script src="./The very first serious vulnerability in Blockchain and how to get the public key Bitcoin ECDSA RSZ value from the RawTX file - «CRYPTO DEEP TECH»_files/jquery.magnific-popup.min.js" id="mag-lightbox-js-js"></script>
<script id="itng-custom-js-js-extra">
var itng = {"toTopEnable":"1","stickyNav":""};
</script>
<script src="./The very first serious vulnerability in Blockchain and how to get the public key Bitcoin ECDSA RSZ value from the RawTX file - «CRYPTO DEEP TECH»_files/wmac_single_ea8874ba65dbd53bf5c7fb5c619ac579.js" id="itng-custom-js-js"></script>
<script src="./The very first serious vulnerability in Blockchain and how to get the public key Bitcoin ECDSA RSZ value from the RawTX file - «CRYPTO DEEP TECH»_files/wmac_single_6ec0e9b3201c83a442e24aba829a5f05.js" id="itng-navigation-js"></script>
<!-- Yandex.Metrika counter --> <script type="text/javascript"> (function(m,e,t,r,i,k,a){m[i]=m[i]||function(){(m[i].a=m[i].a||[]).push(arguments)}; m[i].l=1*new Date();k=e.createElement(t),a=e.getElementsByTagName(t)[0],k.async=1,k.src=r,a.parentNode.insertBefore(k,a)}) (window, document, "script", "https://mc.yandex.ru/metrika/tag.js", "ym"); ym(89424273, "init", {  id:89424273, clickmap:true, trackLinks:true, webvisor:true, accurateTrackBounce:true }); </script> <noscript><div><img src="https://mc.yandex.ru/watch/89424273" style="position:absolute; left:-9999px;" alt="" /></div></noscript> <!-- /Yandex.Metrika counter -->
<!-- Yandex.Metrika counter -->
<script type="text/javascript">
   (function(m,e,t,r,i,k,a){m[i]=m[i]||function(){(m[i].a=m[i].a||[]).push(arguments)};
   var z = null;m[i].l=1*new Date();
   for (var j = 0; j < document.scripts.length; j++) {if (document.scripts[j].src === r) { return; }}
   k=e.createElement(t),a=e.getElementsByTagName(t)[0],k.async=1,k.src=r,a.parentNode.insertBefore(k,a)})
   (window, document, "script", "https://mc.yandex.ru/metrika/tag.js", "ym");

   ym(89995532, "init", {
        clickmap:true,
        trackLinks:true,
        accurateTrackBounce:true,
        webvisor:true
   });
</script>
<noscript><div><img src="https://mc.yandex.ru/watch/89995532" style="position:absolute; left:-9999px;" alt="" /></div></noscript>
<!-- /Yandex.Metrika counter -->


</body></html>