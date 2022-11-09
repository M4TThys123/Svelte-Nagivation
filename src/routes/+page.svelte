<script>
  // 	let navWidth = 0;
  let navOpen = false;

  function handleNav() {
    navOpen = !navOpen;
    // 		navWidth === 0 ? navWidth = 40 : navWidth = 0;
  }

</script>

<nav class="sidenav" class:open={navOpen}>
  <button class="closebtn" on:click={handleNav}>&times;</button>
  <a href="/">Versie 1</a>
  <a href="/v2">Versie 2</a>
  <a href="/v3">Versie 3</a>
  <a href="/v4">Versie x</a>
  <a href="/v5">Versie x</a>
</nav>

<!-- Use to open the sidenav -->
<!-- 	<span on:click={handleNav}>open</span> -->

<!-- Use Menu Icon to open the sidenav -->
<button class="hamButton" class:pushMainToRight={navOpen} class:change={navOpen} on:click={handleNav}>
    <i class='bx bx-menu-alt-left'></i>
</button>

<!-- Add some margin-left to this div if you want the side nav to push page content to the right (not used if you only want the sidenav to sit on top of the page) -->
<div id="main" class:pushMainToRight={navOpen}>
  <h2>Dit is de eerste versie</h2>
  <p>
    This content will slide to the left if you add the class pushMain when
    navOpen evaluates to true in the parent DIV.
  </p>
</div>



<style>
  /* Hamburger Menu icon */
  .hamButton {
    position: absolute;
    left: 20px;
    display: inline-block;
    cursor: pointer;
    z-index: 2;
    font-size: 2em;
    transition: 0.3s;
  }

  /* The side navigation menu */
  .sidenav {
    height: 100%;
    width: 0; /* 0 width - change this with JavaScript */
    position: fixed;
    z-index: 1;
    top: 0;
    left: 0;
    background-color: #111;
    overflow-x: hidden; /* Disable horizontal scroll */
    padding-top: 60px;
    transition: 0.3s;
    transform: translate3d(-472px, 0, 0);
    width: 472px;
  }

  /* The navigation menu links */
  .sidenav a {
    padding: 8px 8px 8px 32px;
    text-decoration: none;
    font-size: 25px;
    color: #818181;
    display: block;
    transition: 0.3s;

  }

  /* When you mouse over the navigation links, change their color */
  .sidenav a:hover {
    color: #f1f1f1;
  }

  /* Position and style the close button (top right corner) */
  .sidenav .closebtn {
    position: absolute;
    top: 0;
    right: 25px;
    font-size: 36px;
    margin-left: 50px;
  }

  /* Style page content - use this if you want to push the page content to the right when you open the side navigation */
  #main {
    transition: all 0.3s;
    padding: 20px;
  }

  .pushMainToRight {
    /* margin-left: 472px; */
    position: absolute;
    transform: translate3d(472px, 0, 0);
  }

  .open {
    /* width: 472px; */
    transform: translate3d(0px, 0, 0);
  }


  button {
  border: none;
  background: none;
  cursor: pointer;
}
</style>
