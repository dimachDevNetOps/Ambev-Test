
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="utf-8">
<meta name="viewport" content="width=device-width, initial-scale=1, shrink-to-fit=no">

<title>Como Instalar Linux, Nginx, MySQL, PHP (pilha LEMP) no Ubuntu 20.04 | DigitalOcean</title>

<meta name="description" content="A pilha de software LEMP é um grupo de softwares que pode ser usado para exibir páginas e aplicativos Web dinâmicos escritos em PHP. Este é um acrônimo que descreve um sistema operacional Linux, com um servidor Web Nginx (se pronuncia “Engine-X). Os d">

<link rel="apple-touch-icon" sizes="180x180" href="/assets/community/apple-icon-180x180-4b5ac7f80f7cb483dde5afeb99c279301c50ec3670129c73ce568f1b465354be.png" />
<link rel="apple-touch-icon" sizes="152x152" href="/assets/community/apple-icon-152x152-ff64fd3242c24284fefdaec8d6d85c68f98744142d58b950f7ec67cbf03251d7.png" />
<link rel="apple-touch-icon" sizes="144x144" href="/assets/community/apple-icon-144x144-3018401d3d675917b06ded0482cdf53a7c3558b4dc7b6b8de21a485a8da27dfe.png" />
<link rel="apple-touch-icon" sizes="120x120" href="/assets/community/apple-icon-120x120-052cdf68a3af8b01c3fd0d46ed35f8f089c10c690109d20e7b186f0159391863.png" />
<link rel="apple-touch-icon" sizes="114x114" href="/assets/community/apple-icon-114x114-8d862033fc61d86a60b4bdbbbab284da399da714089995ce7efc249f36409517.png" />
<link rel="apple-touch-icon" sizes="76x76" href="/assets/community/apple-icon-76x76-d7c1877f2224ca127b591f65d16635fa7472e7b2cd0e1fe7e7dc8b74d03dd874.png" />
<link rel="apple-touch-icon" sizes="72x72" href="/assets/community/apple-icon-72x72-2d888cc13ddb01fb0d786a0c8567c0a2909eaeb86901da715099b6b88a36b46a.png" />
<link rel="apple-touch-icon" sizes="60x60" href="/assets/community/apple-icon-60x60-01be5b392df60249f168b8b2eed5c928c63aa43ac398c7180cd219c5acdd1e70.png" />
<link rel="apple-touch-icon" sizes="57x57" href="/assets/community/apple-icon-57x57-d060d0fd30794efd579d9edc283917e0a65adfd366e151d9a5cfd8fd7d07cb43.png" />

<link rel="icon" type="image/png" sizes="192x192"  href="/assets/community/android-icon-192x192-4d13e6664f412f6904a78be76d626004bcbbd59671f6c755919628134003c2a8.png" />
<link rel="icon" type="image/png" sizes="32x32" href="/assets/community/favicon-32x32-e377577c425642ab495296dfec040ec903e36ffc4cd7a0a4281e84597891a774.png" />
<link rel="icon" type="image/png" sizes="96x96" href="/assets/community/favicon-96x96-967f34b6716bb3cffebefe1fa53206d38d60c72635e826ec5d172c58fb4ab5a9.png" />
<link rel="icon" type="image/png" sizes="16x16" href="/assets/community/favicon-16x16-ce9c1eb6d969d5b2ec276ae4b715756aa0e63106f33dc53a836687fdfee49ecd.png" />

<meta name="msapplication-TileImage" content="/assets/community/ms-icon-144x144-3018401d3d675917b06ded0482cdf53a7c3558b4dc7b6b8de21a485a8da27dfe.png" />
<meta name="msapplication-TileColor" content="#0069ff" />
<meta name="theme-color" content="#0069ff" />

<meta property="og:title" content="Como Instalar Linux, Nginx, MySQL, PHP (pilha LEMP) no Ubuntu 20.04 | DigitalOcean">
<meta property="og:description" content="A pilha de software LEMP é um grupo de softwares que pode ser usado para exibir páginas e aplicativos Web dinâmicos escritos em PHP. Este é um acrônimo que descreve um sistema operacional Linux, com um servidor Web Nginx (se pronuncia “Engine-X). Os d">
<meta property="og:site_name" content="DigitalOcean">
<meta property="og:type" content="article">
<meta property="og:image" content="https://www.digitalocean.com/assets/community/illustrations/DigitalOcean_Community-e00e73a18df20667c3117725e727f3ade330204dff619ad8153050ded7341627.jpg">
<meta property="og:image:url" content="https://www.digitalocean.com/assets/community/illustrations/DigitalOcean_Community-e00e73a18df20667c3117725e727f3ade330204dff619ad8153050ded7341627.jpg">
<meta property="og:image:alt" content="Como Instalar Linux, Nginx, MySQL, PHP (pilha LEMP) no Ubuntu 20.04 | DigitalOcean">
<meta property="og:url" content="https://www.digitalocean.com/community/tutorials/how-to-install-linux-nginx-mysql-php-lemp-stack-on-ubuntu-20-04-pt">

<meta name="twitter:site" content="@digitalocean">
<meta name="twitter:title" content="Como Instalar Linux, Nginx, MySQL, PHP (pilha LEMP) no Ubuntu 20.04 | DigitalOcean">
<meta name="twitter:description" content="A pilha de software LEMP é um grupo de softwares que pode ser usado para exibir páginas e aplicativos Web dinâmicos escritos em PHP. Este é um acrônimo que descreve um sistema operacional Linux, com um servidor Web Nginx (se pronuncia “Engine-X). Os d">
<meta name="twitter:creator" content="DigitalOcean">
<meta name="twitter:card" content="summary_large_image" />
<meta name="twitter:url" content="https://www.digitalocean.com/community/tutorials/how-to-install-linux-nginx-mysql-php-lemp-stack-on-ubuntu-20-04-pt"/>
<meta name="twitter:image" content="https://www.digitalocean.com/assets/community/illustrations/DigitalOcean_Community-e00e73a18df20667c3117725e727f3ade330204dff619ad8153050ded7341627.jpg">
<meta name="twitter:image:alt" content="Como Instalar Linux, Nginx, MySQL, PHP (pilha LEMP) no Ubuntu 20.04 | DigitalOcean">

  <link rel='canonical' href='https://www.digitalocean.com/community/tutorials/how-to-install-linux-nginx-mysql-php-lemp-stack-on-ubuntu-20-04-pt'>

  <link rel='amphtml' href='https://www.digitalocean.com/community/tutorials/how-to-install-linux-nginx-mysql-php-lemp-stack-on-ubuntu-20-04-pt.amp'>

        <link rel="alternate" hreflang="en" href="https://www.digitalocean.com/community/tutorials/how-to-install-linux-nginx-mysql-php-lemp-stack-on-ubuntu-20-04" />
      <link rel="alternate" hreflang="de" href="https://www.digitalocean.com/community/tutorials/how-to-install-linux-nginx-mysql-php-lemp-stack-on-ubuntu-20-04-de" />
      <link rel="alternate" hreflang="es" href="https://www.digitalocean.com/community/tutorials/how-to-install-linux-nginx-mysql-php-lemp-stack-on-ubuntu-20-04-es" />
      <link rel="alternate" hreflang="fr" href="https://www.digitalocean.com/community/tutorials/how-to-install-linux-nginx-mysql-php-lemp-stack-on-ubuntu-20-04-fr" />
      <link rel="alternate" hreflang="pt" href="https://www.digitalocean.com/community/tutorials/how-to-install-linux-nginx-mysql-php-lemp-stack-on-ubuntu-20-04-pt" />
      <link rel="alternate" hreflang="ru" href="https://www.digitalocean.com/community/tutorials/how-to-install-linux-nginx-mysql-php-lemp-stack-on-ubuntu-20-04-ru" />


    <link rel="preconnect" href="https://digitalocean.cdn.prismic.io">
    <link rel="preconnect" href="https://hello.myfonts.net">
    <link rel="stylesheet" media="all" href="/assets/community/application-3f780fb1eae71e41f4e7a172292599b6e60d609e19a1df04d00fbc71d6c06c79.css" />

    
    <meta name="csrf-param" content="authenticity_token" />
<meta name="csrf-token" content="hkLCULitvc7LDPUvcY7gXSL0ec9RNytn259uMJT/9DoQUFUHVQT0dWMRuIfDrWVhW0Q1F1/tIe90ej1ZOxwdRg==" />
    <script src="/assets/community/prerequisites-d767b66db7c8ba7d47a922cfce41c73d40601b3586be6f96107d5cd25cc752b8.js"></script>
    <script>
//<![CDATA[

  window.cookieDomain = '.digitalocean.com';

//]]>
</script><script defer src="https://assets.digitalocean.com/cookieConsent/cookieConsent.js"></script>
<script>
  (function () {
    document.addEventListener("DOMContentLoaded", function () {
      var css = document.getElementById("cookie-consent-css");

      if (css) { return; }

      css = document.createElement("link");
      css.id = "cookie-consent-css";
      css.rel = "stylesheet";
      css.href = "https://assets.digitalocean.com/cookieConsent/cookieConsent.css";
      document.head.insertBefore(css, document.head.childNodes[ document.head.childNodes.length - 1 ].nextSibling);
    }, false);
  })();
</script>

    <script type="text/javascript">
  if(window.analytics=window.analytics||[],window.analytics.included)window.console&&console.error&&console.error("analytics.js included twice");else{window.analytics.included=!0,window.analytics.methods=["identify","group","track","page","pageview","alias","ready","on","once","off","trackLink","trackForm","trackClick","trackSubmit"],window.analytics.factory=function(a){return function(){var n=Array.prototype.slice.call(arguments);return n.unshift(a),window.analytics.push(n),window.analytics}};for(var i=0;i<window.analytics.methods.length;i++){var key=window.analytics.methods[i];window.analytics[key]=window.analytics.factory(key)}window.analytics.load=function(a){var n=document.createElement("script");n.type="text/javascript",n.async=!0,n.src=("https:"===document.location.protocol?"https://":"http://")+"cdn.segment.com/analytics.js/v1/"+a+"/analytics.min.js";var t=document.getElementsByTagName("script")[0];t.parentNode.insertBefore(n,t)},window.analytics.SNIPPET_VERSION="2.0.9",window.analytics.load("puo3uv968t")}
  window.analytics.page();
</script>

<!-- Google Tag Manager -->
<script>
  (function(w,d,s,l,i){w[l]=w[l]||[];w[l].push({'gtm.start':
    new Date().getTime(),event:'gtm.js'});var f=d.getElementsByTagName(s)[0],
    j=d.createElement(s),dl=l!='dataLayer'?'&l='+l:'';j.async=true;j.src=
    '//www.googletagmanager.com/gtm.js?id='+i+dl;f.parentNode.insertBefore(j,f);
  })(window,document,'script','dataLayer','GTM-KHWBBT');
</script>
<!-- End Google Tag Manager -->

<script src="/assets/community/internalCookies-d87064530395e23ede521d41535044c0b89092bef82bbb545bd1c8f731908bad.js"></script>

      <script src="https://cdn.polyfill.io/v2/polyfill.min.js"></script>

    <link rel="alternate" type="application/rss+xml" title="RSS" href="/community/tutorials/feed">
    <script>
      window.comApp = {
        prefix: '/community',
        svgIconPath: 'https://www.digitalocean.com/assets/community/icon-sprite-a36f54b391966bc94e4a1e4467047db73568edf98e549f4bc919b952f5272560.svg',
        railsEnv: 'production',
        rootUrl: 'https://www.digitalocean.com/community',
        algolia_application_id: '6ZHEUVKJ88',
        algolia_api_key: 'c5470567eae7fa1177d43222e18ba086'
      };
    </script>
    
    <script>
  window.Prism = window.Prism || {};
  window.Prism.manual = true;
</script>
 
    <script src="/assets/community/application-1382513ba99b2ba17261dca993165bbd93098a7301600ca31c4c815005cae7e3.js"></script>
  </head>
  <body class="feature-filter-bar feature-upvotes tutorials-controller tutorial-single" data-env="production" data-prefix="/community" data-user-id="" data-facebook-app-id="694818843983011"   data-completed-tutorial-id="" data-tutorial-id="5625" data-js="tutorial"
  data-upvote="null"
  data-flagged=""
>
    

    <div class='outside_viewport'>
        <div id="contents-modal" class="modal fade mini-modal" style="display: none;">
    <div class="modal-dialog">
      <div class="modal-content">
        <div class="modal-header">
          <h1>Contents</h1>
          <button class="close-button icon icon-close-light" data-dismiss="modal" aria-label="close"></button>
        </div>
        <div class="modal-body">
          <div class="table-of-contents-modal"></div>
        </div>
      </div>
    </div>
  </div>
  <div id="share-modal" class="modal fade mini-modal" style="display: none;">
  <div class="modal-dialog">
    <div class="modal-content">
      <div class="modal-header">
        <h1>Share</h1>
        <button type="button" class="close-button icon icon-close-light" aria-label="close" data-dismiss="modal"></button>
      </div>
      <div class="modal-body">
        <div class="social-sharing social-sharing-container">
          <ul class="top ">
            <li class="shareBtn" id="sbTwitter">
              <a href="http://twitter.com/share?text=Como%20Instalar%20Linux%2C%20Nginx%2C%20MySQL%2C%20PHP%20%28pilha%20LEMP%29%20no%20Ubuntu%2020.04&amp;url=https://www.digitalocean.com/community/tutorials/how-to-install-linux-nginx-mysql-php-lemp-stack-on-ubuntu-20-04-pt?utm_content=how-to-install-linux-nginx-mysql-php-lemp-stack-on-ubuntu-20-04-pt&amp;utm_medium=community&amp;utm_source=twshare" class="share-icon share-popup" title="Share on Twitter" target="_blank">
                <span class="sIcon icon-bird"></span>
              </a>
              <a href="http://twitter.com/share?text=Como%20Instalar%20Linux%2C%20Nginx%2C%20MySQL%2C%20PHP%20%28pilha%20LEMP%29%20no%20Ubuntu%2020.04&amp;url=https://www.digitalocean.com/community/tutorials/how-to-install-linux-nginx-mysql-php-lemp-stack-on-ubuntu-20-04-pt?utm_content=how-to-install-linux-nginx-mysql-php-lemp-stack-on-ubuntu-20-04-pt&amp;utm_medium=community&amp;utm_source=twshare" class="share-link share-popup" title="Share on Twitter" target="_blank">
                Twitter
              </a>
            </li>
            <li class="shareBtn" id="sbFacebook">
              <a class="share-icon share-popup" href="https://www.facebook.com/sharer/sharer.php?u=https://www.digitalocean.com/community/tutorials/how-to-install-linux-nginx-mysql-php-lemp-stack-on-ubuntu-20-04-pt?utm_content=how-to-install-linux-nginx-mysql-php-lemp-stack-on-ubuntu-20-04-pt&amp;utm_medium=community&amp;utm_source=fbshare" title="Share on Facebook" target="_blank">
                <span class="sIcon icon-facebook-B"></span>
              </a>
              <a class="share-link share-popup" href="https://www.facebook.com/sharer/sharer.php?u=https://www.digitalocean.com/community/tutorials/how-to-install-linux-nginx-mysql-php-lemp-stack-on-ubuntu-20-04-pt?utm_content=how-to-install-linux-nginx-mysql-php-lemp-stack-on-ubuntu-20-04-pt&amp;utm_medium=community&amp;utm_source=fbshare" title="Share on Facebook" target="_blank">
                Facebook
              </a>
            </li>
            <li class="shareBtn" id="sbYC">
              <a href="https://news.ycombinator.com/submitlink?t=Como%20Instalar%20Linux%2C%20Nginx%2C%20MySQL%2C%20PHP%20%28pilha%20LEMP%29%20no%20Ubuntu%2020.04&amp;u=https://www.digitalocean.com/community/tutorials/how-to-install-linux-nginx-mysql-php-lemp-stack-on-ubuntu-20-04-pt?utm_content=how-to-install-linux-nginx-mysql-php-lemp-stack-on-ubuntu-20-04-pt&amp;utm_medium=community&amp;utm_source=hnshare" class="share-icon share-popup" target="_blank" title="Submit to Hacker News">
                <span class="sIcon icon-hacker-news"></span>
              </a>
              <a href="https://news.ycombinator.com/submitlink?t=Como%20Instalar%20Linux%2C%20Nginx%2C%20MySQL%2C%20PHP%20%28pilha%20LEMP%29%20no%20Ubuntu%2020.04&amp;u=https://www.digitalocean.com/community/tutorials/how-to-install-linux-nginx-mysql-php-lemp-stack-on-ubuntu-20-04-pt?utm_content=how-to-install-linux-nginx-mysql-php-lemp-stack-on-ubuntu-20-04-pt&amp;utm_medium=community&amp;utm_source=hnshare" class="share-link share-popup" target="_blank" title="Submit to Hacker News">
                Hacker News
              </a>
            </li>
          </ul>
        </div>
      </div>
    </div>
  </div>
