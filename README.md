<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">

  <title>ORB — Ourlboy</title>

  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;700;900&display=swap" rel="stylesheet">

  <style>

    *{
      margin:0;
      padding:0;
      box-sizing:border-box;
      font-family:'Inter',sans-serif;
    }

    body{
      background:#050816;
      color:white;
      overflow-x:hidden;
    }

    body::before{
      content:'';
      position:fixed;
      inset:0;
      background:
      radial-gradient(circle at top, rgba(0,140,255,0.18), transparent 35%),
      radial-gradient(circle at bottom, rgba(0,255,255,0.08), transparent 35%);
      z-index:-1;
    }

    .container{
      width:90%;
      max-width:1300px;
      margin:auto;
    }

    header{
      position:fixed;
      width:100%;
      top:0;
      z-index:1000;
      backdrop-filter:blur(14px);
      background:rgba(0,0,0,0.3);
      border-bottom:1px solid rgba(255,255,255,0.08);
    }

    nav{
      display:flex;
      justify-content:space-between;
      align-items:center;
      padding:20px 0;
    }

    .logo{
      display:flex;
      align-items:center;
      gap:14px;
    }

    .orb-icon{
      width:52px;
      height:52px;
      border-radius:50%;
      background:linear-gradient(135deg,#00d9ff,#005eff);
      display:flex;
      align-items:center;
      justify-content:center;
      font-weight:900;
      font-size:24px;
      box-shadow:0 0 35px rgba(0,200,255,0.5);
    }

    .logo h1{
      font-size:24px;
      font-weight:900;
    }

    .logo p{
      font-size:12px;
      color:#7f8ca8;
    }

    .menu{
      display:flex;
      gap:40px;
    }

    .menu a{
      text-decoration:none;
      color:#c6d0e5;
      transition:0.3s;
    }

    .menu a:hover{
      color:#00d9ff;
    }

    .btn{
      padding:14px 28px;
      border-radius:18px;
      border:none;
      cursor:pointer;
      font-weight:700;
      transition:0.3s;
    }

    .btn-primary{
      background:linear-gradient(90deg,#00d9ff,#005eff);
      color:white;
      box-shadow:0 0 35px rgba(0,200,255,0.35);
    }

    .btn-primary:hover{
      transform:translateY(-2px) scale(1.03);
    }

    .btn-secondary{
      background:rgba(255,255,255,0.05);
      border:1px solid rgba(255,255,255,0.08);
      color:white;
    }

    .hero{
      min-height:100vh;
      display:flex;
      align-items:center;
      padding-top:100px;
    }

    .hero-content{
      display:grid;
      grid-template-columns:1fr 1fr;
      gap:80px;
      align-items:center;
    }

    .tag{
      display:inline-block;
      padding:12px 20px;
      border-radius:999px;
      background:rgba(0,217,255,0.1);
      border:1px solid rgba(0,217,255,0.2);
      color:#72eaff;
      margin-bottom:30px;
    }

    .hero h2{
      font-size:84px;
      line-height:0.95;
      font-weight:900;
      margin-bottom:30px;
    }

    .gradient{
      background:linear-gradient(90deg,#00d9ff,#005eff);
      -webkit-background-clip:text;
      -webkit-text-fill-color:transparent;
    }

    .hero p{
      color:#94a3b8;
      font-size:20px;
      line-height:1.8;
      margin-bottom:40px;
    }

    .buttons{
      display:flex;
      gap:20px;
      flex-wrap:wrap;
    }

    .orb-visual{
      display:flex;
      justify-content:center;
      align-items:center;
      position:relative;
    }

    .orb{
      width:420px;
      height:420px;
      border-radius:50%;
      position:relative;
      border:1px solid rgba(0,217,255,0.15);
      display:flex;
      justify-content:center;
      align-items:center;
      animation:pulse 4s infinite ease-in-out;
    }

    .orb::before{
      content:'';
      position:absolute;
      inset:40px;
      border-radius:50%;
      border:1px solid rgba(255,255,255,0.08);
    }

    .orb::after{
      content:'';
      position:absolute;
      inset:90px;
      border-radius:50%;
      border:1px solid rgba(0,217,255,0.2);
    }

    .core{
      width:170px;
      height:170px;
      border-radius:50%;
      background:linear-gradient(135deg,#00d9ff,#005eff);
      display:flex;
      align-items:center;
      justify-content:center;
      font-size:72px;
      font-weight:900;
      box-shadow:0 0 60px rgba(0,200,255,0.5);
    }

    @keyframes pulse{
      0%{transform:scale(1);}
      50%{transform:scale(1.03);}
      100%{transform:scale(1);}
    }

    .stats{
      padding:80px 0;
    }

    .stats-grid{
      display:grid;
      grid-template-columns:repeat(4,1fr);
      gap:24px;
    }

    .card{
      background:rgba(255,255,255,0.03);
      border:1px solid rgba(255,255,255,0.08);
      border-radius:28px;
      padding:40px;
      backdrop-filter:blur(12px);
    }

    .card h3{
      font-size:42px;
      color:#00d9ff;
      margin-bottom:10px;
    }

    .card p{
      color:#94a3b8;
    }

    section{
      padding:120px 0;
    }

    .section-title{
      font-size:58px;
      font-weight:900;
      margin-bottom:30px;
    }

    .section-subtitle{
      color:#94a3b8;
      font-size:20px;
      line-height:1.8;
      max-width:800px;
    }

    .features{
      display:grid;
      grid-template-columns:repeat(3,1fr);
      gap:30px;
      margin-top:80px;
    }

    .feature{
      padding:40px;
      border-radius:30px;
      background:rgba(255,255,255,0.03);
      border:1px solid rgba(255,255,255,0.08);
      transition:0.3s;
    }

    .feature:hover{
      transform:translateY(-5px);
      border-color:rgba(0,217,255,0.3);
    }

    .feature-box{
      width:70px;
      height:70px;
      border-radius:22px;
      background:rgba(0,217,255,0.08);
      border:1px solid rgba(0,217,255,0.2);
      margin-bottom:30px;
    }

    .feature h4{
      font-size:28px;
      margin-bottom:20px;
    }

    .feature p{
      color:#94a3b8;
      line-height:1.8;
    }

    footer{
      border-top:1px solid rgba(255,255,255,0.08);
      padding:60px 0;
      text-align:center;
      color:#7f8ca8;
    }

    @media(max-width:1100px){

      .hero-content{
        grid-template-columns:1fr;
        text-align:center;
      }

      .stats-grid{
        grid-template-columns:1fr 1fr;
      }

      .features{
        grid-template-columns:1fr;
      }

      .hero h2{
        font-size:62px;
      }

      .menu{
        display:none;
      }

    }

    @media(max-width:700px){

      .hero h2{
        font-size:48px;
      }

      .orb{
        width:300px;
        height:300px;
      }

      .core{
        width:120px;
        height:120px;
        font-size:52px;
      }

      .stats-grid{
        grid-template-columns:1fr;
      }

      .section-title{
        font-size:42px;
      }

    }

  </style>
</head>

<body>

<header>
  <div class="container">

    <nav>

      <div class="logo">

        <div class="orb-icon">
          O
        </div>

        <div>
          <h1>ORB</h1>
          <p>Ourlboy</p>
        </div>

      </div>

      <div class="menu">
        <a href="#">Visão</a>
        <a href="#">Ecossistema</a>
        <a href="#">Roadmap</a>
        <a href="#">Tokenomics</a>
      </div>

      <button class="btn btn-primary">
        Entrar na Comunidade
      </button>

    </nav>

  </div>
</header>

<section class="hero">

  <div class="container">

    <div class="hero-content">

      <div>

        <div class="tag">
          Infraestrutura Web3 de Nova Geração
        </div>

        <h2>
          Powering
          <span class="gradient">
            Intelligent
          </span>
          Communities
        </h2>

        <p>
          A ORB está construindo o futuro dos ecossistemas digitais inteligentes através de blockchain, inteligência artificial, games e comunidades descentralizadas.
        </p>

        <div class="buttons">

          <button class="btn btn-primary">
            Explorar Ecossistema
          </button>

          <button class="btn btn-secondary">
            Ler Whitepaper
          </button>

        </div>

      </div>

      <div class="orb-visual">

        <div class="orb">

          <div class="core">
            O
          </div>

        </div>

      </div>

    </div>

  </div>

</section>

<section class="stats">

  <div class="container">

    <div class="stats-grid">

      <div class="card">
        <h3>50M</h3>
        <p>Total de ORB</p>
      </div>

      <div class="card">
        <h3>Polygon</h3>
        <p>Blockchain Oficial</p>
      </div>

      <div class="card">
        <h3>IA + Games</h3>
        <p>Infraestrutura Principal</p>
      </div>

      <div class="card">
        <h3>Comunidade</h3>
        <p>Governança Descentralizada</p>
      </div>

    </div>

  </div>

</section>

<section>

  <div class="container">

    <h2 class="section-title">
      Construindo a Infraestrutura para Comunidades Inteligentes
    </h2>

    <p class="section-subtitle">
      A ORB combina blockchain, inteligência artificial, games e sistemas descentralizados para criar ecossistemas digitais escaláveis para a próxima geração da internet.
    </p>

    <div class="features">

      <div class="feature">

        <div class="feature-box"></div>

        <h4>Inteligência Artificial</h4>

        <p>
          Sistemas inteligentes, automações, experiências digitais avançadas e infraestrutura de IA integrada.
        </p>

      </div>

      <div class="feature">

        <div class="feature-box"></div>

        <h4>Gaming Ecosystems</h4>

        <p>
          Sistemas de recompensa, identidade digital, gamificação e participação comunitária.
        </p>

      </div>

      <div class="feature">

        <div class="feature-box"></div>

        <h4>Comunidades Descentralizadas</h4>

        <p>
          Governança transparente, economias sustentáveis e participação