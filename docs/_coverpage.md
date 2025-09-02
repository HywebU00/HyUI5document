<!-- _coverpage.md -->

<!-- # HyUI <small>4.0</small> -->

<div class="info">
<div class="logo">
      <img src="logo.png" alt="" class="imgResponsive" />
    <span>5.0</span>
</div>

<h1>
  無障礙網頁 UI 框架
</h1>
<p >
  由 HTML5、CSS3 與 JavaScript <br>開發而成的無障礙網頁框架
</p>

<div class="btnList" >
<span >
  <a href="https://github.com/HywebU00/HyUI_v5/">GitHub</a>
</span>
<span >
  <a href="#?id=hyui-kit">Get Started</a>
</span>
</div>
</div>

<style>
  .info{
        margin: 0 0 10% 30%;
  }
  .logo{
    width: 360px;
    margin: 0 auto;
    position: relative;
  }
  .logo span{
    margin-right: 2em;
    text-align: end;
    position: absolute;
    top: 1.25em;
    color:#336699;
    right: 0;
  }
  
  section.cover a{
    border-radius: 2rem;
    
    /* border: 1px solid #0156a2; */
    /* color: #0156a2; */
    color:#fff;
    display: inline-block;
    font-size: 1.05rem;
    letter-spacing: .1rem;
    margin: 0.5rem 1rem;
    padding: 0.75em 2rem;
    text-decoration: none;
    transition: all .15s ease;
    width:250px;
    margin: 0.25em;
    background: rgb(0,93,157); /* Old browsers */
    background: -moz-linear-gradient(45deg,  rgba(0,93,157,1) 0%, rgba(152,209,167,1) 40%, rgba(0,152,255) 100%); /* FF3.6-15 */
    background: -webkit-linear-gradient(45deg,  rgba(0,93,157,1) 0%,rgba(152,209,167,1) 40%, rgba(0,152,255) 100%); /* Chrome10-25,Safari5.1-6 */
    background: linear-gradient(45deg,  rgba(0,93,157,1) 0%,rgba(152,209,167,1) 40%, rgba(0,152,255) 100%); /* W3C, IE10+, FF16+, Chrome26+, Opera12+, Safari7+ */
    filter: progid:DXImageTransform.Microsoft.gradient( startColorstr='#005d9d', endColorstr='#98d1a7',GradientType=1 ); /* IE6-9 fallback on horizontal gradient */

background-size: 300% 100%;
}
section.cover a:hover{
background-position: 100% 0;
moz-transition: all .4s ease-in-out;
-o-transition: all .4s ease-in-out;
-webkit-transition: all .4s ease-in-out;
transition: all .4s ease-in-out;

}
.btnList{
display:flex;
flex-wrap: wrap;
justify-content: center;
}
.btnList span{
width: 100%;
}
.cover.show{
background-repeat: no-repeat !important;
background-size:36% !important;
background-image: url(cover.png) !important;
background-position: left bottom !important;

}
@media screen and (max-width: 1440px){
.cover.show{
background-size:40% !important;
}
}
@media screen and (max-width: 1200px){
.cover.show{
background-size:50% !important;
}
}
@media screen and (max-width: 767px){
.cover.show{
background-image:none !important;
}
.cover.show:after{
background-position: center;
}
.info{
margin: 0 0 10% 0;
}
}
.cover.show:after{
content:'';
background-image: url(cover_bg.png) !important;

width: 100%;
position: absolute;
height: 100%;
z-index: -1;
    background-repeat: no-repeat;
    background-size: cover;
    background-position: right;

}
section.cover h1{
color:#336699;
font-size: 1.8em;
font-weight: 700;
margin:0.75em 0 0 0;

}
section.cover p {
color:#336699;
font-size: 1em;
margin-top: 0em;
margin-bottom:1.75em;
}
</style>