</div>

  <div class="table-of-contents">
    <div data-js="tableOfContentsDesktop"></div>
  </div>
  <!-- algolia universal search -->
<input type="hidden" id="q-universal-search" value="" />



<div id="share-modal" class="modal fade mini-modal" style="display: none;">
  <div class="modal-dialog">
    <div class="modal-content">
      <div class="modal-header">
        <h1>Share</h1>
        <button type="button" class="close-button icon icon-close-light" aria-label="close" data-dismiss="modal"></button>
      </div>
      <div class="modal-body">
        <div class="social-sharing social-sharing-container">
          <ul class="bottom ">
            <li class="shareBtn" id="sbTwitter">
              <a href="http://twitter.com/share?text=Como%20Instalar%20Linux%2C%20Nginx%2C%20MySQL%2C%20PHP%20%28pilha%20LEMP%29%20no%20Ubuntu%2020.04&amp;url=https://www.digitalocean.com/community/tutorials/how-to-install-linux-nginx-mysql-php-lemp-stack-on-ubuntu-20-04-pt?utm_content=how-to-install-linux-nginx-mysql-php-lemp-stack-on-ubuntu-20-04-pt&amp;utm_medium=community&amp;utm_source=twshare" class="share-icon share-popup" title="Share on Twitter" target="_blank">
                <span class="sIcon icon-bird"></span>
              </a>
              <a href="http://twitter.com/share?text=Como%20Instalar%20Linux%2C%20Nginx%2C%20MySQL%2C%20PHP%20%28pilha%20LEMP%29%20no%20Ubuntu%2020.04&amp;url=https://www.digitalocean.com/community/tutorials/how-to-install-linux-nginx-mysql-php-lemp-stack-on-ubuntu-20-04-pt?utm_content=how-to-install-linux-nginx-mysql-php-lemp-stack-on-ubuntu-20-04-pt&amp;utm_medium=community&amp;utm_source=twshare" class="share-link share-popup" title="Share on Twitter" target="_blank">
                Twitter
              </a>
            </li>
            <li class="shareBtn" id="sbFacebook">
              <a class="share-icon share-popup" href="https://www.facebook.com/sharer/sharer.php?u=https://www.digitalocean.com/community/tutorials/how-to-install-linux-nginx-mysql-php-lemp-stack-on-ubuntu-20-04-pt?utm_content=how-to-install-linux-nginx-mysql-php-lemp-stack-on-ubuntu-20-04-pt&amp;utm_medium=community&amp;utm_source=fbshare" title="Share on Facebook" target="_blank">
                <span class="sIcon icon-facebook-B"></span>
              </a>
              <a class="share-link share-popup" href="https://www.facebook.com/sharer/sharer.php?u=https://www.digitalocean.com/community/tutorials/how-to-install-linux-nginx-mysql-php-lemp-stack-on-ubuntu-20-04-pt?utm_content=how-to-install-linux-nginx-mysql-php-lemp-stack-on-ubuntu-20-04-pt&amp;utm_medium=community&amp;utm_source=fbshare" title="Share on Facebook" target="_blank">
                Facebook
              </a>
            </li>
            <li class="shareBtn" id="sbYC">
              <a href="https://news.ycombinator.com/submitlink?t=Como%20Instalar%20Linux%2C%20Nginx%2C%20MySQL%2C%20PHP%20%28pilha%20LEMP%29%20no%20Ubuntu%2020.04&amp;u=https://www.digitalocean.com/community/tutorials/how-to-install-linux-nginx-mysql-php-lemp-stack-on-ubuntu-20-04-pt?utm_content=how-to-install-linux-nginx-mysql-php-lemp-stack-on-ubuntu-20-04-pt&amp;utm_medium=community&amp;utm_source=hnshare" class="share-icon share-popup" target="_blank" title="Submit to Hacker News">
                <span class="sIcon icon-hacker-news"></span>
              </a>
              <a href="https://news.ycombinator.com/submitlink?t=Como%20Instalar%20Linux%2C%20Nginx%2C%20MySQL%2C%20PHP%20%28pilha%20LEMP%29%20no%20Ubuntu%2020.04&amp;u=https://www.digitalocean.com/community/tutorials/how-to-install-linux-nginx-mysql-php-lemp-stack-on-ubuntu-20-04-pt?utm_content=how-to-install-linux-nginx-mysql-php-lemp-stack-on-ubuntu-20-04-pt&amp;utm_medium=community&amp;utm_source=hnshare" class="share-link share-popup" target="_blank" title="Submit to Hacker News">
                Hacker News
              </a>
            </li>
          </ul>
        </div>
      </div>
    </div>
  </div>
</div>

  <div id="newsletter-signup-dialog" class="newsletter-signups-dialog" data-newsletter-signup-dialog data-article-target=".content-body">
  <div class="form-message">
  <div class="pull-right">
    <a href="javascript:;" class="newsletter-signups-dialog-dismiss" data-newsletter-signup-dismiss>&times;</a>

  </div>
  <h4 class="newsletter-signups-dialog-title">
    Sign up for our newsletter.
  </h4>
  <p class="newsletter-signups-dialog-description">
    Get the latest tutorials on SysAdmin and open source topics.
  </p>
  <form class="newsletter-signup" id="new_newsletter_signup" data-newsletter-signup="true" action="/community/newsletter" accept-charset="UTF-8" data-remote="true" method="post"><input name="utf8" type="hidden" value="&#x2713;" />

  <input data-newsletter-signup-field="url" type="hidden" name="newsletter_signup[url]" id="newsletter_signup_url" />
  <input data-newsletter-signup-field="title" type="hidden" name="newsletter_signup[title]" id="newsletter_signup_title" />

  <div class="newsletter-signup-ajax-error" data-newsletter-signup-ajax-error></div>


  <div class="form-group">
    <input placeholder="Enter your email address" required="required" class="field" type="email" name="newsletter_signup[email]" id="newsletter_signup_email" />
  </div>

  <button data-disable-with="Sign Up" class="button blue-button">
    Sign Up
  </button>
</form>
</div>

<div class="thanks-message hidden" data-newsletter-signup-successful> 
  <div class='pull-right'> 
    <a href='javascript:;' class='newsletter-signups-dialog-dismiss icon icon-close-light' data-newsletter-signup-dismiss></a> 
  </div> 

  <span class='newsletter-signups-dialog-success'> 
    Thanks for signing up! 
  </span> 
</div>

</div>



      
    </div>

      
      
