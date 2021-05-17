<script>
  import Header from "./components/Header.svelte";
  import Main from "./components/Main.svelte";
  import Footer from "./components/Footer.svelte";

  let year = new Date().getFullYear();
  let currentPage = "Dashboard";

  let blinds = [
    {
      id: 0,
      room: "Gästezimmer",
      dim: 100,
      power: 0.6,
    },
    {
      id: 1,
      room: "Schlafzimmer",
      dim: 100,
      power: 0.6,
    },
    {
      id: 2,
      room: "Arbeitszimmer",
      dim: 100,
      power: 0,
    },
  ];

  const setCurrentPage = (e) => {
    currentPage = e.detail.srcElement.dataset.target;
  };
</script>

<svelte:head>
  <title>Home Pi | {currentPage}</title>
  <link href="https://fonts.googleapis.com/icon?family=Material+Icons" rel="stylesheet" />
</svelte:head>

<Header on:setCurrentPage={setCurrentPage} />
<Main {currentPage} {blinds} />
<Footer {year} />