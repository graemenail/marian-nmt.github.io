---
layout: home
title: Home
permalink: /
---

<!--h2 class="title">Welcome to {{ site.title }}!</h2-->
<div class="intro">
  <p>
  <b>AmuNMT</b> is an efficient Neural Machine Translation framework written
  in pure C++ with minimal dependencies. 
  </p>

  <p>
  Main features:

  <ul>
    <li> Fast multi-gpu training and translation </li>
    <li> Compatible with Nematus and DL4MT </li>
    <li> Efficient pure C++ implementation </li>
    <li> Permissive open source license (MIT) </li>
    <li> <a href="{{ site.baseurl }}../features"> more details... </a> </li>
  </ul>
  </p>
  
  <br/>
  <div class="cta-container">
    <a class="btn btn-primary btn-cta" href=" {{ site.github }} " target="_blank">
      <i class="fa fa-github"></i>
      Download from GitHub
    </a>
  </div><!--//cta-container-->
</div><!--//intro-->

<div id="cards-wrapper" class="cards-wrapper row">

  {% for card in site.data.cards %}
  <div class="item item-{{ card.color }} col-md-4 col-sm-6 col-xs-6">
    <div class="item-inner">
      <div class="icon-holder">
        <span aria-hidden="true" class="icon fa {{ card.icon }}"></span>
      </div><!--//icon-holder-->
      <h3 class="title">{{ card.title }}</h3>
      <p class="intro">{{ card.intro }}</p>
      <a class="link" href="{{ card.link }}"><span></span></a>
    </div><!--//item-inner-->
  </div><!--//item-->
  {% endfor %}

</div><!--//cards-->

<!--div class="intro">
  <p>
  <a class="twitter-timeline" href="https://twitter.com/AmuNmt">Tweets</a> <script async src="//platform.twitter.com/widgets.js" charset="utf-8"></script>
  </p>
</div-->

<h4> Acknowledgements </h4>
<div class="intro">
  <p>
The development of AmuNMT received funding from the European Union's Horizon 2020 Research and Innovation Programme under grant agreements 688139 (<a href="http://www.summa-project.eu">SUMMA</a>); 2016-2019) and 645487 (<a href="http://www.modernmt.eu">Modern MT</a>); 2015-2017) and the Amazon Academic Research Awards program. 
  </p>
</div>