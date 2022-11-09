<script>
	import { page } from '$app/stores';

  // 	let navWidth = 0;
  let navOpen = false;

  function handleNav() {
    navOpen = !navOpen;
    // 		navWidth === 0 ? navWidth = 40 : navWidth = 0;
  }

  const hoofdstuk1 = [
    {
      id: 1.1,
      name: "1.1 Humanity-centered digital designers",
      route: "/beoogde-leerresultaten/",
      hoofdstuk: 1,
      apiId: 5
    },
    {
      id: 1.2,
      name: "1.2 Competenties",
      route: "/beoogde-leerresultaten/2",
      hoofdstuk: 1,
      apiId: 11
    },
    {
      id: 1.3,
      name: "1.3 Werkveld en maatschappij",
      route: "/beoogde-leerresultaten/3",
      hoofdstuk: 1,
      apiId: 2
    },
    {
      id: 1.4,
      name: "1.4 Ontwikkelingen",
      route: "/beoogde-leerresultaten/4",
      hoofdstuk: 1,
      apiId: 4
    },
    {
      id: 1.5,
      name: "1.5 Ambities en dilemma’s",
      route: "/beoogde-leerresultaten/5",
      hoofdstuk: 1,
      apiId: 12
    },
  ];
  const hoofdstuk2 = [
    {
      id: 2.1,
      name: "2.1 Onderwijsvisie en didactiek",
      route: "/onderwijsleeromgeving",
      hoofdstuk: 2,
      apiId: 15
    },
    {
      id: 2.2,
      name: "2.2 Curriculumopbouw",
      route: "/Onderwijsleeromgeving/2",
      hoofdstuk: 2,
      apiId: 0
    },
    {
      id: 2.3,
      name: "2.3 Borging onderwijskwaliteit",
      route: "/Onderwijsleeromgeving/3",
      hoofdstuk: 2,
      apiId: 18
    },
    {
      id: 2.4,
      name: "2.4 Onderwijs en praktijk",
      route: "/Onderwijsleeromgeving/4",
      hoofdstuk: 2,
      apiId: 1
    },
    {
      id: 2.5,
      name: "2.5 Onderwijs en onderzoek",
      route: "/Onderwijsleeromgeving/5",
      hoofdstuk: 2,
      apiId: 7
    },
    {
      id: 2.6,
      name: "2.6 Internationalisering",
      route: "/Onderwijsleeromgeving/6",
      hoofdstuk: 2,
      apiId: 16
    },
    {
      id: 2.7,
      name: "2.7 Studenten begeleiding",
      route: "/Onderwijsleeromgeving/7",
      hoofdstuk: 2,
      apiId: 14
    },
    {
      id: 2.8,
      name: "2.8 Digitale en analoge voorzieningen",
      route: "/Onderwijsleeromgeving/8",
      hoofdstuk: 2,
      apiId: 22
    },
    {
      id: 2.9,
      name: "2.9 Ambities en dilemma's",
      route: "/Onderwijsleeromgeving/9",
      hoofdstuk: 2,
      apiId: 10
    }
  ];
  const hoofdstuk3 = [
    {
      id: 3.1,
      name: "3.1 Toetsbeleid en -plan",
      route: "/toetsing",
      hoofdstuk: 3,
      apiId: 17
    },
    {
      id: 3.2,
      name: "3.2 Toetsprogramma en -praktijk",
      route: "/toetsing/2",
      hoofdstuk: 3,
      apiId: 9
    },
    {
      id: 3.3,
      name: "3.3 Toetsing en feedback",
      route: "/toetsing/3",
      hoofdstuk: 3,
      apiId: 4
    },
    {
      id: 3.4,
      name: "3.4 Borging en kwaliteit",
      route: "/toetsing/4",
      hoofdstuk: 3,
      apiId: 11
    },
    {
      id: 3.5,
      name: "3.5 Ambities en dilemma's",
      route: "/toetsing/5",
      hoofdstuk: 3,
      apiId: 21
    },
  ]  
  const hoofdstuk4 = [
    {
      id: 4.1,
      name: "4.1 Afstudeerproces",
      route: "/gerealiseerde-leerresultaten",
      hoofdstuk: 4,
      apiId: 19
    },
    {
      id: 4.2,
      name: "4.2 Borging afstudeerniveau vanuit examencommissie",
      route: "/gerealiseerde-leerresultaten/2",
      hoofdstuk: 4,
      apiId: 8
    },
    {
      id: 4.3,
      name: "4.3 Ambities en dilemma's",
      route: "/gerealiseerde-leerresultaten/3",
      hoofdstuk: 4,
      apiId: 20
    },
  ]

  let navHoofdstuk = hoofdstuk1


  function navButtonEen(){
    console.log(`de nav verandert naar h1`)
    navHoofdstuk = hoofdstuk1
  }

  function navButtonTwee(){
    console.log(`de nav verandert naar h2`)
    navHoofdstuk = hoofdstuk2
  }

  function navButtonDrie(){
    console.log(`de nav verandert naar h3`)
    navHoofdstuk = hoofdstuk3
  }

  function navButtonVier(){
    console.log(`de nav verandert naar h4`)
    navHoofdstuk = hoofdstuk4
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

<button
  class="hamButton"
  class:pushMainToRight={navOpen}
  on:click={handleNav}
>
  <i class="bx bx-menu-alt-left" />
</button>

<main id="main" class:pushMainToRight={navOpen}>
  <h2>Dit is de vierde versie</h2>

  <section class="button__wrapper">
    <button on:click={navButtonEen}>H1</button>
    <button on:click={navButtonTwee}>H2</button>
    <button on:click={navButtonDrie}>H3</button>
    <button on:click={navButtonVier}>H4</button>
  </section>
  
  {#each navHoofdstuk as paragraaf}
    <li class:nav__item--active={$page.url.pathname === paragraaf.route}>
      <a href={paragraaf.route} class:nav__link--active={$page.url.pathname === paragraaf.route}>
        {paragraaf.name}
      </a>
    </li>
  {/each}
</main>

<style>
    .button__wrapper button{
        background-color: var(--nav-text-grey);
        padding: .5em 1em;
        color: var(--cream-white);
    }

    .button__active{
        font-weight: bold;
        color: var(--cream-red);
    }

  :global(:root) {
    --yellow: #f4e500;
    --cream-white: #f0ebf0;
    --cream-red: #db504c;
    --dark-grey: #2f3135;
    --nav-accent-color: #50545b;
    --nav-text-grey: #8e9296;
  }

  .sidenav a {
    padding: 8px 8px 8px 32px;
    text-decoration: none;
    font-size: 25px;
    color: #818181;
    display: block;
    transition: 0.3s;

  }

  /* NAVIGATION */
  .sidenav {
    height: 100vh;
    max-width: 400px;
    width: 100%;

    position: fixed;
    z-index: 1;
    top: 0;
    left: 0;

    background-color: #2f3135;

    overflow-x: hidden; /* Disable horizontal scroll */
    padding-top: 60px;

    transition: 0.3s;
    transform: translate3d(-400px, 0, 0);
  }

  /* Hamburger Menu icon */
  .hamButton {
    position: absolute;
    left: 20px;
    display: inline-block;
    cursor: pointer;
    z-index: 2;
    font-size: 2.5em;
    transition: 0.3s;
  }

  /* The navigation menu links */
  .sidenav a {
    text-decoration: none;
    font-size: 25px;
    color: #818181;
    display: block;
    transition: 0.3s;
  }

  /* When you mouse over the navigation links, change their color */
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
    position: absolute;
    transform: translate3d(400px, 0, 0);
  }

  .open {
    transform: translate3d(0px, 0, 0);
  }

  button {
    border: none;
    background: none;
    cursor: pointer;
  }

  :global(.flex) {
    display: flex;
  }

  /* OUDE CODE */
  .nav__icon--wrapper {
    background-color: var(--yellow);
    min-width: 72px;
    max-width: 80px;
    display: flex;
    flex-direction: column;
    align-items: center;
  }
  .nav__icon {
    width: 56px;
    height: 56px;
    display: flex;
    justify-content: center;
    align-items: center;
    background: #000;
    border-radius: 50%;
    margin-bottom: 1em;
  }
  .nav__icon:first-child {
    margin-bottom: 1em;
    margin-top: 1em;
  }
  .nav__icon i {
    font-size: 2.5em;
    color: #f0ebf0;
  }
  .nav__diveder {
    height: 2px;
    width: 32px;
    border-radius: 5px;
    background-color: #000;
    margin-bottom: 1em;
  }
  .nav__link--wrapper {
    background-color: var(--dark-grey);
    width: calc(400px - 72px);
  }

  .nav__header {
    background-color: var(--yellow);
    padding-left: 1em;
    height: 80px;
    display: flex;
    align-items: center;
  }

  .nav__list {
    padding: 1em;
  }

  .nav__item {
    margin-bottom: 1em;
    padding: 2px 4px;
  }
  .nav__link {
    color: var(--nav-text-grey);
    font-size: 22px;
  }
  .nav__item--active {
    background-color: var(--nav-accent-color);
    border-radius: 3px;
  }
  .nav__link--active {
    color: #fff;
  }
</style>