<div style="display: none;">
  <svg xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink">
    <symbol id="navbar-logo" xmlns="http://www.w3.org/2000/svg"> <title>DigitalOcean home</title> <g fill="currentColor" fill-rule="evenodd"> <path d="M14.4942 29v-5.5674c5.9572 0 10.5633-5.8478 8.2892-12.059-.8425-2.3006-2.693-4.1355-5.0126-4.9706-6.262-2.2534-12.1564 2.3135-12.1573 8.2207 0 0-.0006.0014-.0014.0014H0C0 5.2123 9.1687-2.1167 19.1138.9624c4.3459 1.3457 7.7993 4.7708 9.1561 9.081C31.3742 19.9068 23.985 29 14.4942 29"></path> <path d="M14.507 23.4468H8.9103v-5.549s.0005-.0011.0011-.0011h5.5949c.0006 0 .0009.0006.0009.0006v5.5495M8.9093 27.7118H4.6105l-.0012-.0012v-4.2638h4.3009v4.2638l-.0009.0012M4.6125 23.4468H1.0088c-.0015 0-.0026-.0012-.0026-.0012v-3.5724s.0011-.0025.0026-.0025h3.601c.0015 0 .0027.0011.0027.0011v3.575M43.2806 9.6357h1.649c1.8346 0 3.345.358 4.49 1.0647 1.2714.7603 1.9164 2.2069 1.9164 4.2991 0 2.1554-.6465 3.6671-1.9207 4.4942h-.0008c-1.0971.7196-2.5981 1.0846-4.462 1.0846h-1.6719V9.6357zm8.324-1.0736c-1.6598-1.142-3.7252-1.721-6.1387-1.721h-5.2537V23.373h5.2537c2.4074 0 4.4737-.6113 6.1407-1.8157.907-.6382 1.6197-1.5304 2.1185-2.651.4962-1.1144.7479-2.4288.7479-3.9067 0-1.4605-.2517-2.758-.7482-3.857-.4988-1.104-1.212-1.972-2.1202-2.5804zM58.1303 6.6376c-.5051 0-.9403.1777-1.2906.5254-.3546.335-.5346.7597-.5346 1.2618 0 .501.1791.9322.532 1.2825.3529.35.788.528 1.2932.528.5042 0 .9394-.178 1.2928-.528.3535-.3508.5324-.7821.5324-1.2825 0-.5015-.18-.926-.5324-1.2592-.3534-.3503-.7886-.528-1.2928-.528M56.6247 23.3729h2.9538V11.7294h-2.9538zM69.5321 19.5787c-.5162.5814-1.1793.8635-2.0264.8635-.8471 0-1.5064-.282-2.015-.863-.5065-.5777-.7637-1.3439-.7637-2.2773 0-.9479.2572-1.7238.764-2.3058.502-.576 1.1796-.8683 2.0147-.8683.8465 0 1.5096.284 2.0262.8695.5142.582.7751 1.3573.7751 2.3046 0 .9328-.2609 1.6988-.7749 2.2768zm.775-6.8767c-.8908-.7858-1.8858-1.2444-2.9614-1.2444-1.6305 0-2.9859.5598-4.0276 1.662-1.0555 1.0932-1.5907 2.5006-1.5907 4.1823 0 1.644.5269 3.0464 1.568 4.1709 1.0498 1.088 2.4123 1.6396 4.0503 1.6396 1.139 0 2.1182-.3144 2.9157-.9356v.268c0 .9662-.2608 1.7176-.7751 2.234-.5137.5154-1.226.7764-2.1173.7764-1.3637 0-2.2183-.5314-3.2589-1.9262l-2.0115 1.917.0542.0754c.4346.605 1.1 1.197 1.9785 1.7594.8787.5603 1.9832.8447 3.2832.8447 1.7536 0 3.1726-.5363 4.2172-1.5933 1.0506-1.0628 1.5835-2.486 1.5835-4.2286V11.7294H70.307v.9726zM75.7434 23.3729h2.9541V11.7294h-2.9541zM77.249 6.6376c-.5052 0-.94.1777-1.2906.5254-.3547.335-.5344.7597-.5344 1.2618 0 .501.1789.9322.532 1.2825.353.35.7878.528 1.293.528.5045 0 .9396-.178 1.2928-.528.3535-.3508.5323-.7821.5323-1.2825 0-.5015-.1797-.926-.5323-1.2592-.3532-.3503-.7883-.528-1.2929-.528M85.1724 8.5831h-2.9082v3.1463h-1.6888v2.6702h1.6888v4.8365c0 1.5134.3047 2.5964.9064 3.2181.6031.6247 1.6741.9414 3.1831.9414.48 0 .963-.0156 1.4354-.0463l.133-.0088v-2.6683l-1.013.0526c-.7033 0-1.1728-.1226-1.3961-.3637-.226-.245-.3406-.7636-.3406-1.5404v-4.421h2.7497v-2.6703h-2.7497V8.583M101.7735 23.3729h2.9544V6.8412h-2.9544zM134.5728 19.2094c-.5286.5874-1.0693 1.0966-1.4855 1.3613v.0005c-.4085.2599-.924.3918-1.532.3918-.8703 0-1.5703-.3144-2.1405-.9621-.567-.644-.8545-1.4716-.8545-2.4613s.2838-1.8162.8436-2.4556c.5625-.6434 1.2588-.9562 2.1285-.9562.9515 0 1.9548.5869 2.8145 1.5947l1.9525-1.8568c-1.273-1.6433-2.897-2.4081-4.8352-2.4081-1.622 0-3.028.5862-4.1788 1.7411-1.1446 1.147-1.7251 2.6074-1.7251 4.3409 0 1.7335.58 3.1977 1.7234 4.352 1.1447 1.1557 2.5514 1.7417 4.1805 1.7417 2.139 0 3.8651-.9158 5.029-2.5935l-1.9204-1.8304M140.2405 16.0973c.1422-.5567.401-1.0207.7714-1.381.4005-.3906.9214-.5885 1.5489-.5885.716 0 1.2702.2019 1.6474.6014.3495.3696.5467.8296.588 1.368h-4.5557zm6.4569-2.7414c-.4191-.5788-.9896-1.0448-1.6965-1.3854-.7047-.3404-1.526-.513-2.441-.513-1.6489 0-2.9982.6037-4.0113 1.7946-.9836 1.182-1.4818 2.651-1.4818 4.3665 0 1.7648.547 3.2253 1.6254 4.341 1.0727 1.1105 2.5083 1.6737 4.267 1.6737 1.992 0 3.627-.799 4.8587-2.3752l.0666-.0847-1.9273-1.837c-.1789.2139-.4317.4561-.6628.6722-.2918.273-.5659.4842-.8588.6289-.4415.218-.9369.3255-1.4907.3255-.8187 0-1.4964-.2388-2.0147-.71-.4847-.4403-.768-1.0345-.843-1.7683h7.8265l.0264-1.0693c0-.7569-.1038-1.4862-.3088-2.1677a6.312 6.312 0 0 0-.934-1.8918zM152.797 18.9234c.3352-.2318.8085-.3483 1.4073-.3483.7112 0 1.4654.1413 2.2426.421v1.1421c-.6421.592-1.4996.8922-2.5499.8922-.5114 0-.909-.1126-1.1822-.3355-.2683-.218-.3985-.4955-.3985-.847 0-.3994.1571-.7022.4808-.9245zm5.2452-6.3229h-.0003c-.8952-.758-2.1328-1.143-3.678-1.143-.9829 0-1.902.2144-2.7336.6324-.7691.387-1.5245 1.0275-2.0043 1.8662l.0298.0358 1.8917 1.796c.7791-1.2322 1.6454-1.66 2.7941-1.66.6172 0 1.1298.1643 1.5234.4881.3916.3216.5819.7304.5819 1.249v.5652c-.7324-.221-1.4629-.333-2.1738-.333-1.47 0-2.6663.3432-3.555 1.0193-.9.6852-1.3562 1.665-1.3562 2.9125 0 1.094.3847 1.9829 1.1461 2.6433.7677.6372 1.7275.961 2.8524.961 1.1246 0 2.177-.4495 3.132-1.2191v.9587h2.9089v-7.4852c0-1.4173-.4572-2.523-1.3591-3.2872zM170.7656 12.8285c-.8227-.9092-1.9791-1.371-3.4371-1.371-1.172 0-2.1236.3338-2.8357.9926v-.7207h-2.897v11.6435h2.954v-6.4215c0-.8823.2119-1.5828.6293-2.0826.4162-.4987.989-.741 1.75-.741.6691 0 1.1765.2167 1.5506.662.3759.4474.5662 1.0638.5662 1.8335v6.7496H172v-6.7496c0-1.6127-.415-2.889-1.2344-3.7948M92.8158 18.9234c.3351-.2318.8087-.3483 1.4075-.3483.7112 0 1.4652.1413 2.2426.421v1.1421c-.6421.592-1.4998.8922-2.5502.8922-.5114 0-.9087-.1126-1.1819-.3355-.2683-.218-.3988-.4955-.3988-.847 0-.3994.1574-.7022.4808-.9245zm5.2451-6.3229h-.0003c-.8952-.758-2.1328-1.143-3.6776-1.143-.983 0-1.902.2144-2.7337.6324-.7694.387-1.5247 1.0275-2.0043 1.8662l.0295.0358 1.8917 1.796c.7792-1.2322 1.6458-1.66 2.7941-1.66.6172 0 1.1298.1643 1.5234.4881.3916.3216.5822.7304.5822 1.249v.5652c-.7327-.221-1.4631-.333-2.174-.333-1.47 0-2.6664.3432-3.555 1.0193-.8999.6852-1.3562 1.665-1.3562 2.9125 0 1.094.3847 1.9829 1.1463 2.6433.7677.6372 1.7272.961 2.8524.961 1.1246 0 2.1766-.4495 3.1318-1.2191v.9587H99.42v-7.4852c0-1.4173-.457-2.523-1.359-3.2872zM115.4464 9.5808c-3.0682 0-5.5645 2.4755-5.5645 5.5188s2.4963 5.5188 5.5645 5.5188c3.0682 0 5.5645-2.4755 5.5645-5.5188s-2.4963-5.5188-5.5645-5.5188zm0 14.0408c-4.7383 0-8.5928-3.8228-8.5928-8.522 0-4.6994 3.8545-8.5223 8.5928-8.5223 4.738 0 8.5925 3.8229 8.5925 8.5223 0 4.6992-3.8545 8.522-8.5925 8.522z"></path> </g> </symbol>
    <symbol id="navbar-community_logo" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 532.2 99.8" fill="currentColor"> <path class="st0" d="M98.5,23c15.5,0,27.7,12.1,27.7,28.2c0,16.1-12.3,28.1-27.7,28.1c-15.6,0-27.7-11.9-27.7-28.1 C70.8,35.1,82.9,23,98.5,23z M98.5,67.9c8.7,0,14.9-7,14.9-16.8c0-9.8-6.2-16.8-14.9-16.8c-8.8,0-15,7-15,16.8 C83.5,60.9,89.7,67.9,98.5,67.9z"/> <path class="st0" d="M166.8,45.9c0-7-3.5-11.6-9.9-11.6c-7.2,0-11.1,5.3-11.1,13.1V78h-12.5V24.3h12.3V29c2.4-2.8,7-6,13.9-6 c7.3,0,12.2,3.1,15,7c4.4-4.9,10-7,16.8-7c14.4,0,21.4,8.5,21.4,23.8V78h-12.5V45.9c0-7-3.5-11.6-9.9-11.6 c-7.2,0-11.2,5.3-11.2,13.1V78h-12.4V45.9z"/> <path class="st0" d="M255.5,45.9c0-7-3.5-11.6-9.9-11.6c-7.2,0-11.1,5.3-11.1,13.1V78h-12.5V24.3h12.3V29c2.4-2.8,7-6,13.9-6 c7.3,0,12.2,3.1,15,7c4.4-4.9,10-7,16.8-7c14.4,0,21.4,8.5,21.4,23.8V78h-12.5V45.9c0-7-3.5-11.6-9.9-11.6 c-7.2,0-11.2,5.3-11.2,13.1V78h-12.4V45.9z"/> <path class="st0" d="M322.5,56.4c0,7,3.6,11.6,10.1,11.6c7.2,0,11.2-5.6,11.2-13.5V24.3h12.5V78h-12.3v-4.4 c-3.4,3.7-8.1,5.6-13.9,5.6c-11.9,0-20.1-8.4-20.1-23.7V24.3h12.5V56.4z"/> <path class="st0" d="M378.2,78h-12.5V24.3h12.3v4.4c2.7-3.1,7.7-5.7,13.9-5.7c13.1,0,21.3,8.5,21.3,23.8V78h-12.5V46.8 c0-7.5-3.7-12.5-10.6-12.5c-7.8,0-11.8,5.6-11.8,14V78z"/> <path class="st0" d="M427.8,0.2c4.4,0,7.9,3.4,7.9,7.8s-3.5,7.9-7.9,7.9c-4.4,0-7.9-3.5-7.9-7.9S423.4,0.2,427.8,0.2z M421.4,24.3 h12.5V78h-12.5V24.3z"/> <path class="st0" d="M446.7,59.1V35.5h-6.5V24.3h6.5v-15H459v15h12.2v11.2H459v21.7c0,7.8,1.8,9.8,8.8,9.8c1.2,0,4.1-0.2,4.1-0.2 v11.2c0,0-2.4,0.2-6.7,0.2C451.2,78.1,446.7,72.7,446.7,59.1z"/> <path class="st0" d="M497.3,78.7l-21.3-54.4h14.2l14,38.8l14.2-38.8h13.6l-24.1,60.2c-3.7,9.4-7.2,15.3-21.3,15.3 c-2.5,0-4.8-0.1-4.8-0.1V88c0,0,1.5,0.1,2.8,0.1c7.6,0,9.8-2.3,11.8-7.8L497.3,78.7z"/> <path class="st0" d="M62.4,55.9c-5.3,7-12.2,11.4-22.1,11.4c-15.6,0-27-11.7-27-27.5c0-16.1,11.4-27.8,26.5-27.8 c10,0,16.8,4.8,21.3,11.3l8.4-8.8C63.1,5.7,53.3,0,39.7,0C17.1,0,0,15.9,0,39.8c0,23.4,17.1,39.4,40.1,39.4c13.1,0,22-4.9,28.6-12.2 L62.4,55.9z"/> </symbol>
    <symbol id="navbar-control_panel_icon" viewBox="0 0 45 45" fill="none" xmlns="http://www.w3.org/2000/svg"> <path d="M19.6875 23.4862C19.6885 23.9722 19.4965 24.4388 19.1537 24.7833C18.8109 25.1279 18.3454 25.3222 17.8594 25.3237H3.23438C2.99366 25.3232 2.75539 25.2753 2.53321 25.1827C2.31102 25.09 2.10927 24.9545 1.93949 24.7839C1.7697 24.6132 1.63522 24.4108 1.54373 24.1881C1.45223 23.9655 1.40552 23.727 1.40626 23.4862V3.25498C1.40577 3.01417 1.45271 2.77562 1.54441 2.55295C1.63611 2.33028 1.77077 2.12785 1.9407 1.95722C2.11063 1.7866 2.31251 1.65111 2.5348 1.5585C2.75709 1.46589 2.99545 1.41797 3.23626 1.41748L17.8613 1.44186C18.347 1.44384 18.812 1.63843 19.1544 1.98292C19.4968 2.32741 19.6885 2.79366 19.6875 3.27936V23.4862Z" stroke="#0069FF" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/> <path d="M43.5863 12.27C43.5828 12.7516 43.3883 13.212 43.0456 13.5503C42.7028 13.8885 42.2397 14.0768 41.7582 14.0738H27.1332C26.8947 14.0755 26.6582 14.0302 26.4372 13.9405C26.2162 13.8507 26.015 13.7183 25.8453 13.5508C25.6755 13.3833 25.5404 13.1839 25.4477 12.9642C25.355 12.7444 25.3065 12.5085 25.3051 12.27V3.24565C25.308 2.76461 25.5019 2.30442 25.8439 1.96621C26.186 1.62799 26.6484 1.43941 27.1294 1.4419L41.7544 1.41753C42.2365 1.41403 42.7002 1.60205 43.0437 1.94027C43.3872 2.27849 43.5823 2.73924 43.5863 3.22128V12.27Z" stroke="#0069FF" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/> <path d="M19.6875 41.7956C19.686 42.0347 19.6375 42.2712 19.5446 42.4915C19.4518 42.7118 19.3164 42.9117 19.1463 43.0797C18.9762 43.2477 18.7747 43.3806 18.5532 43.4707C18.3318 43.5609 18.0947 43.6065 17.8556 43.605L3.23063 43.5806C2.74908 43.5826 2.28644 43.3934 1.94436 43.0545C1.60228 42.7155 1.40873 42.2547 1.40625 41.7731V32.7563C1.40748 32.5175 1.45575 32.2813 1.54831 32.0612C1.64087 31.8412 1.7759 31.6415 1.94569 31.4736C2.11547 31.3057 2.31667 31.173 2.53779 31.0829C2.75892 30.9929 2.99562 30.9473 3.23438 30.9488H17.8594C18.3414 30.9463 18.8047 31.1352 19.1475 31.4742C19.4903 31.8131 19.6845 32.2742 19.6875 32.7563V41.7956Z" stroke="#0069FF" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/> <path d="M27.1349 43.605C26.894 43.6045 26.6555 43.5565 26.433 43.4638C26.2106 43.3711 26.0087 43.2354 25.8387 43.0646C25.6688 42.8937 25.5341 42.6911 25.4426 42.4682C25.351 42.2453 25.3042 42.0066 25.3049 41.7656V21.5381C25.3042 21.2973 25.3509 21.0587 25.4424 20.8359C25.5338 20.6132 25.6683 20.4106 25.8381 20.2398C26.0078 20.069 26.2095 19.9333 26.4317 19.8405C26.6539 19.7476 26.8923 19.6995 27.1331 19.6987H41.7581C41.9989 19.6995 42.2372 19.7476 42.4594 19.8405C42.6816 19.9333 42.8833 20.069 43.0531 20.2398C43.2228 20.4106 43.3573 20.6132 43.4488 20.8359C43.5402 21.0587 43.5869 21.2973 43.5862 21.5381V41.7412C43.5872 42.2271 43.3955 42.6935 43.0532 43.0383C42.7109 43.3831 42.2458 43.5781 41.7599 43.5806L27.1349 43.605Z" stroke="#0069FF" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/> </symbol>
    <symbol id="navbar-community_icon" viewBox="0 0 45 45" fill="none" xmlns="http://www.w3.org/2000/svg"> <g clip-path="url(#clip0)"> <path d="M12.6562 10.5469C12.6562 9.85155 12.8624 9.17184 13.2487 8.5937C13.635 8.01556 14.1841 7.56495 14.8265 7.29886C15.4689 7.03277 16.1758 6.96315 16.8577 7.0988C17.5397 7.23445 18.1661 7.56929 18.6578 8.06095C19.1495 8.55262 19.4843 9.17905 19.6199 9.86101C19.7556 10.543 19.686 11.2499 19.4199 11.8922C19.1538 12.5346 18.7032 13.0837 18.1251 13.47C17.5469 13.8563 16.8672 14.0625 16.1719 14.0625" stroke="#0069FF" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/> <path d="M16.1719 18.2812C16.0328 18.2812 15.8969 18.3225 15.7812 18.3997C15.6656 18.477 15.5755 18.5868 15.5223 18.7153C15.4691 18.8438 15.4551 18.9852 15.4823 19.1215C15.5094 19.2579 15.5764 19.3832 15.6747 19.4816C15.773 19.5799 15.8983 19.6469 16.0347 19.674C16.1711 19.7011 16.3125 19.6872 16.4409 19.634C16.5694 19.5808 16.6792 19.4906 16.7565 19.375C16.8338 19.2594 16.875 19.1234 16.875 18.9844C16.875 18.7979 16.8009 18.6191 16.6691 18.4872C16.5372 18.3553 16.3584 18.2812 16.1719 18.2812Z" stroke="#0069FF" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/> <path d="M32.3438 4.21875V12.6562" stroke="#0069FF" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/> <path d="M29.5312 1.40625C30.2772 1.40625 30.9925 1.70257 31.52 2.23001C32.0474 2.75746 32.3438 3.47283 32.3438 4.21875" stroke="#0069FF" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/> <path d="M4.21875 1.40625H29.5312" stroke="#0069FF" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/> <path d="M1.40625 4.21875C1.40625 3.47283 1.70257 2.75746 2.23001 2.23001C2.75746 1.70257 3.47283 1.40625 4.21875 1.40625" stroke="#0069FF" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/> <path d="M1.40625 23.9062V4.21875" stroke="#0069FF" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/> <path d="M4.21875 26.7188C3.47283 26.7187 2.75746 26.4224 2.23001 25.895C1.70257 25.3675 1.40625 24.6522 1.40625 23.9062" stroke="#0069FF" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/> <path d="M9.84375 26.7188H4.21875" stroke="#0069FF" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/> <path d="M9.84375 35.1562V26.7188" stroke="#0069FF" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/> <path d="M15.4688 30.9375L9.84375 35.1562" stroke="#0069FF" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/> <path d="M43.5938 35.1562H37.9688V43.5938L29.5312 35.1562H21.0938V18.2812H43.5938V35.1562Z" stroke="#0069FF" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/> <path d="M32.3438 23.9062V29.5312" stroke="#0069FF" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/> </g> <defs> <clipPath id="clip0"> <rect width="45" height="45" fill="white"/> </clipPath> </defs> </symbol>
    <symbol id="navbar-search" viewBox="0 0 16 16" fill="currentColor"><path fill-rule="evenodd" d="M15.7 13.3l-3.81-3.83A5.93 5.93 0 0 0 13 6c0-3.31-2.69-6-6-6S1 2.69 1 6s2.69 6 6 6c1.3 0 2.48-.41 3.47-1.11l3.83 3.81c.19.2.45.3.7.3.25 0 .52-.09.7-.3a.996.996 0 0 0 0-1.41v.01zM7 10.7c-2.59 0-4.7-2.11-4.7-4.7 0-2.59 2.11-4.7 4.7-4.7 2.59 0 4.7 2.11 4.7 4.7 0 2.59-2.11 4.7-4.7 4.7z"></path></symbol>
    <symbol id="navbar-logomark" viewBox="65.2 173.5 180 180" fill="currentColor"><path d="M155.2,351.7v-34.2c36.2,0,64.3-35.9,50.4-74c-5.1-14.1-16.4-25.4-30.5-30.5c-38.1-13.8-74,14.2-74,50.4l0,0H67c0-57.7,55.8-102.7,116.3-83.8c26.4,8.3,47.5,29.3,55.7,55.7C257.9,295.9,213,351.7,155.2,351.7z"/> <polygon points="155.3,317.6 121.3,317.6 121.3,283.6 121.3,283.6 155.3,283.6 155.3,283.6"/> <polygon points="121.3,343.8 95.1,343.8 95.1,343.8 95.1,317.6 121.3,317.6"/> <path d="M95.1,317.6H73.2l0,0v-21.9l0,0h21.9l0,0V317.6z"/></symbol>
    <symbol id="navbar-hubforgood" viewBox="6 6 30 30" width="30" height="30" fill="none" stroke="currentColor" stroke-width="1.5"><circle class="cls-3" cx="21" cy="21.03" r="8.92"/><path class="cls-3" d="M12.08,21a8.94,8.94,0,0,1,8.6-8.92"/><path class="cls-3" d="M29.92,21a9.18,9.18,0,0,1-2.61,6.37A9,9,0,0,1,20.75,30"/><path class="cls-3" d="M21,25.36S16.35,22.69,16.35,20a2.3,2.3,0,0,1,4.59,0h0a2.28,2.28,0,0,1,2.29-2.29A2.25,2.25,0,0,1,25.52,20C25.65,22.69,21,25.36,21,25.36Z"/><path class="cls-3" d="M7.43,20.84A13.49,13.49,0,0,1,20.68,7.46"/><path class="cls-3" d="M34.57,20.91a13.57,13.57,0,0,1-3.95,9.68,13.35,13.35,0,0,1-9.68,3.95"/><path class="cls-3" d="M20.87,34.6a13.42,13.42,0,0,1-9.49-4,13.64,13.64,0,0,1-4-9.81l4.65.13a8.94,8.94,0,0,0,2.61,6.31,9.09,9.09,0,0,0,6.06,2.61Z"/><path class="cls-3" d="M29.92,21a9.06,9.06,0,0,0-2.61-6.31,8.89,8.89,0,0,0-6.63-2.61V7.4a13.76,13.76,0,0,1,9.88,3.95,13.42,13.42,0,0,1,3.95,9.49Z"/></symbol>
    <symbol id="navbar-write4do" viewBox="0 0 30 30" fill="none" stroke="currentColor"> <path d="M16.3063 17.67L11.6663 18.3338L12.3288 13.6925L24.2613 1.76002C24.7887 1.23257 25.5041 0.936249 26.25 0.936249C26.6194 0.936249 26.9851 1.009 27.3263 1.15034C27.6675 1.29168 27.9776 1.49885 28.2388 1.76002C28.4999 2.02118 28.7071 2.33123 28.8484 2.67246C28.9898 3.01369 29.0625 3.37942 29.0625 3.74877C29.0625 4.11811 28.9898 4.48384 28.8484 4.82507C28.7071 5.1663 28.4999 5.47635 28.2388 5.73752L16.3063 17.67Z" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"/> <path d="M22.935 3.08624L26.9125 7.06374"  stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"/> <path d="M23.4375 17.8125V27.1875C23.4375 27.6848 23.24 28.1617 22.8883 28.5133C22.5367 28.865 22.0598 29.0625 21.5625 29.0625H2.8125C2.31522 29.0625 1.83831 28.865 1.48667 28.5133C1.13504 28.1617 0.9375 27.6848 0.9375 27.1875V8.4375C0.9375 7.94022 1.13504 7.46331 1.48667 7.11167C1.83831 6.76004 2.31522 6.5625 2.8125 6.5625H12.1875" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"/> </symbol>
    <symbol id="navbar-hacktoberfest" viewBox="0 0 30 30" fill="none" stroke="currentColor"> <path d="M19.2063 24.9918L16.5714 22.3569V14.4854L13.986 17.0708V23.5755L12.5615 25L11.1371 23.5591V8.44175L10.7419 8.04652L8.93042 9.8662L8 8.94401L11.9358 5.00823L11.944 5.01647L12.1005 5.16468L13.9778 7.04199V13.8431L16.5632 11.2577V8.42528L15.2705 7.12433L17.3948 5L19.4286 7.03376V20.9572L20.4249 21.9535L21.6352 20.7431L22.5492 21.6571L19.2063 24.9918Z" fill="currentcolor"/> <rect x="0.75" y="0.75" width="28.5" height="28.5" rx="2.25" stroke-width="1.5" stroke="currentColor"/> </symbol>
    <symbol id="navbar-build" viewBox="0 0 16 16" fill="none" stroke="currentColor"> <path d="M1.5 14.5C1.23478 14.5 0.98043 14.3946 0.792893 14.2071C0.605357 14.0196 0.5 13.7652 0.5 13.5V2.57667C0.500879 2.29139 0.614596 2.01804 0.81632 1.81632C1.01804 1.6146 1.29139 1.50088 1.57667 1.5H14.4287C14.7125 1.50088 14.9845 1.61403 15.1852 1.81476C15.386 2.01548 15.4991 2.28747 15.5 2.57133V13.4233C15.4991 13.7086 15.3854 13.982 15.1837 14.1837C14.982 14.3854 14.7086 14.4991 14.4233 14.5H1.5Z" stroke-linecap="round" stroke-linejoin="round"/> <path d="M15.5 4.5H0.5" stroke-linecap="round" stroke-linejoin="round"/> <path d="M11 7.5L13 9.5L11 11.5" stroke-linecap="round" stroke-linejoin="round"/> <path d="M5 7.5L3 9.5L5 11.5" stroke-linecap="round" stroke-linejoin="round"/> <path d="M9 7.5L7 11.5" stroke-linecap="round" stroke-linejoin="round"/> </symbol>
  </svg>
