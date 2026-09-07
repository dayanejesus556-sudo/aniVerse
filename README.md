# aniVerse
<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <meta name="description" content="AniVerse - Seu universo de animes.">
  <title>AniVerse — Universo dos Animes</title>

  <style>
    :root {
      --bg: #08090d;
      --bg-card: #11131a;
      --bg-soft: #171923;
      --text: #ffffff;
      --muted: #a5a7b3;
      --primary: #7c3aed;
      --primary-light: #a855f7;
      --danger: #ef4444;
      --border: rgba(255,255,255,.08);
      --shadow: 0 15px 45px rgba(0,0,0,.35);
    }

    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    html {
      scroll-behavior: smooth;
    }

    body {
      font-family: Arial, Helvetica, sans-serif;
      background: var(--bg);
      color: var(--text);
      min-height: 100vh;
    }

    button,
    input,
    select {
      font: inherit;
    }

    button {
      cursor: pointer;
      border: 0;
    }

    /* ================= HEADER ================= */

    header {
      position: fixed;
      top: 0;
      left: 0;
      right: 0;
      z-index: 1000;
      height: 70px;
      display: flex;
      align-items: center;
      padding: 0 5%;
      background: rgba(8,9,13,.82);
      backdrop-filter: blur(18px);
      border-bottom: 1px solid var(--border);
    }

    .logo {
      font-size: 25px;
      font-weight: 900;
      color: white;
      text-decoration: none;
      margin-right: 40px;
    }

    .logo span {
      color: var(--primary-light);
    }

    nav {
      display: flex;
      gap: 25px;
    }

    nav a {
      color: var(--muted);
      text-decoration: none;
      font-size: 14px;
      transition: .2s;
    }

    nav a:hover {
      color: white;
    }

    .header-right {
      margin-left: auto;
      display: flex;
      align-items: center;
      gap: 12px;
    }

    .search-box {
      display: flex;
      align-items: center;
      gap: 8px;
      background: var(--bg-soft);
      border: 1px solid var(--border);
      padding: 8px 12px;
      border-radius: 12px;
    }

    .search-box input {
      width: 170px;
      border: 0;
      outline: none;
      background: transparent;
      color: white;
    }

    .icon-btn {
      width: 40px;
      height: 40px;
      border-radius: 10px;
      background: var(--bg-soft);
      color: white;
      border: 1px solid var(--border);
    }

    .menu-btn {
      display: none;
    }

    /* ================= HERO ================= */

    .hero {
      min-height: 650px;
      padding: 150px 5% 80px;
      display: flex;
      align-items: center;
      position: relative;
      overflow: hidden;

      background:
        linear-gradient(90deg, #08090d 0%, rgba(8,9,13,.9) 35%, rgba(8,9,13,.25) 75%),
        url("https://images.unsplash.com/photo-1578632767115-351597cf2477?auto=format&fit=crop&w=1800&q=80")
        center/cover;
    }

    .hero-content {
      max-width: 650px;
      position: relative;
      z-index: 2;
    }

    .badge {
      display: inline-block;
      padding: 7px 12px;
      border-radius: 999px;
      background: rgba(124,58,237,.2);
      color: #c4b5fd;
      border: 1px solid rgba(168,85,247,.3);
      font-size: 12px;
      font-weight: bold;
      margin-bottom: 18px;
    }

    .hero h1 {
      font-size: clamp(42px, 7vw, 78px);
      line-height: .95;
      margin-bottom: 20px;
    }

    .hero h1 span {
      color: var(--primary-light);
    }

    .hero p {
      color: #d0d1d8;
      line-height: 1.7;
      max-width: 600px;
      margin-bottom: 25px;
    }

    .hero-meta {
      display: flex;
      gap: 15px;
      color: #d1d5db;
      font-size: 14px;
      margin-bottom: 25px;
    }

    .buttons {
      display: flex;
      gap: 12px;
      flex-wrap: wrap;
    }

    .btn {
      padding: 13px 20px;
      border-radius: 10px;
      font-weight: bold;
      transition: .2s;
    }

    .btn-primary {
      color: white;
      background: linear-gradient(135deg, var(--primary), var(--primary-light));
    }

    .btn-primary:hover {
      transform: translateY(-2px);
      box-shadow: 0 10px 25px rgba(124,58,237,.35);
    }

    .btn-secondary {
      color: white;
      background: rgba(255,255,255,.1);
      border: 1px solid var(--border);
    }

    .btn-secondary:hover {
      background: rgba(255,255,255,.16);
    }

    /* ================= MAIN ================= */

    main {
      padding: 55px 5%;
    }

    .section {
      margin-bottom: 60px;
    }

    .section-header {
      display: flex;
      align-items: center;
      justify-content: space-between;
      gap: 20px;
      margin-bottom: 22px;
    }

    .section-header h2 {
      font-size: 26px;
    }

    .section-header p {
      color: var(--muted);
      font-size: 13px;
    }

    .filters {
      display: flex;
      gap: 10px;
      flex-wrap: wrap;
    }

    .filter {
      padding: 9px 14px;
      border-radius: 9px;
      background: var(--bg-card);
      border: 1px solid var(--border);
      color: var(--muted);
    }

    .filter.active,
    .filter:hover {
      color: white;
      background: var(--primary);
    }

    /* ================= GRID ================= */

    .anime-grid {
      display: grid;
      grid-template-columns: repeat(6, 1fr);
      gap: 18px;
    }

    .anime-card {
      position: relative;
      overflow: hidden;
      background: var(--bg-card);
      border: 1px solid var(--border);
      border-radius: 14px;
      transition: .25s;
      cursor: pointer;
    }

    .anime-card:hover {
      transform: translateY(-7px);
      border-color: rgba(168,85,247,.4);
      box-shadow: var(--shadow);
    }

    .poster {
      height: 270px;
      position: relative;
      overflow: hidden;
    }

    .poster img {
      width: 100%;
      height: 100%;
      object-fit: cover;
      transition: .4s;
    }

    .anime-card:hover .poster img {
      transform: scale(1.06);
    }

    .score {
      position: absolute;
      top: 10px;
      left: 10px;
      padding: 5px 8px;
      border-radius: 7px;
      background: rgba(0,0,0,.7);
      color: #facc15;
      font-size: 12px;
      font-weight: bold;
    }

    .fav {
      position: absolute;
      top: 10px;
      right: 10px;
      width: 32px;
      height: 32px;
      border-radius: 50%;
      background: rgba(0,0,0,.65);
      color: white;
      font-size: 17px;
      z-index: 3;
    }

    .fav.active {
      color: #f43f5e;
    }

    .card-info {
      padding: 13px;
    }

    .card-info h3 {
      font-size: 15px;
      white-space: nowrap;
      overflow: hidden;
      text-overflow: ellipsis;
      margin-bottom: 7px;
    }

    .card-info p {
      color: var(--muted);
      font-size: 12px;
    }

    /* ================= EMPTY ================= */

    .empty {
      display: none;
      text-align: center;
      color: var(--muted);
      padding: 50px;
      grid-column: 1/-1;
    }

    /* ================= MODAL ================= */

    .modal {
      position: fixed;
      inset: 0;
      z-index: 2000;
      display: none;
      align-items: center;
      justify-content: center;
      padding: 20px;
      background: rgba(0,0,0,.78);
      backdrop-filter: blur(10px);
    }

    .modal.show {
      display: flex;
    }

    .modal-box {
      width: min(900px, 100%);
      max-height: 90vh;
      overflow-y: auto;
      background: #11131a;
      border: 1px solid var(--border);
      border-radius: 18px;
      box-shadow: var(--shadow);
      position: relative;
    }

    .close {
      position: absolute;
      right: 18px;
      top: 18px;
      z-index: 4;
      width: 38px;
      height: 38px;
      border-radius: 50%;
      background: rgba(0,0,0,.65);
      color: white;
      font-size: 20px;
    }

    .modal-banner {
      height: 300px;
      position: relative;
      background-size: cover;
      background-position: center;
    }

    .modal-banner::after {
      content: "";
      position: absolute;
      inset: 0;
      background: linear-gradient(transparent, #11131a);
    }

    .modal-content {
      padding: 0 30px 30px;
      margin-top: -55px;
      position: relative;
      z-index: 2;
    }

    .modal-content h2 {
      font-size: 34px;
      margin-bottom: 10px;
    }

    .modal-content p {
      color: #c7c9d1;
      line-height: 1.7;
      margin: 15px 0;
    }

    .tags {
      display: flex;
      gap: 8px;
      flex-wrap: wrap;
    }

    .tag {
      padding: 6px 10px;
      background: var(--bg-soft);
      border-radius: 7px;
      color: #c4b5fd;
      font-size: 12px;
    }

    /* ================= FOOTER ================= */

    footer {
      border-top: 1px solid var(--border);
      padding: 45px 5%;
      color: var(--muted);
      text-align: center;
    }

    footer strong {
      color: white;
    }

    /* ================= RESPONSIVE ================= */

    @media (max-width: 1200px) {
      .anime-grid {
        grid-template-columns: repeat(4, 1fr);
      }
    }

    @media (max-width: 800px) {
      nav {
        display: none;
      }

      .menu-btn {
        display: block;
      }

      .search-box input {
        width: 100px;
      }

      .anime-grid {
        grid-template-columns: repeat(3, 1fr);
      }

      .poster {
        height: 230px;
      }

      .hero {
        min-height: 570px;
      }
    }

    @media (max-width: 550px) {
      header {
        padding: 0 4%;
      }

      .logo {
        margin-right: 10px;
      }

      .search-box {
        display: none;
      }

      .anime-grid {
        grid-template-columns: repeat(2, 1fr);
        gap: 12px;
      }

      .poster {
        height: 250px;
      }

      main {
        padding: 40px 4%;
      }

      .hero {
        padding-left: 4%;
        padding-right: 4%;
        background:
          linear-gradient(90deg, #08090d 0%, rgba(8,9,13,.82) 100%),
          url("https://images.unsplash.com/photo-1578632767115-351597cf2477?auto=format&fit=crop&w=1200&q=80")
          center/cover;
      }

      .hero h1 {
        font-size: 48px;
      }

      .section-header {
        align-items: flex-start;
        flex-direction: column;
      }

      .modal-content {
        padding: 0 20px 25px;
      }
    }
  </style>
</head>

<body>

  <!-- ================= HEADER ================= -->

  <header>
    <a href="#" class="logo">Ani<span>Verse</span></a>

    <nav>
      <a href="#inicio">Início</a>
      <a href="#populares">Populares</a>
      <a href="#catalogo">Catálogo</a>
      <a href="#favoritos">Favoritos</a>
    </nav>

    <div class="header-right">

      <div class="search-box">
        🔎
        <input
          type="text"
          id="search"
          placeholder="Pesquisar anime..."
          autocomplete="off"
        >
      </div>

      <button class="icon-btn" id="themeBtn" title="Alterar tema">
        ☀️
      </button>

      <button class="icon-btn menu-btn" id="menuBtn">
        ☰
      </button>

    </div>
  </header>


  <!-- ================= HERO ================= -->

  <section class="hero" id="inicio">

    <div class="hero-content">

      <span class="badge">🔥 DESTAQUE DA SEMANA</span>

      <h1>
        O mundo dos<br>
        <span>animes</span>
      </h1>

      <div class="hero-meta">
        <span>⭐ 9.8</span>
        <span>•</span>
        <span>2026</span>
        <span>•</span>
        <span>Ação</span>
      </div>

      <p>
        Explore um universo de aventuras, batalhas e histórias inesquecíveis.
        Encontre seus animes favoritos em um só lugar.
      </p>

      <div class="buttons">
        <button class="btn btn-primary" onclick="openAnime(1)">
          ▶ Ver detalhes
        </button>

        <button class="btn btn-secondary" onclick="scrollToCatalog()">
          Explorar catálogo
        </button>
      </div>

    </div>

  </section>


  <!-- ================= MAIN ================= -->

  <main>

    <section class="section" id="populares">

      <div class="section-header">
        <div>
          <h2>🔥 Mais populares</h2>
          <p>Os animes que estão fazendo sucesso</p>
        </div>
      </div>

      <div class="anime-grid" id="popularGrid"></div>

    </section>


    <section class="section" id="catalogo">

      <div class="section-header">

        <div>
          <h2>📚 Catálogo</h2>
          <p>Encontre seu próximo anime favorito</p>
        </div>

        <div class="filters">
          <button class="filter active" data-filter="Todos">
            Todos
          </button>

          <button class="filter" data-filter="Ação">
            Ação
          </button>

          <button class="filter" data-filter="Aventura">
            Aventura
          </button>

          <button class="filter" data-filter="Fantasia">
            Fantasia
          </button>

          <button class="filter" data-filter="Romance">
            Romance
          </button>
        </div>

      </div>

      <div class="anime-grid" id="animeGrid">

        <div class="empty" id="empty">
          Nenhum anime encontrado. 😕
        </div>

      </div>

    </section>


    <section class="section" id="favoritos">

      <div class="section-header">
        <div>
          <h2>❤️ Seus favoritos</h2>
          <p>Animes que você marcou para assistir depois</p>
        </div>
      </div>

      <div class="anime-grid" id="favoriteGrid">

        <div class="empty" id="favoriteEmpty" style="display:block;">
          Você ainda não adicionou favoritos.
        </div>

      </div>

    </section>

  </main>


  <!-- ================= MODAL ================= -->

  <div class="modal" id="modal">

    <div class="modal-box">

      <button class="close" onclick="closeModal()">×</button>

      <div
        class="modal-banner"
        id="modalBanner"
      ></div>

      <div class="modal-content">

        <h2 id="modalTitle"></h2>

        <div class="tags" id="modalTags"></div>

        <p id="modalDescription"></p>

        <div class="buttons">
          <button class="btn btn-primary">
            ▶ Assistir agora
          </button>

          <button class="btn btn-secondary" id="modalFavorite">
            ❤️ Favoritar
          </button>
        </div>

      </div>

    </div>

  </div>


  <!-- ================= FOOTER ================= -->

  <footer>
    <p>
      <strong>AniVerse</strong> — Seu universo de animes.
    </p>

    <br>

    <small>
      Projeto demonstrativo criado com HTML, CSS e JavaScript.
    </small>
  </footer>


  <!-- ================= JAVASCRIPT ================= -->

  <script>

    const animes = [

      {
        id: 1,
        title: "Shadow Legends",
        year: 2026,
        score: 9.8,
        genre: ["Ação", "Fantasia"],
        image: "https://images.unsplash.com/photo-1578632767115-351597cf2477?auto=format&fit=crop&w=700&q=80",
        description:
          "Um jovem guerreiro descobre um poder misterioso capaz de mudar o destino de seu mundo."
      },

      {
        id: 2,
        title: "Demon Realm",
        year: 2025,
        score: 9.5,
        genre: ["Ação", "Fantasia"],
        image: "https://images.unsplash.com/photo-1614583224978-fc8e2e5d3f4c?auto=format&fit=crop&w=700&q=80",
        description:
          "Uma jornada perigosa começa quando portais para um reino desconhecido aparecem."
      },

      {
        id: 3,
        title: "Cyber Tokyo",
        year: 2026,
        score: 9.2,
        genre: ["Ação"],
        image: "https://images.unsplash.com/photo-1519608487953-e999c86e7455?auto=format&fit=crop&w=700&q=80",
        description:
          "Em uma cidade futurista, uma equipe de jovens enfrenta uma ameaça tecnológica."
      },

      {
        id: 4,
        title: "Dragon's Path",
        year: 2024,
        score: 9.0,
        genre: ["Aventura", "Fantasia"],
        image: "https://images.unsplash.com/photo-1577083552431-6e5fd01988d5?auto=format&fit=crop&w=700&q=80",
        description:
          "Um aventureiro parte em busca de um antigo dragão lendário."
      },

      {
        id: 5,
        title: "Moon Academy",
        year: 2025,
        score: 8.9,
        genre: ["Fantasia", "Romance"],
        image: "https://images.unsplash.com/photo-1500530855697-b586d89ba3ee?auto=format&fit=crop&w=700&q=80",
        description:
          "Uma estudante descobre que sua nova escola esconde segredos mágicos."
      },

      {
        id: 6,
        title: "Samurai Zero",
        year: 2023,
        score: 8.8,
        genre: ["Ação", "Aventura"],
        image: "https://images.unsplash.com/photo-1528360983277-13d401cdc186?auto=format&fit=crop&w=700&q=80",
        description:
          "Um samurai sem mestre procura redenção enquanto atravessa um Japão cheio de perigos."
      },

      {
        id: 7,
        title: "Star Fighters",
        year: 2025,
        score: 8.7,
        genre: ["Ação", "Aventura"],
        image: "https://images.unsplash.com/photo-1446776877081-d282a0f896e2?auto=format&fit=crop&w=700&q=80",
        description:
          "Pilotos de diferentes planetas se unem para proteger a galáxia."
      },

      {
        id: 8,
        title: "Love Signal",
        year: 2024,
        score: 8.6,
        genre: ["Romance"],
        image: "https://images.unsplash.com/photo-1518709268805-4e9042af9f23?auto=format&fit=crop&w=700&q=80",
        description:
          "Uma história leve sobre amizade, sentimentos e novos começos."
      },

      {
        id: 9,
        title: "Mystic Forest",
        year: 2025,
        score: 8.5,
        genre: ["Fantasia", "Aventura"],
        image: "https://images.unsplash.com/photo-1448375240586-882707db888b?auto=format&fit=crop&w=700&q=80",
        description:
          "Uma floresta misteriosa guarda criaturas mágicas e um segredo antigo."
      },

      {
        id: 10,
        title: "Ninja Code",
        year: 2026,
        score: 8.4,
        genre: ["Ação"],
        image: "https://images.unsplash.com/photo-1550751827-4bd374c3f58b?auto=format&fit=crop&w=700&q=80",
        description:
          "Ninjas modernos usam tecnologia avançada para proteger sua cidade."
      },

      {
        id: 11,
        title: "Ocean Dreams",
        year: 2023,
        score: 8.3,
        genre: ["Aventura", "Romance"],
        image: "https://images.unsplash.com/photo-1507525428034-b723cf961d3e?auto=format&fit=crop&w=700&q=80",
        description:
          "Uma aventura marítima cheia de descobertas e amizades."
      },

      {
        id: 12,
        title: "Magic World",
        year: 2024,
        score: 8.2,
        genre: ["Fantasia"],
        image: "https://images.unsplash.com/photo-1519608487953-e999c86e7455?auto=format&fit=crop&w=700&q=80",
        description:
          "Um estudante comum recebe a chance de entrar em um mundo completamente mágico."
      }

    ];


    let favorites =
      JSON.parse(localStorage.getItem("animeFavorites")) || [];

    let currentFilter = "Todos";


    /* ================= CARD ================= */

    function createCard(anime) {

      const isFavorite = favorites.includes(anime.id);

      return `

        <article
          class="anime-card"
          onclick="openAnime(${anime.id})"
        >

          <div class="poster">

            <img
              src="${anime.image}"
              alt="${anime.title}"
              loading="lazy"
            >

            <span class="score">
              ⭐ ${anime.score}
            </span>

            <button
              class="fav ${isFavorite ? "active" : ""}"
              onclick="toggleFavorite(event, ${anime.id})"
              title="Favoritar"
            >
              ${isFavorite ? "♥" : "♡"}
            </button>

          </div>

          <div class="card-info">

            <h3>${anime.title}</h3>

            <p>
              ${anime.year} • ${anime.genre.join(" / ")}
            </p>

          </div>

        </article>

      `;
    }


    /* ================= RENDER ================= */

    function renderPopular() {

      const grid = document.getElementById("popularGrid");

      const popular = [...animes]
        .sort((a, b) => b.score - a.score)
        .slice(0, 6);

      grid.innerHTML = popular
        .map(createCard)
        .join("");
    }


    function renderCatalog() {

      const grid = document.getElementById("animeGrid");
      const empty = document.getElementById("empty");

      const search =
        document
          .getElementById("search")
          .value
          .toLowerCase()
          .trim();

      const filtered = animes.filter(anime => {

        const matchesFilter =
          currentFilter === "Todos" ||
          anime.genre.includes(currentFilter);

        const matchesSearch =
          anime.title.toLowerCase().includes(search);

        return matchesFilter && matchesSearch;
      });

      grid.innerHTML =
        filtered.length
          ? filtered.map(createCard).join("")
          : "";

      empty.style.display =
        filtered.length ? "none" : "block";
    }


    function renderFavorites() {

      const grid = document.getElementById("favoriteGrid");
      const empty = document.getElementById("favoriteEmpty");

      const favoriteAnimes =
        animes.filter(anime =>
          favorites.includes(anime.id)
        );

      grid.innerHTML =
        favoriteAnimes.length
          ? favoriteAnimes.map(createCard).join("")
          : "";

      empty.style.display =
        favoriteAnimes.length
          ? "none"
          : "block";
    }


    /* ================= FAVORITES ================= */

    function toggleFavorite(event, id) {

      event.stopPropagation();

      if (favorites.includes(id)) {

        favorites =
          favorites.filter(item => item !== id);

      } else {

        favorites.push(id);
      }

      localStorage.setItem(
        "animeFavorites",
        JSON.stringify(favorites)
      );

      renderPopular();
      renderCatalog();
      renderFavorites();
    }


    /* ================= MODAL ================= */

    function openAnime(id) {

      const anime =
        animes.find(item => item.id === id);

      if (!anime) return;

      document.getElementById("modalTitle")
        .textContent = anime.title;

      document.getElementById("modalDescription")
        .textContent = anime.description;

      document.getElementById("modalBanner")
        .style.backgroundImage =
        `url("${anime.image}")`;

      document.getElementById("modalTags")
        .innerHTML = `

          <span class="tag">
            ⭐ ${anime.score}
          </span>

          <span class="tag">
            ${anime.year}
          </span>

          ${anime.genre.map(g =>
            `<span class="tag">${g}</span>`
          ).join("")}

        `;

      const favoriteBtn =
        document.getElementById("modalFavorite");

      favoriteBtn.textContent =
        favorites.includes(id)
          ? "♥ Remover dos favoritos"
          : "♡ Favoritar";

      favoriteBtn.onclick = () => {

        const fakeEvent = {
          stopPropagation: () => {}
        };

        toggleFavorite(fakeEvent, id);

        favoriteBtn.textContent =
          favorites.includes(id)
            ? "♥ Remover dos favoritos"
            : "♡ Favoritar";
      };

      document
        .getElementById("modal")
        .classList.add("show");
    }


    function closeModal() {

      document
        .getElementById("modal")
        .classList.remove("show");
    }


    document
      .getElementById("modal")
      .addEventListener("click", event => {

        if (event.target.id === "modal") {
          closeModal();
        }

      });


    /* ================= SEARCH ================= */

    document
      .getElementById("search")
      .addEventListener("input", renderCatalog);


    /* ================= FILTERS ================= */

    document
      .querySelectorAll(".filter")
      .forEach(button => {

        button.addEventListener("click", () => {

          document
            .querySelectorAll(".filter")
            .forEach(btn =>
              btn.classList.remove("active")
            );

          button.classList.add("active");

          currentFilter =
            button.dataset.filter;

          renderCatalog();
        });

      });


    /* ================= THEME ================= */

    const themeBtn =
      document.getElementById("themeBtn");

    themeBtn.addEventListener("click", () => {

      const light =
        document.body.dataset.theme === "light";

      if (light) {

        document.body.dataset.theme = "dark";
        themeBtn.textContent = "☀️";

        document.documentElement.style
          .setProperty("--bg", "#08090d");

        document.documentElement.style
          .setProperty("--bg-card", "#11131a");

        document.documentElement.style
          .setProperty("--bg-soft", "#171923");

        document.documentElement.style
          .setProperty("--text", "#ffffff");

      } else {

        document.body.dataset.theme = "light";
        themeBtn.textContent = "🌙";

        document.documentElement.style
          .setProperty("--bg", "#f4f4f7");

        document.documentElement.style
          .setProperty("--bg-card", "#ffffff");

        document.documentElement.style
          .setProperty("--bg-soft", "#e9e9ef");

        document.documentElement.style
          .setProperty("--text", "#111111");

      }

    });


    /* ================= SCROLL ================= */

    function scrollToCatalog() {

      document
        .getElementById("catalogo")
        .scrollIntoView({
          behavior: "smooth"
        });
    }


    /* ================= MOBILE MENU ================= */

    document
      .getElementById("menuBtn")
      .addEventListener("click", () => {

        const nav =
          document.querySelector("nav");

        if (nav.style.display === "flex") {

          nav.style.display = "none";

        } else {

          nav.style.display = "flex";

          nav.style.position = "absolute";
          nav.style.top = "70px";
          nav.style.left = "0";
          nav.style.right = "0";
          nav.style.padding = "20px";
          nav.style.background = "#11131a";
          nav.style.flexDirection = "column";
        }

      });


    /* ================= ESC ================= */

    document.addEventListener("keydown", event => {

      if (event.key === "Escape") {
        closeModal();
      }

    });


    /* ================= START ================= */

    renderPopular();
    renderCatalog();
    renderFavorites();

  </script>

</body>
</html>