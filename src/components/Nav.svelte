<script>
	export let segment;
	import { animate } from "./../animate.js";
  let desc = false;
</script>





<style>
main {
    text-align: center;
    padding: 1em;
		font-size: 3.5em;
    margin: 0 auto;
		
  }
  nav {
    border-bottom: 1px solid rgba(255, 62, 0, 0.1);
    font-weight: 300;
    padding: 0 1em;
  }

  ul {
    margin: 0;
    padding: 0;
  }

  /* clearfix */
  ul::after {
    content: "";
    display: block;
    clear: both;
  }

  li {
    display: block;
    float: left;
  }

  [aria-current] {
    position: relative;
    display: inline-block;
  }

  [aria-current]::after {
    position: absolute;
    content: "";
    width: calc(100% - 1em);
    height: 2px;
    background-color: rgb(87, 218, 196);
    display: block;
    bottom: -1px;
  }

  a {
    text-decoration: none;
    padding: 1em 0.5em;
    font-size: 2em;
    display: block;
  }
</style>

<nav>
  <ul class="flex justify-center">
    <li>
      <a aria-current={segment === undefined ? 'page' : undefined} href=".">
        home
      </a>
    </li>
    <li>
      <a aria-current={segment === 'about' ? 'page' : undefined} href="about">
        about
      </a>
    </li>

    <!-- for the blog link, we're using rel=prefetch so that Sapper prefetches
		     the blog data when we hover over the link or tap it on a touchscreen -->
    <li>
      <a
        rel="prefetch"
        aria-current={segment === 'blog' ? 'page' : undefined}
        href="blog">
        blog
      </a>
    </li>
  </ul>
</nav>
<main 
  use:animate={{ type: 'from', duration: 1,y:100, ease: "bounce",opacity: 0,scale:0.5, onComplete: () => (desc = true) }}>
  <p class="text-secondary-600">Sapper >> TailWind >> Gsap !!!!!</p>
</main>