</div>

<nav class="navbar" role="navigation" aria-label="Navigation" data-js="global-navbar">
  <ul role="menubar" class="utility">
    <li role="banner" data-flex="grow" data-show="always" data-js="global-navbar-banner">
    </li>
    <li role="menuitem">
      <a href="/products/">Products</a>
    </li>
    <li role="menuitem">
      <a href="/pricing/">Pricing</a>
    </li>
    <li role="menuitem" aria-haspopup="true" tabindex="0">
      <span class="expander">Docs</span>
      <div role="menuitem" class="mini" aria-expanded="false">
        <ul role="menu">
          <li role="menuitem">
            <a href="/docs/">Product Docs</a>
          </li>
          <li role="menuitem">
            <a href="https://developers.digitalocean.com/documentation/">API Docs</a>
          </li>
        </ul>
      </div>
    </li>
      <li role="menuitem" aria-haspopup="true" tabindex="0">
      <span class="expander">Sign in</span>
        <div role="menuitem" class="mini" aria-expanded="false">
          <header>Sign in to</header>
          <ul role="menu">
            <li role="menuitem">
              <svg xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink">
                <use xlink:href="#navbar-community_icon"></use>
              </svg>
              <a id="log-in" href="/community/auth/digitalocean">Community</a>
            </li>
            <li role="menuitem">
              <svg xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink">
                <use xlink:href="#navbar-control_panel_icon"></use>
              </svg>
              <a href="https://cloud.digitalocean.com/registrations/new">Control Panel</a>
            </li>
          </ul>
        </div>
      </li>
  </ul>

  <ul role="menubar" class="primary">
    <li role="menuitem" data-show="always" class="logo-square">
      <a href="https://www.digitalocean.com/">
        <svg xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" shape-rendering="auto">
          <use xlink:href="#navbar-logomark"></use>
        </svg>
      </a>
    </li>
    <li role="menuitem" data-show="always">
      <a title="DigitalOcean Community Home" class="home" href="/community">
        <svg xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" width="120px" height="24px"
             shape-rendering="auto">
          <use xlink:href="#navbar-community_logo"></use>
        </svg>
</a>    </li>
    <li role="menuitem">
      <a data-activatable="true" href="/community/tutorials">Tutorials</a>
    </li>
    <li role="menuitem">
      <a data-activatable="true" href="/community/questions">Questions</a>
    </li>
    <li role="menuitem" aria-haspopup="true" class="mega_parent" tabindex="0">
      <span class="expander">Get Involved</span>
      <div role="menuitem" class="mega" aria-expanded="false">
        <div class="section column">
          <header>Participate</header>
          <ul role="menu">
            <li role="menuitem">
              <a href="https://www.digitalocean.com/community/pages/hub-for-good" class="with_image">
                <svg xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink">
                  <use xlink:href="#navbar-hubforgood"></use>
                </svg>
                <p>
                  <strong>Hub for Good</strong>
                  Supporting each other to make an impact
                </p>
              </a>
            </li>
            <li role="menuitem">
              <a class="with_image" href="/community/pages/write-for-digitalocean">
                <svg xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink">
                  <use xlink:href="#navbar-write4do"></use>
                </svg>
                <p>
                  <strong>Write for DigitalOcean</strong>
                  You get paid, we donate to tech non-profits.
                </p>
</a>            </li>
            <li role="menuitem">
              <a href="https://hacktoberfest.digitalocean.com" class="with_image">
                <svg xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink">
                  <use xlink:href="#navbar-hacktoberfest"></use>
                </svg>
                <p>
                  <strong>Hacktoberfest</strong>
                  Contribute to Open Source
                </p>
              </a>
            </li>
          </ul>
        </div>
        <div class="section column">
          <header>
            <svg xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink">
              <use xlink:href="#navbar-build"></use>
            </svg>
            Build with DigitalOcean
          </header>
          <ul role="menu" class="indent">
            <li role="menuitem">
              <a title="Community-built tools and integrations that use the DigitalOcean API" href="/community/tools">Community Tools and Integrations</a>
            </li>
            <li role="menuitem">
              <a href="https://www.digitalocean.com/hatch/" title="Build your startup on DigitalOcean.">
                Hatch Startup Program
              </a>
            </li>
            <li role="menuitem">
              <a href="https://marketplace.digitalocean.com/vendors/"
                 title="List your open source One-Click Application in the DigitalOcean Marketplace">
                Marketplace Partner Program
              </a>
            </li>
            <li role="menuitem">
              <a href="https://www.digitalocean.com/partners/solutions-partners/"
                 title="Easily deploy & modernize your clients’ infrastructures with the Solutions Partner Program">
                Solutions Partner Program
              </a>
            </li>
            <li role="menuitem">
              <a href="https://www.digitalocean.com/droplets-for-demos/"
                 title="DigitalOcean credits to fund research for conference and meetup presentations">
                Presentation Grants
              </a>
            </li>
            <li role="menuitem">
              <a href="https://github.com/digitalocean"
                 title="View all the open-source projects that DigitalOcean have on GitHub">
                DigitalOcean on GitHub
              </a>
            </li>
          </ul>
        </div>
      </div>
    </li>
    <li role="menuitem" data-show="mobile" data-flex="grow" class="right">
      <a href="javascript:void(0);" data-js="modal_toggle" data-body-class="mobile_nav_expanded">
        <span class="icon-menu-thin"></span>
      </a>
    </li>
    <li role="menuitem" data-flex="grow">
      <button id="q" class="search_button">
          <svg xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" shape-rendering="auto"
               width="14px" height="14px">
            <use xlink:href="#navbar-search"></use>
          </svg>
          Search DigitalOcean
          <kbd>/</kbd>
      </button>
    </li>
    <li role="menuitem">
      <a class="button blue-button small-button" href="/community/auth/digitalocean?display=sessionless+register+button">Sign Up</a>
    </li>
  </ul>

  <div class="mobile_nav_bg" data-js="modal_toggle"></div>
  <div class="mobile_nav">
    <a data-dismiss='modal' aria-label="close" href="javascript:void(0);" data-js="modal_toggle"><span class="icon-close"></span></a>
    <div class="mobile_nav_content">
      <header>Community</header>
      <ul role="menu">
        <li role="menuitem">
          <a data-activatable="true" href="/community/tutorials">Tutorials</a>
        </li>
        <li role="menuitem">
          <a data-activatable="true" href="/community/questions">Questions</a>
        </li>
        <li role="menuitem">
          <a href="/community/pages/write-for-digitalocean">Write for Us</a>
        </li>
        <li role="menuitem">
          <a href="https://hacktoberfest.digitalocean.com">Hacktoberfest</a>
        </li>
        <li role="menuitem">
          <a href="/community/tools">Tools</a>
        </li>
      </ul>
      <header>Products</header>
      <ul role="menu">
        <li role="menuitem">
          <a href="https://www.digitalocean.com/">Homepage</a>
        </li>
        <li role="menuitem">
          <a href="https://www.digitalocean.com/pricing">Pricing</a>
        </li>
        <li role="menuitem">
          <a href="https://www.digitalocean.com/products">Product Overview</a>
        </li>
        <li role="menuitem">
          <a href="https://marketplace.digitalocean.com/">Marketplace</a>
        </li>
      </ul>
      <header>Customers</header>
      <ul role="menu">
        <li role="menuitem">
          <a href="https://cloud.digitalocean.com/login">Control Panel</a>
        </li>
        <li role="menuitem">
          <a href="https://www.digitalocean.com/docs/">Documentation</a>
        </li>
        <li role="menuitem">
          <a href="https://www.digitalocean.com/company/contact/#support">Contact Support</a>
        </li>
        <li role="menuitem">
          <a href="https://www.digitalocean.com/company/contact/sales/">Contact Sales</a>
        </li>
      </ul>

      <ul role="menu">
        <li role="menuitem" class="mobile-log-in">
            <a id="log-in" href="/community/auth/digitalocean">Sign In</a>
        </li>
      </ul>
    </div>
  </div>
</nav>

<header>
  <div class="legacy-header ">
    <div class="flash-container">
      
    </div>

    <div class="wrapper">
      
    </div>
  </div>
</header>



      

      <div class='wrapper layout-wrapper'>

        












<div class="section-content section-content-growable content Tutorial-content">
  

  <div class="container tutorial-header">
    

      <div class="featured-items-right-bar">
        <h3>Related</h3>
          <a href="https://www.digitalocean.com/community/tools/nginx">
            <div class="featured-item-highlight" data-js="tutorial">
                  <span class="featured-item-highlight-image"><img width="45" height="45" alt="Tool" src="https://images.prismic.io/digitalocean/4b8cf536-a272-426e-8c69-72afefddd52c_nginx.png?auto=compress,format&amp;rect=0,0,40,40&amp;w=40&amp;h=40" /></span>
                NGINX Config Generator
                <span class="featured-item-category">
                  
                  Tool
                </span>
              </div>
</a>          <a href="/community/tutorials/how-to-set-up-a-node-js-application-for-production-on-ubuntu-20-04-pt">
            <div class="featured-item-regular" data-js="tutorial">
                  Como configurar um aplicativo Node.js para produção no Ubuntu 20.04
                  <span class="featured-item-category">
                    <img width="14" height="14" alt="Tutorial" src="/assets/community/tutorials/featured-item-tutorial-icon-bce4d5cc06536a907c48f6663a93392cdf6c5f30677b48439d1164c89fb71ad1.png" />
                    Tutorial
                  </span>
                </div>
</a>          <a href="/community/tutorials/how-to-install-wordpress-on-ubuntu-20-04-with-a-lamp-stack-pt">
            <div class="featured-item-regular" data-js="tutorial">
                  Como instalar o WordPress no Ubuntu 20.04 com uma pilha LAMP
                  <span class="featured-item-category">
                    <img width="14" height="14" alt="Tutorial" src="/assets/community/tutorials/featured-item-tutorial-icon-bce4d5cc06536a907c48f6663a93392cdf6c5f30677b48439d1164c89fb71ad1.png" />
                    Tutorial
                  </span>
                </div>
</a>      </div>


    

    <h4 class="eyebrow">Tutorial</h4>
    <h1 class="content-title Tutorial-header">Como Instalar Linux, Nginx, MySQL, PHP (pilha LEMP) no Ubuntu 20.04</h1>
    <span class="meta-section tags">
  <a class="tag" href="/community/tags/nginx">Nginx</a><a class="tag" href="/community/tags/ubuntu">Ubuntu</a><a class="tag" href="/community/tags/php">PHP</a><a class="tag" href="/community/tags/lemp">LEMP</a><a class="tag" href="/community/tags/ubuntu-20-04">Ubuntu 20.04</a>
</span>


    <div class="tutorial-authors-translations">
      <div class="tutorial-authors">
        <div class="component-collaborators-container">
  <ul class="component-collaborators-content">
        <li class="collaborator-byline-avatar">
          <a href="/community/users/erikaheidi">
            <div class="mod-avatar mod-avatar-large"><img class="avatar avatar-large" src="https://community-cdn-digitalocean-com.global.ssl.fastly.net/assets/users/avatars/large/4c3251574011991e1d7c79990a16a45759a2ecdd.jpeg?1582714750" /><span class="mod-star" title="MOD" data-toggle="tooltip" data-container="body"><span class="mod-star-icon"></span></span></div>
