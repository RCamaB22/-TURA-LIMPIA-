# -TURA-LIMPIA-
El proyecto Tura Limpia. Espacio para compartir avances, revisar asignaciones e integrar el trabajo del equipo.


<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>TuraLimpia | Prototipo visual</title>
  <style>
    :root{
      --green:#177a52;
      --green-dark:#0f5d3d;
      --green-soft:#e8f5ef;
      --bg:#f3f6f5;
      --card:#ffffff;
      --line:#dce5e1;
      --text:#20332b;
      --muted:#6d7d76;
      --blue:#dff1fb;
      --blue-soft:#eef7ff;
      --danger:#e44;
      --shadow:0 4px 14px rgba(25, 66, 48, .08);
      --radius:14px;
    }

    *{box-sizing:border-box}

    body{
      margin:0;
      font-family: "Segoe UI", Arial, sans-serif;
      background:var(--bg);
      color:var(--text);
    }

    .app{
      display:grid;
      grid-template-columns: 270px 1fr;
      min-height:100vh;
    }

    /* SIDEBAR */
    .sidebar{
      background:linear-gradient(180deg,#0d5a3b,#083f2a);
      color:#fff;
      padding:20px 0;
      display:flex;
      flex-direction:column;
      gap:18px;
    }

    .brand{
      display:flex;
      align-items:center;
      gap:14px;
      padding:0 24px 10px 24px;
    }

    .brand-logo{
      width:38px;
      height:38px;
      border-radius:12px;
      background:rgba(255,255,255,.15);
      display:flex;
      align-items:center;
      justify-content:center;
      font-size:24px;
    }

    .brand h1{
      margin:0;
      font-size:24px;
      font-weight:800;
      letter-spacing:.2px;
    }

    .menu{
      padding:0 12px;
    }

    .menu-item{
      display:flex;
      align-items:center;
      gap:12px;
      color:#eaf5f0;
      text-decoration:none;
      padding:14px 16px;
      border-radius:12px;
      margin-bottom:8px;
      transition:.2s;
      font-size:16px;
    }

    .menu-item.active{
      background:#1f8a5e;
      box-shadow:inset 0 0 0 1px rgba(255,255,255,.08);
    }

    .menu-item .icon{
      width:24px;
      text-align:center;
      opacity:.95;
    }

    .menu-sep{
      margin:10px 18px;
      border-top:1px solid rgba(255,255,255,.16);
    }

    /* MAIN */
    .main{
      display:flex;
      flex-direction:column;
      min-width:0;
    }

    .topbar{
      background:#fff;
      border-bottom:1px solid var(--line);
      display:flex;
      justify-content:space-between;
      align-items:center;
      padding:18px 26px;
      gap:20px;
    }

    .topbar-left{
      display:flex;
      align-items:center;
      gap:18px;
      min-width:0;
    }

    .topbar-left .divider{
      width:1px;
      height:34px;
      background:var(--line);
    }

    .topbar-title{
      font-size:20px;
      font-weight:700;
      white-space:nowrap;
      overflow:hidden;
      text-overflow:ellipsis;
    }

    .topbar-right{
      display:flex;
      align-items:center;
      gap:18px;
    }

    .bell{
      position:relative;
      font-size:22px;
    }

    .bell::after{
      content:"";
      position:absolute;
      top:1px;
      right:-2px;
      width:8px;
      height:8px;
      border-radius:50%;
      background:var(--danger);
    }

    .user{
      display:flex;
      align-items:center;
      gap:12px;
    }

    .user-avatar{
      width:42px;
      height:42px;
      border-radius:50%;
      background:#eef2f3;
      border:1px solid #d9e0dc;
      display:flex;
      align-items:center;
      justify-content:center;
      font-size:22px;
    }

    .user-info{
      line-height:1.15;
    }

    .user-info .name{
      font-weight:700;
    }

    .user-info .role{
      color:var(--muted);
      font-size:14px;
      margin-top:3px;
    }

    .content{
      padding:18px;
      display:flex;
      flex-direction:column;
      gap:16px;
    }

    .card{
      background:var(--card);
      border:1px solid var(--line);
      border-radius:var(--radius);
      box-shadow:var(--shadow);
    }

    .card.pad{
      padding:18px;
    }

    .card-title{
      display:flex;
      align-items:center;
      gap:12px;
      margin:0 0 14px 0;
      font-size:20px;
      font-weight:800;
    }

    .card-title .ico{
      color:var(--green);
    }

    /* FILTERS */
    .filters-grid{
      display:grid;
      grid-template-columns:repeat(4, minmax(0,1fr));
      gap:18px;
    }

    .field label{
      display:block;
      margin-bottom:10px;
      font-weight:800;
      font-size:15px;
    }

    .field select{
      width:100%;
      height:46px;
      border-radius:10px;
      border:2px solid #cad8d2;
      outline:none;
      padding:0 14px;
      background:#fff;
      font-size:16px;
      color:#1d3128;
    }

    .field select:focus{
      border-color:#3ca877;
      box-shadow:0 0 0 3px rgba(23,122,82,.08);
    }

    /* LAYOUT BELOW FILTERS */
    .dashboard{
      display:grid;
      grid-template-columns:minmax(0,1.8fr) minmax(340px,1fr);
      gap:16px;
    }

    .map-shell{
      display:flex;
      flex-direction:column;
      gap:12px;
    }

    .map-box{
      background:#90d4f5;
      border-radius:12px;
      overflow:hidden;
      border:1px solid #cce4ef;
      position:relative;
      min-height:690px;
    }

    .map-inner{
      position:relative;
      width:100%;
      height:690px;
      background:
        radial-gradient(circle at 30% 25%, rgba(255,255,255,.22), transparent 20%),
        linear-gradient(180deg,#99d8f6,#8bcdf1);
    }

    /* legend */
    .legend{
      position:absolute;
      left:14px;
      top:14px;
      width:200px;
      background:#fff;
      border-radius:12px;
      border:1px solid rgba(0,0,0,.06);
      box-shadow:var(--shadow);
      padding:14px;
      z-index:5;
    }

    .legend-row{
      display:flex;
      align-items:center;
      gap:12px;
      margin-bottom:14px;
      font-size:14px;
      color:#354941;
    }

    .legend-row:last-child{margin-bottom:0}

    .lg-line{
      width:36px;
      height:5px;
      border-radius:999px;
      background:var(--green);
    }

    .lg-stop{
      width:30px;
      height:30px;
      border-radius:50%;
      background:#1d975f;
      color:#fff;
      display:flex;
      align-items:center;
      justify-content:center;
      font-weight:800;
      font-size:15px;
      flex-shrink:0;
    }

    .lg-hollow{
      width:16px;
      height:16px;
      border-radius:50%;
      border:3px solid #6f7d7a;
      background:#fff;
      margin-left:7px;
      margin-right:7px;
      flex-shrink:0;
    }

    .lg-area{
      width:36px;
      height:22px;
      border-radius:4px;
      background:#cfe8c9;
      flex-shrink:0;
    }

    .lg-road{
      width:36px;
      height:5px;
      border-radius:999px;
      background:#d4d8db;
      flex-shrink:0;
    }

    /* compass */
    .compass{
      position:absolute;
      top:18px;
      right:18px;
      width:44px;
      height:62px;
      background:#fff;
      border-radius:10px;
      box-shadow:var(--shadow);
      display:flex;
      flex-direction:column;
      align-items:center;
      justify-content:center;
      font-weight:800;
      z-index:6;
    }

    .compass .arrow{
      font-size:28px;
      color:#31454f;
      line-height:1;
      margin-top:2px;
    }

    /* zoom */
    .zoom{
      position:absolute;
      right:18px;
      bottom:24px;
      display:flex;
      flex-direction:column;
      background:#fff;
      border-radius:10px;
      overflow:hidden;
      box-shadow:var(--shadow);
      z-index:6;
      border:1px solid rgba(0,0,0,.08);
    }

    .zoom button{
      width:48px;
      height:48px;
      border:none;
      background:#fff;
      font-size:34px;
      color:#233842;
      cursor:pointer;
    }

    .zoom button + button{
      border-top:1px solid #e6ebea;
    }

    .scale{
      position:absolute;
      left:16px;
      bottom:20px;
      z-index:6;
      color:#19302d;
      font-size:14px;
    }

    .scale-bar{
      width:140px;
      height:6px;
      border-bottom:4px solid #233743;
      position:relative;
      margin-top:4px;
    }

    .scale-bar::before,
    .scale-bar::after{
      content:"";
      position:absolute;
      bottom:-4px;
      width:2px;
      height:12px;
      background:#233743;
    }

    .scale-bar::before{left:0}
    .scale-bar::after{right:0}
    .scale-mid{
      position:absolute;
      left:50%;
      transform:translateX(-50%);
      bottom:-4px;
      width:2px;
      height:12px;
      background:#233743;
    }

    /* stylized map island */
    .island{
      position:absolute;
      inset:40px 56px 40px 56px;
      display:flex;
      align-items:center;
      justify-content:center;
    }

    .island svg{
      width:100%;
      height:100%;
      display:block;
    }

    .land-label{
      fill:#1f3952;
      font-size:18px;
      opacity:.9;
    }

    .neighborhood{
      fill:#202c2c;
      font-size:15px;
      font-weight:500;
    }

    .water-label{
      fill:#2d6aa2;
      font-style:italic;
      font-size:15px;
      opacity:.9;
    }

    .map-status{
      color:var(--muted);
      font-size:14px;
      margin-top:6px;
    }

    /* RIGHT PANELS */
    .side-panels{
      display:flex;
      flex-direction:column;
      gap:16px;
    }

    .info-panel{
      padding:16px;
    }

    .panel-heading{
      display:flex;
      align-items:center;
      gap:10px;
      font-size:19px;
      font-weight:800;
      margin-bottom:14px;
    }

    .route-highlight,
    .stop-highlight{
      display:flex;
      align-items:center;
      justify-content:space-between;
      gap:12px;
      background:var(--green-soft);
      border-radius:10px;
      padding:12px 14px;
      margin-bottom:10px;
    }

    .route-highlight-left,
    .stop-highlight-left{
      display:flex;
      align-items:center;
      gap:10px;
      font-weight:800;
      font-size:17px;
      color:#167249;
    }

    .route-status{
      background:#19834f;
      color:#fff;
      padding:8px 12px;
      border-radius:10px;
      font-weight:700;
      font-size:14px;
      white-space:nowrap;
    }

    .kv{
      display:grid;
      grid-template-columns:132px 1fr;
      gap:10px;
      padding:10px 0;
      border-bottom:1px solid var(--line);
      font-size:15px;
    }

    .kv:last-child{border-bottom:none}
    .kv-label{
      color:#4f645b;
      display:flex;
      align-items:flex-start;
      gap:10px;
      min-width:0;
    }
    .kv-label .mini{
      width:18px;
      text-align:center;
      color:#52655d;
      flex-shrink:0;
    }
    .kv-value{
      color:#20322d;
      line-height:1.35;
    }

    .status-dot{
      display:inline-block;
      width:12px;
      height:12px;
      border-radius:50%;
      background:#15934f;
      margin-right:10px;
      vertical-align:middle;
    }

    .note{
      background:#dfeeff;
      color:#1f5680;
      padding:14px 16px;
      border-radius:12px;
      font-size:14px;
      line-height:1.45;
      display:flex;
      gap:12px;
      align-items:flex-start;
    }

    .note .ni{
      font-size:20px;
      line-height:1;
      margin-top:1px;
    }

    .muted-small{
      color:#6f7d78;
      font-size:13px;
      margin-top:4px;
    }

    /* responsiveness */
    @media (max-width: 1300px){
      .filters-grid{
        grid-template-columns:repeat(2, minmax(0,1fr));
      }
      .dashboard{
        grid-template-columns:1fr;
      }
    }

    @media (max-width: 900px){
      .app{
        grid-template-columns:1fr;
      }
      .sidebar{
        display:none;
      }
      .topbar{
        padding:16px;
      }
      .content{
        padding:12px;
      }
      .map-box{
        min-height:560px;
      }
      .map-inner{
        height:560px;
      }
    }

    @media (max-width: 620px){
      .filters-grid{
        grid-template-columns:1fr;
      }
      .topbar-title{
        font-size:18px;
      }
      .topbar-right .user-info{
        display:none;
      }
      .legend{
        width:180px;
        padding:12px;
      }
      .kv{
        grid-template-columns:1fr;
      }
    }
  </style>
</head>
<body>
  <div class="app">
    <aside class="sidebar">
      <div class="brand">
        <div class="brand-logo">🍃</div>
        <h1>TuraLimpia</h1>
      </div>

      <nav class="menu">
        <a class="menu-item active" href="#"><span class="icon">🗺️</span><span>Rutas</span></a>
        <a class="menu-item" href="#"><span class="icon">📍</span><span>Paradas</span></a>
        <a class="menu-item" href="#"><span class="icon">👤</span><span>Trabajadores</span></a>
        <a class="menu-item" href="#"><span class="icon">🚛</span><span>Vehículos</span></a>
        <a class="menu-item" href="#"><span class="icon">📄</span><span>Reportes</span></a>
        <div class="menu-sep"></div>
        <a class="menu-item" href="#"><span class="icon">⚙️</span><span>Configuración</span></a>
      </nav>
    </aside>

    <main class="main">
      <header class="topbar">
        <div class="topbar-left">
          <div class="brand-logo" style="background:#e7f4ed;color:var(--green);width:42px;height:42px;">🍃</div>
          <div class="divider"></div>
          <div class="topbar-title">Consulta de rutas de recolección</div>
        </div>

        <div class="topbar-right">
          <div class="bell">🔔</div>
          <div class="user">
            <div class="user-avatar">👤</div>
            <div class="user-info">
              <div class="name">Usuario Municipal</div>
              <div class="role">Administrador</div>
            </div>
            <div style="color:#566b63;">▾</div>
          </div>
        </div>
      </header>

      <div class="content">
        <section class="card pad">
          <h2 class="card-title"><span class="ico">⏷</span><span>Filtros de búsqueda</span></h2>

          <div class="filters-grid">
            <div class="field">
              <label for="zona">1. Zona</label>
              <select id="zona">
                <option value="">Seleccionar zona</option>
                <option value="isla">Isla de Cascajal</option>
                <option value="continente">Continente</option>
              </select>
            </div>

            <div class="field">
              <label for="comuna">2. Comuna</label>
              <select id="comuna" disabled>
                <option value="">Seleccionar comuna</option>
              </select>
            </div>

            <div class="field">
              <label for="barrio">3. Barrio</label>
              <select id="barrio" disabled>
                <option value="">Seleccionar barrio</option>
              </select>
            </div>

            <div class="field">
              <label for="ruta">4. Ruta</label>
              <select id="ruta" disabled>
                <option value="">Seleccionar ruta</option>
              </select>
            </div>
          </div>
        </section>

        <section class="dashboard">
          <div class="map-shell">
            <div class="card pad" style="padding-bottom:14px;">
              <h2 class="card-title"><span class="ico">🗺️</span><span>Mapa de ruta y paradas</span></h2>

              <div class="map-box">
                <div class="map-inner">
                  <div class="legend">
                    <div class="legend-row"><div class="lg-line"></div><div>Ruta seleccionada</div></div>
                    <div class="legend-row"><div class="lg-stop">1</div><div>Parada de recolección</div></div>
                    <div class="legend-row"><div class="lg-hollow"></div><div>Otras paradas</div></div>
                    <div class="legend-row"><div class="lg-area"></div><div>Áreas verdes</div></div>
                    <div class="legend-row"><div class="lg-road"></div><div>Calles principales</div></div>
                  </div>

                  <div class="compass">
                    <div style="font-size:18px;">N</div>
                    <div class="arrow">▲</div>
                  </div>

                  <div class="island">
                    <svg viewBox="0 0 800 600" xmlns="http://www.w3.org/2000/svg">
                      <!-- water text -->
                      <text x="20" y="235" class="water-label">Bahía de</text>
                      <text x="20" y="260" class="water-label">Buenaventura</text>
                      <text x="620" y="540" class="water-label">Estero</text>
                      <text x="600" y="567" class="water-label">San Antonio</text>

                      <!-- outer island -->
                      <path d="M177 109
                               C228 57, 313 40, 404 50
                               C477 58, 571 70, 635 118
                               C679 151, 718 219, 725 273
                               C733 337, 714 405, 661 459
                               C613 507, 529 547, 449 560
                               C354 574, 266 553, 193 508
                               C126 467, 82 408, 69 337
                               C57 270, 71 198, 111 152
                               C128 132, 149 119, 177 109Z"
                            fill="#efefef" stroke="#f7f7f7" stroke-width="8"/>

                      <!-- green islets -->
                      <path d="M266 96 C300 74,330 74,346 98 C320 123,291 126,266 96Z" fill="#d8ebcf"/>
                      <path d="M460 82 C495 70,525 72,542 96 C512 120,480 121,460 82Z" fill="#d8ebcf"/>
                      <path d="M598 124 C632 120,652 136,664 156 C638 173,615 168,598 124Z" fill="#d8ebcf"/>
                      <path d="M72 472 C116 448,162 452,185 486 C142 514,99 514,72 472Z" fill="#d8ebcf"/>

                      <!-- green areas -->
                      <path d="M272 213 C302 191,336 196,349 225 C328 251,291 248,272 213Z" fill="#d7ebd1"/>
                      <path d="M474 272 C505 251,543 260,548 296 C526 320,485 323,474 272Z" fill="#d7ebd1"/>
                      <path d="M312 424 C339 407,370 412,382 437 C362 456,330 455,312 424Z" fill="#d7ebd1"/>

                      <!-- roads -->
                      <g stroke="#ffffff" stroke-width="9" fill="none" stroke-linecap="round" opacity=".95">
                        <path d="M116 260 C202 242,274 228,351 227 C440 226,523 243,657 268"/>
                        <path d="M108 320 C191 301,262 290,346 290 C437 290,526 309,665 337"/>
                        <path d="M140 188 C230 172,305 163,392 165 C485 166,577 179,674 205"/>
                        <path d="M155 393 C257 373,335 362,430 361 C520 360,603 375,679 394"/>
                        <path d="M193 112 C196 213,194 288,196 471"/>
                        <path d="M304 101 C307 200,305 279,308 501"/>
                        <path d="M412 90 C414 191,412 276,416 524"/>
                        <path d="M519 104 C522 192,523 277,524 495"/>
                        <path d="M607 132 C608 219,610 297,612 453"/>
                      </g>

                      <g stroke="#d6dbdc" stroke-width="3" fill="none" opacity=".9">
                        <path d="M102 225 C189 209,289 201,377 202 C499 203,583 214,697 237"/>
                        <path d="M120 282 C204 269,283 260,381 260 C481 260,597 276,690 299"/>
                        <path d="M130 347 C223 332,305 321,402 321 C492 321,584 336,677 357"/>
                        <path d="M171 145 C172 246,171 312,174 462"/>
                        <path d="M247 125 C249 229,250 303,251 482"/>
                        <path d="M359 108 C362 214,362 316,365 521"/>
                        <path d="M463 111 C466 216,468 317,471 516"/>
                        <path d="M573 128 C575 229,577 312,580 489"/>
                        <path d="M647 162 C649 238,652 310,654 438"/>
                      </g>

                      <!-- dynamic route -->
                      <path id="routePath" fill="none" stroke="#11824e" stroke-width="6" stroke-linecap="round" stroke-linejoin="round"></path>

                      <!-- dynamic arrows group -->
                      <g id="routeArrows" fill="#11824e"></g>

                      <!-- labels -->
                      <text id="mapMainLabel" x="330" y="325" class="land-label" font-size="22" font-weight="500">Seleccione una ruta</text>

                      <text id="label1" x="360" y="148" class="neighborhood"></text>
                      <text id="label2" x="535" y="275" class="neighborhood"></text>
                      <text id="label3a" x="228" y="316" class="neighborhood"></text>
                      <text id="label3b" x="228" y="336" class="neighborhood"></text>
                      <text id="label4" x="150" y="415" class="neighborhood"></text>
                      <text id="label5a" x="480" y="410" class="neighborhood"></text>
                      <text id="label5b" x="480" y="430" class="neighborhood"></text>

                      <!-- dynamic stops -->
                      <g id="stopMarkers"></g>
                    </svg>
                  </div>

                  <div class="zoom">
                    <button type="button">+</button>
                    <button type="button">−</button>
                    <button type="button" style="font-size:24px;">⌖</button>
                  </div>

                  <div class="scale">
                    <div>0 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 0,5 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 1 km</div>
                    <div class="scale-bar"><span class="scale-mid"></span></div>
                  </div>
                </div>
              </div>

              <div class="map-status" id="mapStatus">
                Visualización estática de demostración. Selecciona una ruta para ver el recorrido.
              </div>
            </div>
          </div>

          <div class="side-panels">
            <section class="card info-panel">
              <div class="panel-heading"><span style="color:var(--green);">📋</span><span>Información de la ruta</span></div>

              <div class="route-highlight">
                <div class="route-highlight-left"><span>🚛</span><span id="routeNameTop">Sin ruta seleccionada</span></div>
                <div class="route-status" id="routeStateTop">Pendiente</div>
              </div>

              <div id="routeInfoBody">
                <div class="muted-small">Selecciona una ruta para visualizar su información.</div>
              </div>
            </section>

            <section class="card info-panel">
              <div class="panel-heading"><span style="color:var(--green);">📍</span><span>Parada seleccionada</span></div>

              <div class="stop-highlight">
                <div class="stop-highlight-left"><span>📍</span><span id="stopTitleTop">Sin parada</span></div>
                <div style="font-weight:700;color:#4b6056;font-size:14px;" id="stopOrderTop">Orden de visita: --</div>
              </div>

              <div id="stopInfoBody">
                <div class="muted-small">Haz clic en una parada del mapa.</div>
              </div>
            </section>

            <div class="note">
              <div class="ni">ℹ️</div>
              <div>
                <strong>Visualización estática de rutas y paradas.</strong>
                <div class="muted-small" style="color:#4e6c86;margin-top:4px;">
                  No incluye seguimiento en tiempo real. Horarios y recorridos simulados.
                </div>
              </div>
            </div>
          </div>
        </section>
      </div>
    </main>
  </div>

  <script>
    // ================================
    // DATOS BASE
    // ================================
    const BARRIOS = {
      1: ["Nayita", "Centenario", "La Isla"],
      2: ["Vientos libre Norte", "Montechino", "El Firme", "Capricho", "F. Paula Santander", "El Jorge", "Borrero Olano", "Santa Rosa"],
      3: ["Alfonso López", "Alberto Lleras"],
      4: ["San José", "Muro Yusty", "Vientos Libres Sur", "Campo Alegre", "La Playita"],
      5: ["Pascual de Andagoya", "La Palera", "Punta del Este", "Santa Cruz", "La Inmaculada", "Santa Fe", "Miramar"],
      6: ["El Porvenir", "El Campín", "El Jardín", "Brisas del Mar", "Miraflores", "El Oriente", "Isla de la Paz", "Barrio Naval", "Bosque Municipal", "La Comuna"],
      7: ["Kennedy", "San Luis", "San Francisco", "Municipal", "Juan 23", "Eucarístico", "Rockefeller", "14 de Julio"],
      8: ["Modelo", "María Eugenia", "Bella Vista", "El Cristal", "Transformación", "Los Laureles", "Ciudadela Colpuertos"],
      9: ["San Buenaventura", "Doña Cesi", "12 de Abril", "6 de Enero", "Turbay Ayala", "Nueva Buenaventura"],
      10: ["Independencia", "Urbanización Acuarela", "Carlos Holmes", "Las Américas", "Bolívar", "Camilo Torres", "Urbanización Bahía", "El Progreso", "La Fortaleza", "Urbanización Comunitaria", "Los Álamos", "Urbanización Confamar", "Bello Horizonte"],
      11: ["El Dorado", "Antonio Nariño", "Cascajal", "El Carmen", "Nueva Colombia", "Los Pinos", "Panamericano", "Gran Colombiana", "Cristóbal Colon", "El Futuro"],
      12: ["Puerta del Mar", "Alfonso López M.", "Unión de Vivienda", "El Triunfo", "20 de Julio", "El Reten", "Nueva Granada", "Las Palmas", "Nueva Frontera", "Matia Mulumba", "Cabal Pombo", "El Caldas", "La Libertad", "La Gloria", "La Unión", "El Ruiz", "Rafael Uribe", "El Cambio", "Nuevo Amanecer", "La Campiña", "Vista Hermosa", "Jorge E. Gaitán", "La Dignidad", "Brisas del Pacífico", "12 de Octubre"]
    };

    function formatHour(totalMinutes){
      const h = Math.floor(totalMinutes / 60);
      const m = totalMinutes % 60;
      const period = h >= 12 ? "p. m." : "a. m.";
      const hour12 = ((h + 11) % 12) + 1;
      return `${String(hour12).padStart(2,"0")}:${String(m).padStart(2,"0")} ${period}`;
    }

    function normalizeCode(n){
      return String(n).padStart(2,"0");
    }

    // crear rutas simuladas agrupando barrios de 5 en 5
    const RUTAS = [];
    Object.entries(BARRIOS).forEach(([comunaStr, barrios]) => {
      const comuna = Number(comunaStr);
      const zona = comuna <= 5 ? "isla" : "continente";

      for(let i=0; i<barrios.length; i+=5){
        const group = barrios.slice(i, i+5);
        const routeNum = Math.floor(i/5) + 1;
        const code = `C${normalizeCode(comuna)}-R${normalizeCode(routeNum)}`;

        const frequencyOptions = [
          "Lunes, miércoles y viernes",
          "Martes, jueves y sábado"
        ];
        const startOptions = [6*60, 10*60, 14*60]; // 6 am, 10 am, 2 pm
        const freq = frequencyOptions[(comuna + routeNum) % 2];
        const start = startOptions[(comuna + routeNum - 1) % 3];
        const end = start + 240;

        const paradas = group.map((b, idx) => ({
          orden: idx + 1,
          barrio: b,
          hora: formatHour(start + 20 + idx * 40),
          direccion: "Por definir",
          coordsText: "Pendientes de integrar"
        }));

        RUTAS.push({
          id: code,
          nombre: `Ruta de ejemplo ${code}`,
          comuna,
          zona,
          barrioPrincipal: group[0],
          barriosAsociados: group,
          frecuencia: freq,
          horario: `${formatHour(start)} – ${formatHour(end)}`,
          servicio: "Recolección ordinaria",
          estado: "Programada",
          paradas
        });
      }
    });

    // ================================
    // DOM
    // ================================
    const zonaSel = document.getElementById('zona');
    const comunaSel = document.getElementById('comuna');
    const barrioSel = document.getElementById('barrio');
    const rutaSel = document.getElementById('ruta');

    const routeNameTop = document.getElementById('routeNameTop');
    const routeStateTop = document.getElementById('routeStateTop');
    const routeInfoBody = document.getElementById('routeInfoBody');
    const stopTitleTop = document.getElementById('stopTitleTop');
    const stopOrderTop = document.getElementById('stopOrderTop');
    const stopInfoBody = document.getElementById('stopInfoBody');
    const mapStatus = document.getElementById('mapStatus');

    const routePath = document.getElementById('routePath');
    const routeArrows = document.getElementById('routeArrows');
    const stopMarkers = document.getElementById('stopMarkers');

    const mapMainLabel = document.getElementById('mapMainLabel');
    const label1 = document.getElementById('label1');
    const label2 = document.getElementById('label2');
    const label3a = document.getElementById('label3a');
    const label3b = document.getElementById('label3b');
    const label4 = document.getElementById('label4');
    const label5a = document.getElementById('label5a');
    const label5b = document.getElementById('label5b');

    function setOptions(select, placeholder, items){
      select.innerHTML = `<option value="">${placeholder}</option>`;
      items.forEach(item => {
        const opt = document.createElement('option');
        opt.value = item.value;
        opt.textContent = item.label;
        select.appendChild(opt);
      });
      select.disabled = items.length === 0;
    }

    function clearRouteView(){
      routeNameTop.textContent = 'Sin ruta seleccionada';
      routeStateTop.textContent = 'Pendiente';
      routeInfoBody.innerHTML = `<div class="muted-small">Selecciona una ruta para visualizar su información.</div>`;
      stopTitleTop.textContent = 'Sin parada';
      stopOrderTop.textContent = 'Orden de visita: --';
      stopInfoBody.innerHTML = `<div class="muted-small">Haz clic en una parada del mapa.</div>`;
      routePath.setAttribute('d','');
      routeArrows.innerHTML = '';
      stopMarkers.innerHTML = '';
      mapStatus.textContent = 'Visualización estática de demostración. Selecciona una ruta para ver el recorrido.';
      mapMainLabel.textContent = 'Seleccione una ruta';

      [label1,label2,label3a,label3b,label4,label5a,label5b].forEach(el => el.textContent = '');
    }

    function kvRow(icon, label, value){
      return `
        <div class="kv">
          <div class="kv-label"><span class="mini">${icon}</span><span>${label}</span></div>
          <div class="kv-value">${value}</div>
        </div>
      `;
    }

    function zonaBonita(z){
      return z === 'isla' ? 'Isla de Cascajal' : 'Continente';
    }

    // route geometries depending on number of stops
    const routeShapes = {
      2: [
        [372,160],[566,270]
      ],
      3: [
        [356,150],[570,255],[473,465]
      ],
      4: [
        [360,150],[575,265],[465,476],[188,335]
      ],
      5: [
        [360,150],[575,265],[465,476],[188,335],[330,265]
      ]
    };

    function buildPath(coords){
      if(!coords.length) return '';
      return coords.map((p,i)=> `${i===0?'M':'L'}${p[0]} ${p[1]}`).join(' ');
    }

    function addArrow(x1,y1,x2,y2){
      const angle = Math.atan2(y2-y1, x2-x1) * 180 / Math.PI;
      const mx = (x1+x2)/2;
      const my = (y1+y2)/2;
      const ns = "http://www.w3.org/2000/svg";
      const poly = document.createElementNS(ns,'polygon');
      poly.setAttribute('points','0,-7 14,0 0,7 4,0');
      poly.setAttribute('transform',`translate(${mx},${my}) rotate(${angle})`);
      poly.setAttribute('fill','#11824e');
      routeArrows.appendChild(poly);
    }

    function drawRoute(route){
      stopMarkers.innerHTML = '';
      routeArrows.innerHTML = '';

      const coords = routeShapes[route.paradas.length] || routeShapes[4];
      routePath.setAttribute('d', buildPath(coords));

      for(let i=0;i<coords.length-1;i++){
        addArrow(coords[i][0],coords[i][1],coords[i+1][0],coords[i+1][1]);
      }

      const mapLabels = route.barriosAsociados.slice(0,5);
      label1.textContent = mapLabels[0] || '';
      label2.textContent = mapLabels[1] || '';
      label3a.textContent = mapLabels[2] ? splitLabel(mapLabels[2])[0] : '';
      label3b.textContent = mapLabels[2] ? splitLabel(mapLabels[2])[1] : '';
      label4.textContent = mapLabels[3] || '';
      label5a.textContent = mapLabels[4] ? splitLabel(mapLabels[4])[0] : '';
      label5b.textContent = mapLabels[4] ? splitLabel(mapLabels[4])[1] : '';

      mapMainLabel.textContent = route.zona === 'isla' ? 'Isla de Cascajal' : `Comuna ${route.comuna}`;

      route.paradas.forEach((parada, idx) => {
        const [x,y] = coords[idx];
        const g = makeStopMarker(x,y,parada,route);
        stopMarkers.appendChild(g);
      });

      const first = stopMarkers.querySelector('.stop-marker');
      if(first) first.dispatchEvent(new Event('click'));
    }

    function splitLabel(text){
      if(text.length <= 14) return [text,''];
      const words = text.split(' ');
      if(words.length === 1) return [text,''];
      const half = Math.ceil(words.length / 2);
      return [words.slice(0,half).join(' '), words.slice(half).join(' ')];
    }

    function makeStopMarker(x,y,parada,route){
      const ns = "http://www.w3.org/2000/svg";
      const g = document.createElementNS(ns,'g');
      g.setAttribute('class','stop-marker');
      g.style.cursor = 'pointer';

      const circle = document.createElementNS(ns,'circle');
      circle.setAttribute('cx',x);
      circle.setAttribute('cy',y);
      circle.setAttribute('r',18);
      circle.setAttribute('fill','#129253');
      circle.setAttribute('stroke','#ffffff');
      circle.setAttribute('stroke-width','5');

      const text = document.createElementNS(ns,'text');
      text.setAttribute('x',x);
      text.setAttribute('y',y+6);
      text.setAttribute('text-anchor','middle');
      text.setAttribute('font-size','20');
      text.setAttribute('font-weight','800');
      text.setAttribute('fill','#fff');
      text.textContent = parada.orden;

      g.appendChild(circle);
      g.appendChild(text);

      g.addEventListener('click',() => {
        [...stopMarkers.children].forEach(el => {
          el.querySelector('circle').setAttribute('fill','#129253');
        });
        circle.setAttribute('fill','#0d7a45');

        stopTitleTop.textContent = `Parada ${parada.orden}`;
        stopOrderTop.textContent = `Orden de visita: ${parada.orden} de ${route.paradas.length}`;

        stopInfoBody.innerHTML =
          kvRow('🏠','Barrio de referencia', parada.barrio) +
          kvRow('🕒','Hora estimada', parada.hora) +
          kvRow('📍','Dirección o referencia', parada.direccion) +
          kvRow('🗺️','Coordenadas geográficas', parada.coordsText);
      });

      return g;
    }

    function showRoute(route){
      routeNameTop.textContent = route.nombre;
      routeStateTop.textContent = route.estado;

      routeInfoBody.innerHTML =
        kvRow('🏷️','Código', route.id) +
        kvRow('📍','Zona', zonaBonita(route.zona)) +
        kvRow('🏢','Comuna', `Comuna ${route.comuna}`) +
        kvRow('🏠','Barrio seleccionado', barrioSel.value || route.barrioPrincipal) +
        kvRow('👥','Barrios asociados', route.barriosAsociados.join(', ')) +
        kvRow('📅','Frecuencia', route.frecuencia) +
        kvRow('🕒','Horario estimado', route.horario) +
        kvRow('🚛','Tipo de servicio', route.servicio) +
        kvRow('✅','Estado', `<span class="status-dot"></span>${route.estado}`);

      mapStatus.textContent = 'Recorrido y horarios simulados para el prototipo visual.';
      drawRoute(route);
    }

    zonaSel.addEventListener('change', () => {
      const zona = zonaSel.value;
      let comunas = [];
      if(zona === 'isla') comunas = [1,2,3,4,5];
      if(zona === 'continente') comunas = [6,7,8,9,10,11,12];

      setOptions(comunaSel, 'Seleccionar comuna', comunas.map(c => ({
        value:String(c),
        label:`Comuna ${c}`
      })));

      setOptions(barrioSel, 'Seleccionar barrio', []);
      setOptions(rutaSel, 'Seleccionar ruta', []);
      clearRouteView();
    });

    comunaSel.addEventListener('change', () => {
      const comuna = Number(comunaSel.value);
      const barrios = BARRIOS[comuna] || [];
      setOptions(barrioSel, 'Seleccionar barrio', barrios.map(b => ({
        value:b,
        label:b
      })));
      setOptions(rutaSel, 'Seleccionar ruta', []);
      clearRouteView();
    });

    barrioSel.addEventListener('change', () => {
      const comuna = Number(comunaSel.value);
      const barrio = barrioSel.value;

      const routes = RUTAS.filter(r =>
        r.comuna === comuna &&
        r.barriosAsociados.includes(barrio)
      );

      setOptions(rutaSel, 'Seleccionar ruta', routes.map(r => ({
        value:r.id,
        label:r.id
      })));

      clearRouteView();

      if(routes.length === 1){
        rutaSel.value = routes[0].id;
        showRoute(routes[0]);
      }
    });

    rutaSel.addEventListener('change', () => {
      const route = RUTAS.find(r => r.id === rutaSel.value);
      if(!route){
        clearRouteView();
        return;
      }
      showRoute(route);
    });

    clearRouteView();
  </script>
</body>
</html>