</a>        </li>

    <li class="collaborators-byline-data">
        <p class="names">By <a href="/community/users/erikaheidi">Erika Heidi</a></p>

      <span class="meta-section date-views">
  <span class="meta-section timestamp"><span class="tutorial-date-text">Posted</span><span class="tutorial-date">May 15, 2020</span></span>
  <span class="meta-section pageviews"><span class="icon icon-eye v-mid"></span><span class="views-count v-mid">1.3k</span><span class="sr-only"> views</span></span>
</span>

    </li>
  </ul>
</div>

      </div>

        <select name="translation_language" id="translation_language" autocomplete="off" class="large-chosen-dropdown"><option value="/community/tutorials/how-to-install-linux-nginx-mysql-php-lemp-stack-on-ubuntu-20-04">English</option>
<option value="/community/tutorials/how-to-install-linux-nginx-mysql-php-lemp-stack-on-ubuntu-20-04-de">Deutsch</option>
<option value="/community/tutorials/how-to-install-linux-nginx-mysql-php-lemp-stack-on-ubuntu-20-04-es">Español</option>
<option value="/community/tutorials/how-to-install-linux-nginx-mysql-php-lemp-stack-on-ubuntu-20-04-fr">Français</option>
<option selected="selected" value="/community/tutorials/how-to-install-linux-nginx-mysql-php-lemp-stack-on-ubuntu-20-04-pt">Português</option>
<option value="/community/tutorials/how-to-install-linux-nginx-mysql-php-lemp-stack-on-ubuntu-20-04-ru">Русский</option></select>
    </div>
  </div>

  




  <div class="content-body tutorial-content" data-growable-markdown>
    
    <h3 id="introdução">Introdução</h3>

<p>A pilha de software LEMP é um grupo de softwares que pode ser usado para exibir páginas e aplicativos Web dinâmicos escritos em PHP. Este é um acrônimo que descreve um sistema operacional <strong>L</strong>inux, com um servidor Web Nginx (se pronuncia &ldquo;<strong>E</strong>ngine-X). Os dados do backend são armazenados no banco de dados <strong>M</strong>ySQL e o processamento dinâmico é tratado pelo <strong>P</strong>HP.</p>

<p>Este guia demonstra como instalar uma pilha LEMP em um servidor Ubuntu 20.04. O sistema operacional Ubuntu cuida do primeiro requisito. Vamos descrever como colocar o resto dos componentes em funcionamento.</p>

<h2 id="pré-requisitos">Pré-requisitos</h2>

<p>Para completar este tutorial, você precisará de acesso a um servidor Ubuntu 20.04, como um usuário <code>sudo</code> regular, não root , e um firewall habilitado em seu servidor. Para configurar isto, siga nosso <a href="https://www.digitalocean.com/community/tutorials/initial-server-setup-with-ubuntu-20-04">guia de configuração inicial de servidor para o Ubuntu 20.04</a>.</p>

<h2 id="passo-1-—-como-instalar-o-servidor-web-nginx">Passo 1 — Como instalar o servidor Web Nginx</h2>

<p>Para mostrar páginas Web aos visitantes de nosso site, vamos usar o Nginx, um servidor Web de alto desempenho. Usaremos o gerenciador de pacotes <code>apt</code> para obter esse software.</p>

<p>Uma vez que essa é a primeira vez que vamos usar o <code>apt</code> para esta sessão, atualize o índice de pacotes do seu servidor. Em seguida, você pode usar o <code>apt install</code> para instalar o Nginx:</p>
<pre class="code-pre command prefixed"><code><ul class="prefixed"><li class="line" prefix="$">sudo apt update
</li><li class="line" prefix="$">sudo apt install nginx
</li></ul></code></pre>
<p>Quando solicitado, digite <code>y</code> para confirmar se deseja instalar o Nginx. Assim que a instalação terminar, o servidor web Nginx estará ativo e em execução em seu servidor Ubuntu 20.04.</p>

<p>Se você tiver o firewall <code>ufw</code> habilitado, conforme recomendado em nosso guia de configuração inicial de servidor, você precisará permitir conexões com o Nginx. O Nginx registra alguns perfis diferentes de aplicações no UFW após a instalação. Para verificar quais perfis do UFW estão disponíveis, execute:</p>
<pre class="code-pre command prefixed"><code><ul class="prefixed"><li class="line" prefix="$">sudo ufw app list
</li></ul></code></pre><pre class="code-pre "><code><div class="secondary-code-label " title="Output">Output</div>Available applications:
  Nginx Full
  Nginx HTTP
  Nginx HTTPS
  OpenSSH
</code></pre>
<p>É recomendável que você habilite o perfil mais restritivo que, ainda assim, permitirá o tráfego que você precisa. Como você ainda não configurou o SSL para seu servidor neste guia, você precisará apenas permitir o tráfego HTTP regular na porta <code>80</code>.</p>

<p>Habilite isso digitando:</p>
<pre class="code-pre command prefixed"><code><ul class="prefixed"><li class="line" prefix="$">sudo ufw allow 'Nginx HTTP'
</li></ul></code></pre>
<p>Verifique a mudança executando:</p>
<pre class="code-pre command prefixed"><code><ul class="prefixed"><li class="line" prefix="$">sudo ufw status
</li></ul></code></pre>
<p>A saída deste comando irá mostrar que o tráfego HTTP está permitido agora:</p>
<pre class="code-pre "><code><div class="secondary-code-label " title="Output">Output</div>Status: active

To                         Action      From
--                         ------      ----
OpenSSH                    ALLOW       Anywhere
<span class="highlight">Nginx HTTP                 ALLOW       Anywhere</span>
OpenSSH (v6)               ALLOW       Anywhere (v6)
<span class="highlight">Nginx HTTP (v6)            ALLOW       Anywhere (v6)</span>
</code></pre>
<p>Com essas novas regras adicionadas no firewall, você pode testar se o servidor está funcionando acessando o nome do domínio do seu servidor ou endereço IP público no seu navegador Web.</p>

<p>Se você não tiver um nome de domínio apontando para o seu servidor e você não souber o endereço IP público dele, é possível encontrá-lo executando o seguinte comando:</p>
<pre class="code-pre command prefixed"><code><ul class="prefixed"><li class="line" prefix="$">ip addr show eth0 | grep inet | awk '{ print $2; }' | sed 's/\/.*$//'
</li></ul></code></pre>
<p>Isso irá mostrar na tela alguns endereços IP. Você pode testar cada um deles em seu navegador Web.</p>

<p>Como uma alternativa, verifique qual endereço IP está acessível, como visto por outros locais na internet:</p>
<pre class="code-pre command prefixed"><code><ul class="prefixed"><li class="line" prefix="$">curl -4 icanhazip.com
</li></ul></code></pre>
<p>Digite o endereço que receber no seu navegador Web e ele irá levá-lo para a página inicial do Nginx:</p>
<pre class="code-pre "><code>http://<span class="highlight">server_domain_or_IP</span>
</code></pre>
<p><img src="https://assets.digitalocean.com/articles/lemp_ubuntu2004/nginx_default.png" alt="Nginx default page"></p>

<p>Se você vir essa página, significa que você instalou o Nginx com sucesso e habilitou o tráfego HTTP para seu servidor web.</p>

<h2 id="passo-2-—-instalando-o-mysql">Passo 2 — Instalando o MySQL</h2>

<p>Agora que você tem um servidor web funcionando, você precisa instalar um sistema de banco de dados, para conseguir armazenar e gerenciar os dados do seu site. O MySQL é um sistema de gerenciamento de banco de dados popular, usado em ambientes PHP.</p>

<p>Novamente, utilize o <code>apt</code> para adquirir e instalar este software:</p>
<pre class="code-pre command prefixed"><code><ul class="prefixed"><li class="line" prefix="$">sudo apt install mysql-server
</li></ul></code></pre>
<p>Quando solicitado, confirme a instalação digitando <code>Y</code> e, depois, <code>ENTER</code>.</p>

<p>Quando a instalação terminar, é recomendável que você execute um script de segurança que vem pré-instalado com o MySQL. Esse script removerá algumas configurações padrão inseguras e irá bloquear o acesso ao seu sistema de banco de dados. Inicie o script interativo executando:</p>
<pre class="code-pre command prefixed"><code><ul class="prefixed"><li class="line" prefix="$">sudo mysql_secure_installation
</li></ul></code></pre>
<p>Este script irá perguntar se você deseja configurar o <code>VALIDATE PASSWORD PLUGIN</code>.</p>

<p><span class='warning'><strong>Atenção:</strong> ativar esta característica é uma decisão sua. Se habilitada, as senhas que não corresponderem ao critério especificado serão rejeitadas pelo MySQL com um erro. É seguro deixar a validação desativada, mas sempre utilize senhas fortes e únicas para as credenciais do banco de dados.<br></span></p>

<p>Responda <code>Y</code> para sim, ou qualquer outra coisa para continuar sem a habilitar.</p>
<pre class="code-pre "><code>VALIDATE PASSWORD PLUGIN can be used to test passwords
and improve security. It checks the strength of password
and allows the users to set only those passwords which are
secure enough. Would you like to setup VALIDATE PASSWORD plugin?

Press y|Y for Yes, any other key for No:
</code></pre>
<p>Se você responder &quot;yes&rdquo;, você será solicitado a selecionar um nível de validação por senha. Lembre-se de que se você digitar <code>2</code> para o nível mais forte você receberá erros ao tentar definir qualquer senha que não contenha números, letras maiúsculas e minúsculas, e caracteres especiais, ou que baseiam-se em palavras comuns do dicionário.</p>
<pre class="code-pre "><code>There are three levels of password validation policy:

LOW    Length &gt;= 8
MEDIUM Length &gt;= 8, numeric, mixed case, and special characters
STRONG Length &gt;= 8, numeric, mixed case, special characters and dictionary              file

Please enter 0 = LOW, 1 = MEDIUM and 2 = STRONG: <span class="highlight">1</span>
</code></pre>
<p>Independentemente de você ter escolhido <code>VALIDATE PASSWORD PLUGIN</code>, seu servidor irá pedir a você para selecionar e confirmar uma senha para o.<strong>root</strong> user do MySQL. Isso não deve ser confundido com o <strong>root do sistema</strong>. O usuário <strong>root do banco de dados</strong> é um usuário administrativo com privilégios totais sobre o sistema de banco de dados. Embora o método de autenticação predefinido para o usuário root dispense o uso de uma senha, <strong>mesmo quando uma senha está definida</strong>, você deve definir uma senha forte aqui como uma medida de segurança adicional. Vamos falar sobre isso em breve.</p>

<p>Se você habilitar a validação por senha, será apresentado a você a força da senha para a senha root. e o seu servidor perguntará se você deseja continuar com essa senha. Se estiver satisfeito com sua senha atual, digite <code>Y</code> para &ldquo;yes&rdquo; no prompt:</p>
<pre class="code-pre "><code>Estimated strength of the password: <span class="highlight">100</span>
Do you wish to continue with the password provided?(Press y|Y for Yes, any other key for No) : <span class="highlight">y</span>
</code></pre>
<p>Para o resto das perguntas, pressione <code>Y</code> e pressione a tecla <code>ENTER</code> em cada prompt. Isso removerá alguns usuários anônimos e o banco de dados de teste, desativará os logins remotos para o root e carregará essas novas regras para que o MySQL respeite imediatamente as alterações que você fez.</p>

<p>Quando terminar, teste se você consegue fazer login no console do MySQL digitando:</p>
<pre class="code-pre command prefixed"><code><ul class="prefixed"><li class="line" prefix="$">sudo mysql
</li></ul></code></pre>
<p>Isso conectará ao servidor MySQL como usuário administrativo <strong>root</strong> do banco de dados, o que é pressuposto pelo uso do <code>sudo</code> ao executar esse comando. Você deve ver um resultado como este:</p>
<pre class="code-pre "><code><div class="secondary-code-label " title="Output">Output</div>Welcome to the MySQL monitor.  Commands end with ; or \g.
Your MySQL connection id is 22
Server version: 8.0.19-0ubuntu5 (Ubuntu)

Copyright (c) 2000, 2020, Oracle and/or its affiliates. All rights reserved.

Oracle is a registered trademark of Oracle Corporation and/or its
affiliates. Other names may be trademarks of their respective
owners.

Type 'help;' or '\h' for help. Type '\c' to clear the current input statement.

mysql&gt;
</code></pre>
<p>Para sair do console do MySQL, digite:</p>
<pre class="code-pre custom_prefix prefixed"><code><ul class="prefixed"><li class="line" prefix="mysql&gt;">exit
</li></ul></code></pre>
<p>Note que você não precisa fornecer uma senha para se conectar como <strong>root</strong> user, embora você tenha definido uma ao executar o script <code>mysql_secure_installation</code>. Isso é porque o método de autenticação padrão para o usuário administrativo do MySQL é <code>unix_socket</code>, em vez de <code>password</code> (senha). Embora, num primeiro momento, isso possa parecer um problema de segurança, tal medida torna o servidor de banco de dados mais seguro, uma vez que que os únicos usuários autorizados a fazer login como usuário <strong>root</strong> do MySQL são os usuários do sistema com privilégios sudo que conectam-se pelo console ou através de uma aplicação executando com os mesmos privilégios. Em termos práticos, isso significa que você não conseguirá usar o usuário <strong>root</strong> do banco de dados administrativo para se conectar a partir do seu aplicativo PHP. Definir uma senha para a conta <strong>root</strong> do MySQL funciona como uma salvaguarda, caso o método de autenticação padrão seja alterado de <code>unix_socket</code> para <code>password</code>.</p>

<p>Para aumentar a segurança, o melhor é configurar contas de usuário dedicadas, com privilégios menos abrangentes em relação a cada banco de dados, especialmente se você planeja ter vários bancos de dados hospedados no seu servidor.</p>

<p><span class='note'><strong>Nota:</strong> no momento em que este artigo foi escrito, a biblioteca nativa do PHP para o MySQL <code>mysqlnd</code> <a href="https://www.php.net/manual/en/ref.pdo-mysql.php">não suporta</a> o <code>caching_sha2_authentication</code>, o método de autenticação padrão para o MySQL 8. Por essa razão, ao criar usuários de banco de dados para aplicações PHP no MySQL 8, você precisará garantir que eles estejam configurados para usar o <code>mysql_native_password</code>. Vamos demonstrar como fazer isso no <a href="#step-6-%E2%80%94-testing-database-connection-from-php-(optional)">Passo 6</a>.<br></span></p>

<p>Agora, seu servidor MySQL está instalado e protegido. Em seguida, instalaremos o PHP, o componente final na pilha LEMP.</p>

<h2 id="passo-3-—-instalando-o-php">Passo 3 — Instalando o PHP</h2>

<p>Você tem o Nginx instalado para exibir seu conteúdo e o MySQL instalado para armazenar e gerenciar seus dados. Agora, você pode instalar o PHP para processar código e gerar conteúdo dinâmico para o servidor Web.</p>

<p>Enquanto o Apache incorpora o interpretador PHP em cada solicitação, o Nginx necessita de um programa externo para lidar com o processamento PHP e atuar como uma ponte entre o próprio interpretador PHP e o servidor web. Isso permite um desempenho global melhor na maioria dos sites baseados em PHP, mas exige configuração adicional. Será necessário instalar o <code>php-fpm</code>, que significa &ldquo;Gerenciador de processos PHP fastCGI&rdquo;, e dizer ao Nginx para enviar as solicitações PHP para esse software para processamento. Adicionalmente, você precisará do <code>php-mysql</code> , um módulo PHP que permite ao PHP se comunicar com os bancos de dados baseados em MySQL. Os pacotes básicos do PHP serão instalados automaticamente como dependências.</p>

<p>Para instalar os pacotes <code>php-fpm</code> e <code>php-mysql</code>, execute:</p>
<pre class="code-pre command prefixed"><code><ul class="prefixed"><li class="line" prefix="$">sudo apt install php-fpm php-mysql
</li></ul></code></pre>
<p>Quando solicitado, digite <code>Y</code> e <code>ENTER</code> para confirmar a instalação.</p>

<p>Agora, você tem seus componentes PHP instalados. Em seguida, você configurará o Nginx para utilizá-los.</p>

<h2 id="passo-4-—-configurando-o-nginx-para-usar-o-processador-php">Passo 4 — Configurando o Nginx para Usar o Processador PHP</h2>

<p>Ao usar o servidor web Nginx, podemos utilizar os <em>blocos de servidor</em> (similares aos virtual hosts no Apache) para encapsular detalhes de configuração e hospedar mais de um domínio em um único servidor. Neste guia, usaremos <strong>your_domain</strong> como um nome de domínio de exemplo. Para aprender mais sobre como configurar um nome de domínio com a DigitalOcean, veja nossa <a href="https://www.digitalocean.com/docs/networking/dns/">Introdução ao DNS do DigitalOcean</a>.</p>

<p>No Ubuntu 20.04, o Nginx tem um bloco de servidor habilitado por padrão que está configurado para servir documentos do diretório <code>/var/www/html</code>. Enquanto isso funciona bem para um único site, isso se torna difícil de gerenciar se você estiver hospedando vários sites. Em vez de modificar o <code>/var/www/html</code>, vamos criar uma estrutura de diretórios dentro do <code>/var/www</code> para o site <strong>your_domain</strong>, deixando o <code>/var/www/html</code> intocado como o diretório padrão para ser servido se uma solicitação de cliente não corresponder a nenhum outro site.</p>

<p>Crie o diretório para <strong>your_domain</strong> como segue:</p>
<pre class="code-pre command prefixed"><code><ul class="prefixed"><li class="line" prefix="$">sudo mkdir /var/www/<span class="highlight">your_domain</span>
</li></ul></code></pre>
<p>Em seguida, atribua a propriedade do diretório com a variável de ambiente $USER, que deve fazer referência ao seu usuário de sistema atual:</p>
<pre class="code-pre command prefixed"><code><ul class="prefixed"><li class="line" prefix="$">sudo chown -R $USER:$USER /var/www/<span class="highlight">your_domain</span>
</li></ul></code></pre>
<p>Em seguida, abra um novo arquivo de configuração no diretório <code>sites-available</code> do Nginx usando seu editor de linha de comando preferido. Aqui, usaremos o <code>nano</code>:</p>
<pre class="code-pre command prefixed"><code><ul class="prefixed"><li class="line" prefix="$">sudo nano /etc/nginx/sites-available/<span class="highlight">your_domain</span>
</li></ul></code></pre>
<p>Isso criará um novo arquivo em branco. Cole nele a seguinte configuração:</p>
<div class="code-label " title="/etc/nginx/sites-available/your_domain">/etc/nginx/sites-available/your_domain</div><pre class="code-pre "><code>server {
    listen 80;
    server_name <span class="highlight">your_domain</span> www.<span class="highlight">your_domain</span>;
    root /var/www/<span class="highlight">your_domain</span>;

    index index.html index.htm index.php;

    location / {
        try_files $uri $uri/ =404;
    }

    location ~ \.php$ {
        include snippets/fastcgi-php.conf;
        fastcgi_pass unix:/var/run/php/php7.4-fpm.sock;
     }

    location ~ /\.ht {
        deny all;
    }

}


</code></pre>
<p>Aqui está o que cada um desses blocos de localização e diretrizes fazem:</p>

<ul>
<li><code>listen</code> — Define em qual porta o Nginx irá escutar. Neste caso, ele irá escutar na porta <code>80</code>, a porta padrão para o HTTP.</li>
<li><code>root</code> — Define o document root onde os arquivos servidos por este site são armazenados.</li>
<li><code>index</code> — Define em que ordem o Nginx irá priorizar os arquivos de index para este site. É uma prática comum listar arquivos <code>index.html</code> com uma precedência superior aos arquivos <code>index.php</code> para permitir uma configuração rápida de uma página inicial de manutenção em aplicações PHP. Você pode ajustar essas configurações para melhor se adaptar às necessidades da sua aplicação.</li>
<li><code>server_name</code> — Define para quais nomes de domínio e/ou endereços IP este bloco de servidor deve responder. <strong>Aponte esta diretiva para o nome de domínio do seu servidor ou endereço IP público.</strong></li>
<li><code>location/</code> — O primeiro bloco de localização inclui uma diretiva <code>try_files</code>, que verifica a existência de arquivos ou diretórios que correspondam a uma requisição de URI. Se o Nginx não puder encontrar o recurso apropriado, ele irá retornar um erro 404.</li>
<li><code>location ~ \.php$</code> — Este bloco de localização lida com o processamento PHP real, apontando o Nginx para o arquivo de configuração <code>fastcgi-php.conf</code> e o arquivo <code>php7.4-fpm.sock</code>, que declara qual soquete está associado ao <code>php-fpm</code>.</li>
<li><code>location ~ /\.ht</code> — O último bloco de localização lida com os arquivos <code>.htaccess</code>, que o Nginx não processa. Ao adicionar a diretiva <code>deny all</code>, se acontecer de algum arquivo <code>.htaccess</code> ser encontrado no caminho do document root, ele não será apresentado aos visitantes.</li>
</ul>

<p>Quando terminar de editar, salve e feche o arquivo. Se você estiver usando o <code>nano</code>, você pode fazer isso digitando <code>CTRL+X</code> e, depois, <code>y</code> e <code>ENTER</code> para confirmar.</p>

<p>Ative sua configuração vinculando ao arquivo de configuração no diretório <code>sites-enabled</code> do Nginx:</p>
<pre class="code-pre command prefixed"><code><ul class="prefixed"><li class="line" prefix="$">sudo ln -s /etc/nginx/sites-available/<span class="highlight">your_domain</span> /etc/nginx/sites-enabled/
</li></ul></code></pre>
<p>Isso dirá ao Nginx para usar a configuração da próxima vez que ela for recarregada. Teste a configuração para conferir erros de sintaxe digitando:</p>
<pre class="code-pre command prefixed"><code><ul class="prefixed"><li class="line" prefix="$">sudo nginx -t
</li></ul></code></pre>
<p>Se algum erro for reportado, volte para seu arquivo de configuração para revisar seu conteúdo antes de continuar.</p>

<p>Quando estiver pronto, recarregue o Nginx para aplicar as alterações:</p>
<pre class="code-pre command prefixed"><code><ul class="prefixed"><li class="line" prefix="$">sudo systemctl reload nginx
</li></ul></code></pre>
<p>Agora, seu novo site está ativo, mas o web root <code>/var/www/<span class="highlight">your_domain</span></code> ainda está vazio. Crie um arquivo <code>index.html</code> naquele local para que possamos testar se o seu novo bloco de servidor funciona conforme esperado:</p>
<pre class="code-pre command prefixed"><code><ul class="prefixed"><li class="line" prefix="$">nano /var/www/<span class="highlight">your_domain</span>/index.html
</li></ul></code></pre>
<p>Inclua o conteúdo a seguir neste arquivo:</p>
<div class="code-label " title="/var/www/your_domain/index.html">/var/www/your_domain/index.html</div><pre class="code-pre "><code>&lt;html&gt;
  &lt;head&gt;
    &lt;title&gt;<span class="highlight">your_domain</span> website&lt;/title&gt;
  &lt;/head&gt;
  &lt;body&gt;
    &lt;h1&gt;Hello World!&lt;/h1&gt;

    &lt;p&gt;This is the landing page of &lt;strong&gt;<span class="highlight">your_domain</span>&lt;/strong&gt;.&lt;/p&gt;
  &lt;/body&gt;
&lt;/html&gt;
</code></pre>
<p>Agora, vá para seu navegador e acesse o nome de domínio ou endereço IP do seu servidor, conforme listado na diretiva <code>server_name</code> em seu arquivo de configuração de bloco de servidor:</p>
<pre class="code-pre "><code>http://<span class="highlight">server_domain_or_IP</span>
</code></pre>
<p>Você verá uma página como esta:</p>

<p><img src="https://assets.digitalocean.com/articles/lemp_ubuntu2004/landing_page.png" alt="Nginx server block"></p>

<p>Se você vir esta página, isso significa que seu bloco de servidor do Nginx está funcionando como esperado.</p>

<p>Você pode deixar esse arquivo funcionando como uma página principal temporária para sua aplicação até que você configure um arquivo <code>index.php</code> para substituí-lo. Assim que fizer isso, lembre-se de remover ou renomear o arquivo <code>index.html</code> de seu document root pois isso teria precedência sobre um arquivo <code>index.php</code> por padrão.</p>

<p>Sua pilha LEMP está totalmente configurada agora. No próximo passo, criaremos um script PHP para testar se o Nginx é, de fato, capaz de lidar com arquivos <code>.php</code> dentro do seu site recém configurado.</p>

<h2 id="passo-5-—-testando-o-php-com-o-nginx">Passo 5 — Testando o PHP com o Nginx</h2>

<p>Sua pilha LEMP agora deve estar configurada completamente. Você pode testá-la para validar que o Nginx pode manusear corretamente os arquivos <code>.php</code> para o seu processador PHP.</p>

<p>Você pode fazer isso criando um arquivo PHP de teste em seu document root. Abra um novo arquivo chamado <code>info.php</code> dentro do documento raiz no editor de texto:</p>
<pre class="code-pre command prefixed"><code><ul class="prefixed"><li class="line" prefix="$">nano /var/www/<span class="highlight">your_domain</span>/info.php
</li></ul></code></pre>
<p>Digite ou cole as seguintes linhas dentro do novo arquivo: Este é um código PHP válido que irá retornar informações sobre seu servidor:</p>
<div class="code-label " title="/var/www/your_domain/info.php">/var/www/your_domain/info.php</div><pre class="code-pre "><code>&lt;?php
phpinfo();
</code></pre>
<p>Quando você terminar, salve e feche o arquivo digitando <code>CTRL</code>+<code>X</code> e, depois, <code>y</code> e <code>ENTER</code> para confirmar.</p>

<p>Agora, você pode acessar essa página em seu navegador web visitando o nome de domínio ou o endereço IP público que você configurou em seu arquivo de configuração do Nginx, seguido por <code>/info.php</code>:</p>
<pre class="code-pre "><code>http://<span class="highlight">server_domain_or_IP</span>/info.php
</code></pre>
<p>Você verá uma página web contendo informações detalhadas sobre seu servidor:</p>

<p><img src="https://assets.digitalocean.com/articles/lemp_ubuntu2004/phpinfo.png" alt="PHPInfo Ubuntu 20.04"></p>

<p>Após verificar as informações relevantes sobre seu servidor PHP através dessa página, é melhor remover o arquivo que você criou, uma vez que ele contém informações sensíveis sobre seu ambiente PHP e seu servidor Ubuntu. Use o <code>rm</code> para remover esse arquivo:</p>
<pre class="code-pre command prefixed"><code><ul class="prefixed"><li class="line" prefix="$">sudo rm /var/www/<span class="highlight">your_domain</span>/info.php
</li></ul></code></pre>
<p>Você sempre pode gerar esse arquivo novamente se você precisar dele mais tarde.</p>

<h2 id="passo-6-—-testando-a-conexão-com-o-banco-de-dados-pelo-php-opcional">Passo 6 — Testando a Conexão com o Banco de Dados pelo PHP (Opcional)</h2>

<p>Se você quiser testar se o PHP é capaz de se conectar ao MySQL e executar consultas ao banco de dados, você pode criar uma tabela de teste, com dados fictícios, e fazer uma consulta em seu conteúdo, a partir de um script PHP. Antes que possamos fazer isso, precisamos criar um banco de dados de teste e um novo usuário do MySQL corretamente configurado para acessá-lo.</p>

<p>No momento em que este artigo foi escrito, a biblioteca <code>mysqlnd</code> nativa do PHP para o MySQL <a href="https://www.php.net/manual/en/ref.pdo-mysql.php">não suporta</a> o <code>caching_sha2_authentication</code>, o método de autenticação padrão para o MySQL 8. Precisaremos criar um novo usuário com o método de autenticação <code>mysql_native_password</code> para conseguir se conectar ao banco de dados MySQL a partir do PHP.</p>

<p>Vamos criar um banco de dados chamado <strong>example_database</strong> e um usuário chamado <strong>example_user</strong>, mas você pode substituir esses nomes por valores diferentes.</p>

<p>Primeiro, conecte-se ao console do MySQL usando a conta <strong>root</strong>:</p>
<pre class="code-pre command prefixed"><code><ul class="prefixed"><li class="line" prefix="$">sudo mysql
</li></ul></code></pre>
<p>Para criar um novo banco de dados, execute o seguinte comando a partir do seu console do MySQL:</p>
<pre class="code-pre custom_prefix prefixed"><code><ul class="prefixed"><li class="line" prefix="mysql&gt;">CREATE DATABASE <span class="highlight">example_database</span>;
</li></ul></code></pre>
<p>Agora, crie um usuário e lhe conceda privilégios completos sobre o banco de dados personalizado que acabou de criar.</p>

<p>O comando a seguir cria um novo usuário chamado <code><span class="highlight">example_user</span></code> usando o <code>mysql_native_password</code> como o método de autenticação padrão. Vamos definir a senha do usuário como <code><span class="highlight">password</span></code>, mas você deve substituir esse valor por uma senha segura de sua própria escolha:</p>
<pre class="code-pre custom_prefix prefixed"><code><ul class="prefixed"><li class="line" prefix="mysql&gt;">CREATE USER '<span class="highlight">example_user</span>'@'%' IDENTIFIED WITH mysql_native_password BY '<span class="highlight">password</span>';
</li></ul></code></pre>
<p>Agora, precisamos dar a este usuário permissão para o banco de dados <code>example_database</code>:</p>
<pre class="code-pre custom_prefix prefixed"><code><ul class="prefixed"><li class="line" prefix="mysql&gt;">GRANT ALL ON example_database.* TO 'example_user'@'%';
</li></ul></code></pre>
<p>Isso dará ao usuário <strong>example_user</strong> privilégios totais sobre o banco de dados <strong>example_database</strong>, ao mesmo tempo que impedirá que esse usuário crie ou altere outros bancos de dados no seu servidor.</p>

<p>Agora, saia do shell do MySQL com:</p>
<pre class="code-pre custom_prefix prefixed"><code><ul class="prefixed"><li class="line" prefix="mysql&gt;">exit
</li></ul></code></pre>
<p>Você pode testar se o novo usuário tem as permissões adequadas fazendo login no console MySQL novamente, desta vez usando as credenciais de usuário personalizadas:</p>
<pre class="code-pre command prefixed"><code><ul class="prefixed"><li class="line" prefix="$">mysql -u <span class="highlight">example_user</span> -p
</li></ul></code></pre>
<p>Note a flag <code>-p</code> neste comando, a qual irá solicitar a senha utilizada ao criar o usuário <strong>example_user</strong>. Após fazer login no console do MySQL, confirme se você tem acesso ao banco de dados <strong>example_database</strong>:</p>
<pre class="code-pre custom_prefix prefixed"><code><ul class="prefixed"><li class="line" prefix="mysql&gt;">SHOW DATABASES;
</li></ul></code></pre>
<p>Isso gerará o seguinte resultado:</p>
<pre class="code-pre "><code><div class="secondary-code-label " title="Output">Output</div>+--------------------+
| Database           |
+--------------------+
| <span class="highlight">example_database</span>   |
| information_schema |
+--------------------+
2 rows in set (0.000 sec)
</code></pre>
<p>Em seguida, criaremos uma tabela de teste chamada <strong>todo_list</strong>. A partir do console do MySQL, execute a seguinte instrução:</p>
<pre class="code-pre custom_prefix prefixed"><code><ul class="prefixed"><li class="line" prefix="mysql&gt;">CREATE TABLE <span class="highlight">example_database</span>.<span class="highlight">todo_list</span> (
</li><li class="line" prefix="mysql&gt;">    item_id INT AUTO_INCREMENT,
</li><li class="line" prefix="mysql&gt;">    content VARCHAR(255),
</li><li class="line" prefix="mysql&gt;">    PRIMARY KEY(item_id)
</li><li class="line" prefix="mysql&gt;">);
</li></ul></code></pre>
<p>Insira algumas linhas de conteúdo na tabela de teste. Talvez queira repetir o próximo comando algumas vezes, usando valores diferentes:</p>
<pre class="code-pre custom_prefix prefixed"><code><ul class="prefixed"><li class="line" prefix="mysql&gt;">INSERT INTO <span class="highlight">example_database</span>.<span class="highlight">todo_list</span> (content) VALUES ("<span class="highlight">My first important item</span>");
</li></ul></code></pre>
<p>Para confirmar se os dados foram salvos com sucesso em sua tabela, execute:</p>
<pre class="code-pre custom_prefix prefixed"><code><ul class="prefixed"><li class="line" prefix="mysql&gt;">SELECT * FROM <span class="highlight">example_database</span>.<span class="highlight">todo_list</span>;
</li></ul></code></pre>
<p>Você verá o seguinte resultado:</p>
<pre class="code-pre "><code><div class="secondary-code-label " title="Output">Output</div>+---------+--------------------------+
| item_id | content                  |
+---------+--------------------------+
|       1 | My first important item  |
|       2 | My second important item |
|       3 | My third important item  |
|       4 | and this one more thing  |
+---------+--------------------------+
4 rows in set (0.000 sec)

</code></pre>
<p>Após confirmar que você tem dados válidos em sua tabela de teste, saia do console do MySQL:</p>
<pre class="code-pre custom_prefix prefixed"><code><ul class="prefixed"><li class="line" prefix="mysql&gt;">exit
</li></ul></code></pre>
<p>Agora, você pode criar o script PHP que se conectará ao MySQL e irá consultar seu conteúdo. Crie um arquivo do PHP no seu diretório raiz da Web personalizado, usando seu editor preferido. Usaremos o <code>nano</code> para isso:</p>
<pre class="code-pre command prefixed"><code><ul class="prefixed"><li class="line" prefix="$">nano /var/www/<span class="highlight">your_domain</span>/<span class="highlight">todo_list.php</span>
</li></ul></code></pre>
<p>O script PHP a seguir se conecta ao banco de dados MySQL e consulta o conteúdo da tabela <strong>todo_list</strong>, mostrando os resultados em uma lista. Se houver um problema com a conexão do banco de dados, ele irá gerar uma exceção. Copie este conteúdo para seu script <code>todo_list.php</code>:</p>
<div class="code-label " title="/var/www/your_domain/todo_list.php">/var/www/your_domain/todo_list.php</div><pre class="code-pre "><code class="code-highlight language-php">&lt;?php
$user = "<span class="highlight">example_user</span>";
$password = "<span class="highlight">password</span>";
$database = "<span class="highlight">example_database</span>";
$table = "<span class="highlight">todo_list</span>";

try {
  $db = new PDO("mysql:host=localhost;dbname=$database", $user, $password);
  echo "&lt;h2&gt;TODO&lt;/h2&gt;&lt;ol&gt;";
  foreach($db-&gt;query("SELECT content FROM $table") as $row) {
    echo "&lt;li&gt;" . $row['content'] . "&lt;/li&gt;";
  }
  echo "&lt;/ol&gt;";
} catch (PDOException $e) {
    print "Error!: " . $e-&gt;getMessage() . "&lt;br/&gt;";
    die();
}
</code></pre>
<p>Salve e feche o arquivo quando terminar de editar.</p>

<p>Agora, você pode acessar esta página em seu navegador web visitando o nome de domínio ou o endereço IP público para seu site, seguido de <code>/todo_list.php</code>:</p>
<pre class="code-pre "><code>http://<span class="highlight">server_domain_or_IP</span>/todo_list.php
</code></pre>
<p>Você deve ver uma página como esta, mostrando o conteúdo que você inseriu em sua tabela de teste:</p>

<p><img src="https://assets.digitalocean.com/articles/lemp_debian10/todo_list.png" alt="Example PHP todo list​​​​​"></p>

<p>Isso significa que seu ambiente PHP está pronto para se conectar e interagir com seu servidor MySQL.</p>

<h2 id="conclusão">Conclusão</h2>

<p>Neste guia, construímos uma base flexível para servir sites e aplicações PHP aos seus visitantes, usando o Nginx como servidor web e o MySQL como sistema de banco de dados.</p>

<p>Há um número de passos que você pode tomar a partir daqui. Por exemplo, certifique-se de que as conexões para seu servidor estejam seguras. Para isso, você pode <a href="https://www.digitalocean.com/community/tutorials/how-to-secure-nginx-with-let-s-encrypt-on-ubuntu-20-04">proteger sua instalação Nginx com o Let&rsquo;s Encrypt</a>. Ao seguir este guia, você receberá um certificado TLS/SSL gratuito para seu servidor, permitindo que apresente conteúdo em HTTPS.</p>

 </div>

</div>

<div class="tutorial-footer">
  <div class='tutorial-footer-details'>


      <div class="tfb--container">
  <div class="tfb--content">
    <div class="tfb--undo tfb--hide">
      <span class="icon icon-helpfulness-upvoted"></span>
      <span class="tfb--question">Você classificou esta tradução como útil.</span>
      <button name="button" type="submit" class="tfb--button-down tfb--thumb-down-js">Undo</button>
    </div>

    <div class="tfb--flagging-undo tfb--hide">
      <span class="icon icon-helpfulness-flag"></span>
      <span class="tfb--question">Você marcou esta tradução.</span>
      <button name="button" type="submit" class="tfb--button-down tfb--unflagging-js">Undo</button>
    </div>

    <div class="tfb--do">
      <span class="tfb--question">Como você avalia a qualidade da tradução?</span>
      <button name="button" type="submit" class="tfb--button tfb--thumb-up-js" data-translation-upvote-id="5625" data-translation-upvote-type="Tutorial" role="button" aria-label="Good">👍</button>
      <button name="button" type="submit" class="tfb--button tfb--flagging-js" data-translation-flag-id="5625" data-translation-flag-type="Tutorial" role="button" aria-label="Bad">👎</button>
    </div>
  </div>
</div>




      
<div class="hsb--container">
  <div class="hsb--content">
    <div class="hsb--content-main">
      <div class="hsb--undo hsb--hide">
        <span class="icon icon-helpfulness-upvoted"></span>
        <span class="hsb--question">You rated this helpful.</span>
        <button name="button" type="submit" class="hsb--button-down hsb--vote-down-js" data-upvotable-type="Tutorial">Undo</button>
      </div>

      <div class="hsb--flagging-undo hsb--hide">
        <span class="icon icon-helpfulness-flag"></span>
        <span class="hsb--question">You reported this tutorial.</span>
        <button name="button" type="submit" class="hsb--button-down hsb--unflagging-js">Undo</button>
      </div>

      <div class="hsb--do">
        <span class="hsb--question">Was this helpful?</span>
        <button name="button" type="submit" class="hsb--button hsb--vote-up-js" id="submit-upvote-report" data-upvotable-id="5625" data-upvotable-type="Tutorial">Yes</button>
        <button name="button" type="submit" class="hsb--button hsb--flagging-js" data-url="/community/tutorials/how-to-install-linux-nginx-mysql-php-lemp-stack-on-ubuntu-20-04-pt/flag" data-flaggable-id="5625" data-flag-type="no">No</button>
      </div>

      <div class="hsb--social-and-comments">
        <div class="hsb--social-sharing">
          <a target="_blank" class="share-popup" href="http://twitter.com/share?text=Como%20Instalar%20Linux%2C%20Nginx%2C%20MySQL%2C%20PHP%20%28pilha%20LEMP%29%20no%20Ubuntu%2020.04&amp;url=https://www.digitalocean.com/community/tutorials/how-to-install-linux-nginx-mysql-php-lemp-stack-on-ubuntu-20-04-pt?utm_content=how-to-install-linux-nginx-mysql-php-lemp-stack-on-ubuntu-20-04-pt&amp;utm_medium=community&amp;utm_source=twshare">
            <span class="icon icon-helpfulness-twitter"></span>
</a>
          <a target="_blank" class="share-popup" href="https://www.facebook.com/sharer/sharer.php?u=https://www.digitalocean.com/community/tutorials/how-to-install-linux-nginx-mysql-php-lemp-stack-on-ubuntu-20-04-pt?utm_content=how-to-install-linux-nginx-mysql-php-lemp-stack-on-ubuntu-20-04-pt&amp;utm_medium=community&amp;utm_source=fbshare">
            <span class="icon icon-helpfulness-facebook"></span>
</a>
          <a target="_blank" class="share-popup" href="https://news.ycombinator.com/submitlink?t=Como%20Instalar%20Linux%2C%20Nginx%2C%20MySQL%2C%20PHP%20%28pilha%20LEMP%29%20no%20Ubuntu%2020.04&amp;u=https://www.digitalocean.com/community/tutorials/how-to-install-linux-nginx-mysql-php-lemp-stack-on-ubuntu-20-04-pt?utm_content=how-to-install-linux-nginx-mysql-php-lemp-stack-on-ubuntu-20-04-pt&amp;utm_medium=community&amp;utm_source=hnshare">
            <span class="icon icon-helpfulness-hacker-news"></span>
</a>        </div>

        <div class="hsb--comment">
          <span class="icon icon-helpfulness-comment"></span>
          <strong class="amount">0</strong>
        </div>
      </div>
    </div>

  </div>

  <a class="hsb--flagging-js" data-url="/community/tutorials/how-to-install-linux-nginx-mysql-php-lemp-stack-on-ubuntu-20-04-pt/flag" data-flaggable-id="5625" data-flag-type="report" href="javascript:void(0);">Report an issue</a>
</div>




    <div class="component-collaborators-container-footer">
  <div class="component-collaborators-content">
    <div class="heading">About the authors</div>

      <div class="author">
          <a href="/community/users/erikaheidi">
            <div class="avatar">
              <div class="mod-avatar mod-avatar-large"><img class="avatar avatar-large" src="https://community-cdn-digitalocean-com.global.ssl.fastly.net/assets/users/avatars/large/4c3251574011991e1d7c79990a16a45759a2ecdd.jpeg?1582714750" /><span class="mod-star" title="MOD" data-toggle="tooltip" data-container="body"><span class="mod-star-icon"></span></span></div>
            </div>
</a>          <div class="byline-info">
            <div class="names">
              <a href="/community/users/erikaheidi">
                Erika Heidi
</a>            </div>
              <p>I like to write and build stuff. Passionate about community and open source &lt;3</p>
          </div>
      </div>

      <div class="editor-translator">
      </div>
  </div>
</div>


</div>



  <div class='related-content'>
    <div class='section-content panels'>
      <h2>Related</h2>

      <ul>
        <li title="Como configurar um aplicativo Node.js para produção no Ubuntu 20.04">
  <a class="panel" href="/community/tutorials/how-to-set-up-a-node-js-application-for-production-on-ubuntu-20-04-pt">
    <h6>Tutorial</h6>
    <div class="panel-data">
      <h5>Como configurar um aplicativo Node.js para produção no Ubuntu 20.04</h5>
      <p data-clamp>O Node.js é um ambiente de execução de código aberto do JavaScript para construção de aplicativos de rede e do servidor. A plataforma executa nos sistemas operacionais Linux, macOS, FreeBSD e Windows. Embora você possa executar aplicativos Node.js na…</p>
    </div>
  </a>
</li>
<li title="Como instalar o WordPress no Ubuntu 20.04 com uma pilha LAMP">
  <a class="panel" href="/community/tutorials/how-to-install-wordpress-on-ubuntu-20-04-with-a-lamp-stack-pt">
    <h6>Tutorial</h6>
    <div class="panel-data">
      <h5>Como instalar o WordPress no Ubuntu 20.04 com uma pilha LAMP</h5>
      <p data-clamp>Hoje, o WordPress é uma ferramenta de código aberto extremamente popular para fazer sites e blogs na internet. Usado por 63% de todos os sites que usam um sistema de gerenciamento de conteúdo (CMS), os sites com WordPress representam 36% de todos os sites que estão atualmente…</p>
    </div>
  </a>
</li>
<li title="Como instalar e configurar o Zabbix para monitorar servidores remotos com segurança no Ubuntu 20.04">
  <a class="panel" href="/community/tutorials/how-to-install-and-configure-zabbix-to-securely-monitor-remote-servers-on-ubuntu-20-04-pt">
    <h6>Tutorial</h6>
    <div class="panel-data">
      <h5>Como instalar e configurar o Zabbix para monitorar servidores remotos com segurança no Ubuntu 20.04</h5>
      <p data-clamp>O autor selecionou o Computer History Museum para receber uma doação como parte do programa Write for DOnations. O Zabbix é um software de monitoramento de código aberto para redes e…</p>
    </div>
  </a>
</li>
<li title="Como instalar o Jenkins no Ubuntu 20.04">
  <a class="panel" href="/community/tutorials/how-to-install-jenkins-on-ubuntu-20-04-pt">
    <h6>Tutorial</h6>
    <div class="panel-data">
      <h5>Como instalar o Jenkins no Ubuntu 20.04</h5>
      <p data-clamp>Quando confrontado com tarefas técnicas repetitivas, encontrar soluções de automação que funcionem pode ser uma tarefa árdua. Com o Jenkins, um servidor de automação de código aberto, você pode gerenciar eficientemente tarefas que vão desde a compilação até…</p>
    </div>
  </a>
</li>

      </ul>
    </div>
  </div>



  <div class='looking-for-an-answer'>
  <div class='section-content'>
    <h4>Still looking for an answer?</h4>
    <div class="lfa--actions">
      <a href="/community/questions/new?tags=LEMP%2CNginx%2CPHP%2CUbuntu%2CUbuntu+20.04"
         class="lfa--action-box">
        <span class="icon icon-look-for-answer-question"></span>
        Ask a question
      </a>
      <a href="javascript:void(0)" class="lfa--action-box use-universal-search-js">
        <span class="icon icon-look-for-answer-search-thin"></span>
        Search for more help
      </a>
    </div>
  </div>
</div>

</div>


<div class="tabs">
  <ul>
    <li class="is-active" >
      <a data-js="related-comments">Comments</a>
    </li>
    <li class="not-active">
      <a data-js="follow-up-questions">Follow-Up Questions</a>
    </li>
  </ul>
</div>

<div id="comments-tab" style="display:block">
  <div class="content-comments">
  <div class="section-content">
    <div class="tutorial commentable" id="tutorial_5625">

  <div class="comments-header">
    <h4 class="comments-count">
        <span>0 Comments</span>
    </h4>
  </div>

    <div class="response response-form no-avatar no-comments">
  <div class="js-display-on-error flash error hidden"></div>


  <form class="content-form disabled-form" id="new_comment" action="/community/tutorials/how-to-install-linux-nginx-mysql-php-lemp-stack-on-ubuntu-20-04-pt/comments" accept-charset="UTF-8" data-remote="true" method="post"><input name="utf8" type="hidden" value="&#x2713;" />

    <textarea name="comment[content]" id="comment_content" placeholder="Leave a comment..." class="js-comment-content tutorial-comment-field" data-markdown="true">
</textarea>

      <div class="log-in-notice "><a href="/community/auth/digitalocean">Sign In to Comment</a></div>

    <div class='clearfix'></div>
</form>
</div>


  <div class="comments">
    <ul class="response-list">
    </ul>

  </div>

  <div class='load-more-container'></div>
</div>


  </div>
</div>

</div>

<div class="creative-commons">
  <a class="creative-commons-image" href="https://creativecommons.org/licenses/by-nc-sa/4.0/"><img rel="license" alt="Creative Commons License" src="/assets/community/creativecommons-027bb7f065acf05ba3c0f84a040d2da641648afc81daa6ff5570301d4998bbb6.png" /></a>
  <div class="license-text">This work is licensed under a <a rel="license" href="https://creativecommons.org/licenses/by-nc-sa/4.0/">Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International License</a>.</div>
</div>









        <div class="clearfix"></div>
      </div>

      
      <footer>
        <section>
            <a href="https://www.digitalocean.com/community/pages/write-for-digitalocean" class="panel_with_image">
            <div class="photo_wrap">
              <img class="photo" src="https://images.prismic.io/digitalocean/70910e9fdeb57be46aaa209ce8d9b4dc8e117fab_w4do2.jpg?auto=compress,format" alt="">
            </div>
            <span class="heading">Become a contributor</span>
            <p>
                You get paid; we donate to tech nonprofits.
            </p>
          </a>
            <a href="https://www.digitalocean.com/community/newsletter" class="panel_with_image">
            <div class="photo_wrap">
              <img class="photo" src="https://images.prismic.io/digitalocean/ca12c951cc76f33037f3384bba9942545d160d82_iaan_illo.jpg?auto=compress,format" alt="">
            </div>
            <span class="heading">Get our biweekly newsletter</span>
            <p>
                Sign up for Infrastructure as a Newsletter.
            </p>
          </a>
            <a href="https://www.digitalocean.com/community/pages/hub-for-good" class="panel_with_image">
            <div class="photo_wrap">
              <img class="photo" src="https://images.prismic.io/digitalocean/21ab4275-bcf3-42ac-b148-6f81d516ca1d_Twitter_graphic.png?auto=compress,format&amp;rect=0,61,1024,387&amp;w=370&amp;h=140" alt="">
            </div>
            <span class="heading">Hub for Good</span>
            <p>
                Working on improving health and education, reducing inequality, and spurring economic growth? We&#39;d like to help.
            </p>
          </a>
      </section>
      <section class="slim ">
        <span class="heading">Featured on Community</span>
            <a href="https://www.digitalocean.com/community/curriculums/kubernetes-for-full-stack-developers">Kubernetes Course</a>
            <a href="https://www.digitalocean.com/community/tutorial_series/how-to-code-in-python-3">Learn Python 3</a>
            <a href="https://www.digitalocean.com/community/tutorials/machine-learning-projects-python-a-digitalocean-ebook">Machine Learning in Python</a>
            <a href="https://www.digitalocean.com/community/tutorials/how-to-write-your-first-program-in-go">Getting started with Go</a>
            <a href="https://www.digitalocean.com/community/tutorials/an-introduction-to-kubernetes">Intro to Kubernetes</a>
        <hr>
        <span class="heading">DigitalOcean Products</span>
            <a href="https://www.digitalocean.com/products/droplets/">Droplets</a>
            <a href="https://www.digitalocean.com/products/managed-databases/">Managed Databases</a>
            <a href="https://www.digitalocean.com/products/kubernetes/">Managed Kubernetes</a>
            <a href="https://www.digitalocean.com/products/spaces/">Spaces Object Storage</a>
            <a href="https://marketplace.digitalocean.com/">Marketplace</a>
      </section>
        <section class="product">
          <a class="copy" href="/products">
            <h3>Welcome to the developer cloud</h3>
            <p>DigitalOcean makes it simple to launch in the cloud and scale up as you grow – whether you’re running one virtual machine or ten thousand.</p>
            <span class="link_text">Learn More</span>
          </a>
          <div class="feature">
            <a class="img_wrap" href="/products">
              <img class="photo" src="https://images.prismic.io/digitalocean/95c1215227aa7f39f2bd23076de28feb969741c7_cloud.digitalocean.com_projects_63f9252f-652b-4645-9c0c-bee96f2bc503_resources_ic0ce81-2.png?auto=compress,format" alt="DigitalOcean Cloud Control Panel">
            </a>
          </div>
        </section>
        <section class="dark">
          <div class="vlist grow">
            <a href="https://www.digitalocean.com">
              <svg xmlns="http://www.w3.org/2000/svg" width="50" height="50" viewBox="0 0 50 50">
                <title>DigitalOcean Homepage</title>
                <g fill="#0080FF" fill-rule="evenodd">
                  <path
                    d="M24.9153 50v-9.661c10.226 0 18.1638-10.1413 14.2372-20.904-1.4406-3.983-4.6327-7.1751-8.6158-8.6158C19.774 6.921 9.6327 14.8305 9.6327 25.0565H0C0 8.7571 15.7627-3.9548 32.8531 1.3842c7.4576 2.3446 13.418 8.2768 15.7345 15.7344C53.9266 34.2373 41.2429 50 24.9153 50">
                  </path>
                  <path
                    d="M15.339 40.3672h9.6045v-9.6045H15.339zM7.9379 47.7684h7.401v-7.4012H7.938zM1.7514 40.3672H7.938v-6.1864H1.7514z">
                  </path>
                </g>
              </svg>
            </a>
            <br><br>
            © <script type="text/javascript">
              document.write(new Date().getFullYear());

            </script> DigitalOcean, LLC. All rights reserved.
          </div>

              <div class="vlist">
                <span class="heading">Company</span>
                <ul>
                    <li>
                      <a href="https://www.digitalocean.com/about/">About</a>
                    </li>
                    <li>
                      <a href="https://www.digitalocean.com/about/leadership/">Leadership</a>
                    </li>
                    <li>
                      <a href="https://www.digitalocean.com/blog/">Blog</a>
                    </li>
                    <li>
                      <a href="https://www.digitalocean.com/careers/">Careers</a>
                    </li>
                    <li>
                      <a href="https://www.digitalocean.com/partners/">Partners</a>
                    </li>
                    <li>
                      <a href="https://www.digitalocean.com/referral-program/">Referral Program</a>
                    </li>
                    <li>
                      <a href="https://www.digitalocean.com/press/">Press</a>
                    </li>
                    <li>
                      <a href="https://www.digitalocean.com/legal/">Legal</a>
                    </li>
                    <li>
                      <a href="https://www.digitalocean.com/trust/">Security &amp; Trust Center</a>
                    </li>
                </ul>
              </div>
              <div class="vlist">
                <span class="heading">Products</span>
                <ul>
                    <li>
                      <a href="https://www.digitalocean.com/pricing/">Pricing</a>
                    </li>
                    <li>
                      <a href="https://www.digitalocean.com/products/">Products Overview</a>
                    </li>
                    <li>
                      <a href="https://www.digitalocean.com/products/droplets/">Droplets</a>
                    </li>
                    <li>
                      <a href="https://www.digitalocean.com/products/kubernetes/">Kubernetes</a>
                    </li>
                    <li>
                      <a href="https://www.digitalocean.com/products/managed-databases/">Managed Databases</a>
                    </li>
                    <li>
                      <a href="https://www.digitalocean.com/products/spaces/">Spaces</a>
                    </li>
                    <li>
                      <a href="https://www.digitalocean.com/products/marketplace/">Marketplace</a>
                    </li>
                    <li>
                      <a href="https://www.digitalocean.com/products/load-balancer/">Load Balancers</a>
                    </li>
                    <li>
                      <a href="https://www.digitalocean.com/products/block-storage/">Block Storage</a>
                    </li>
                    <li>
                      <a href="https://developers.digitalocean.com/documentation/">API Documentation</a>
                    </li>
                    <li>
                      <a href="https://www.digitalocean.com/docs">Documentation</a>
                    </li>
                    <li>
                      <a href="https://www.digitalocean.com/docs/release-notes/">Release Notes</a>
                    </li>
                </ul>
              </div>
              <div class="vlist">
                <span class="heading">Community</span>
                <ul>
                    <li>
                      <a href="https://www.digitalocean.com/community/tutorials">Tutorials</a>
                    </li>
                    <li>
                      <a href="https://www.digitalocean.com/community/questions">Q&amp;A</a>
                    </li>
                    <li>
                      <a href="https://www.digitalocean.com/community/tools">Tools and Integrations</a>
                    </li>
                    <li>
                      <a href="https://www.digitalocean.com/community/tags">Tags</a>
                    </li>
                    <li>
                      <a href="https://ideas.digitalocean.com/">Product Ideas</a>
                    </li>
                    <li>
                      <a href="https://www.digitalocean.com/write-for-donations/">Write for DigitalOcean</a>
                    </li>
                    <li>
                      <a href="https://www.digitalocean.com/droplets-for-demos/">Presentation Grants</a>
                    </li>
                    <li>
                      <a href="https://www.digitalocean.com/hatch/">Hatch Startup Program</a>
                    </li>
                    <li>
                      <a href="http://store.digitalocean.com/">Shop Swag</a>
                    </li>
                    <li>
                      <a href="https://www.digitalocean.com/research/">Research Program</a>
                    </li>
                    <li>
                      <a href="https://www.digitalocean.com/open-source/">Open Source</a>
                    </li>
                    <li>
                      <a href="https://www.digitalocean.com/community/pages/code-of-conduct">Code of Conduct</a>
                    </li>
                </ul>
              </div>
              <div class="vlist">
                <span class="heading">Contact</span>
                <ul>
                    <li>
                      <a href="https://www.digitalocean.com/support/">Get Support</a>
                    </li>
                    <li>
                      <a href="https://www.digitalocean.com/docs/getting-started/faq/">Trouble Signing In?</a>
                    </li>
                    <li>
                      <a href="https://www.digitalocean.com/company/contact/sales/">Sales</a>
                    </li>
                    <li>
                      <a href="https://www.digitalocean.com/company/contact/#abuse">Report Abuse</a>
                    </li>
                    <li>
                      <a href="https://status.digitalocean.com/">System Status</a>
                    </li>
                </ul>
              </div>
        </section>
      </footer>


      <div id='sign-in-modal' class='modal fade mini-modal' style="display: none;">
  <div class='modal-dialog'>
    <div class='modal-content'>
      <div class='modal-header'>
        <h1>Almost there!</h1>
        <a class='close-button' data-dismiss='modal' aria-label="close"  href=''><span class='icon icon-close-light'></span></a>
      </div>
      <div class='modal-body'>
        <div class='sign-in-message'>Sign in to your Community account or create a new one below.</div>
        <div class='sign-in-modal-actions'>
          <a class="sign-in-link button blue-button" data-default-url="/community/auth/digitalocean" href="/community/auth/digitalocean">Sign In</a>
          <a class="sign-up-link button blue-button" data-default-url="/community/auth/digitalocean?display=sessionless+register" href="/community/auth/digitalocean?display=sessionless+register">Sign Up</a>
        </div>
      </div>
    </div>
  </div>
</div>


      <script>
    $(function() {
      window.initTranslationFeedbackActions(5625);
    });
  </script>
  <script>
    $(function() {
      window.initHelpfulnessActions(5625, '/community/tutorials/how-to-install-linux-nginx-mysql-php-lemp-stack-on-ubuntu-20-04-pt/flag');
    });
  </script>

  <script>
    $(function() {
      if (!!window.init_sharing) {
        window.init_sharing();
      }
      new window.NewsletterSignup();
      new window.GrowableMarkdown({ target: '[data-growable-markdown]' });

      createTranslationSelection({
        $translation_language: $('#translation_language'),
      });
    });
  </script>
  <script type="application/ld+json">
  {"@context":"http://schema.org","@type":"Article","name":"Como Instalar Linux, Nginx, MySQL, PHP (pilha LEMP) no Ubuntu 20.04","headline":"Como Instalar Linux, Nginx, MySQL, PHP (pilha LEMP) no Ubuntu 20.04","alternativeHeadline":"Como Instalar Linux, Nginx, MySQL, PHP (pilha LEMP) no Ubuntu 20.04","description":"A pilha de software LEMP é um grupo de softwares que pode ser usado para exibir páginas e aplicativos Web dinâmicos escritos em PHP. Este é um acrônimo que descreve um sistema operacional Linux, com um servidor Web Nginx (se pronuncia “Engine-X). Os dados do backend são…","keywords":"LEMP,Nginx,PHP,DO-Writers,Ubuntu,Ubuntu 20.04","url":"https://www.digitalocean.com/community/tutorials/how-to-install-linux-nginx-mysql-php-lemp-stack-on-ubuntu-20-04-pt","mainEntityOfPage":{"@type":"WebPage","@id":"https://www.digitalocean.com/community/tutorials/how-to-install-linux-nginx-mysql-php-lemp-stack-on-ubuntu-20-04-pt"},"dateModified":"2020-05-15T13:45:19Z","inLanguage":"pt","accessMode":"textual","accessModeSufficient":"textual","isAccessibleForFree":true,"license":"https://creativecommons.org/licenses/by-nc-sa/4.0/","publishingPrinciples":"https://www.digitalocean.com/community/tutorials/technical-recommendations-and-best-practices-for-digitalocean-s-tutorials","author":[{"@type":"Person","name":"Erika Heidi","@id":"https://www.digitalocean.com/community/users/erikaheidi"}],"datePublished":"2020-05-15T13:45:19Z","image":{"@type":"ImageObject","url":"https://www.digitalocean.com/assets/community/illustrations/DigitalOcean_Community-e00e73a18df20667c3117725e727f3ade330204dff619ad8153050ded7341627.jpg","height":375,"width":750},"interactionStatistic":[{"@type":"InteractionCounter","interactionType":"http://schema.org/LikeAction","userInteractionCount":"1"},{"@type":"InteractionCounter","interactionType":"http://schema.org/CommentAction","userInteractionCount":"0"}],"sourceOrganization":{"@type":"Organization","name":"DigitalOcean Community","url":"https://www.digitalocean.com/community"},"publisher":{"@type":"Organization","name":"DigitalOcean","url":"https://www.digitalocean.com","logo":{"@type":"ImageObject","url":"https://assets.digitalocean.com/logos/DO_Logo_horizontal_blue.png","width":351,"height":60}}}
</script>

  <script type="text/javascript">
    $(function() {
      $('.use-universal-search-js').on('click', function () {
        $('#q').trigger('click');
      });
    });

    window.loadUniversalSearchScript( function () {
      var search = new UniversalSearch({
        element_id: 'q',
        search_on_slash: true,
        primary_list: ['quicknav', 'community_consolidated'],
        secondary_list: ['alldocs', 'marketplace'],
        algolia_app_id: "6ZHEUVKJ88",
        algolia_public_key: "c5470567eae7fa1177d43222e18ba086"
      });
      search.start();
    });
  </script>


      <script src="https://do-community.github.io/dns-tool-embed/bundle.js" type="text/javascript"></script>
      <script src="https://do-community.github.io/glob-tool-embed/bundle.js" type="text/javascript"></script>
  </body>
</html>








[Contribution guidelines for this project](docs/CONTRIBUTING.md)


Alguns comandos Git básicos são:
```
git status
git add
git commit
Git error
shibiu crazy
```

Alguns comandos Git básicos são:
```
git status
git add
git commit
```


Alguns comandos Git básicos são:
```
git status
git add
git commit
```

Alguns comandos Git básicos são:
```
git status
git add
git commit
```
