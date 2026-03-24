[index.html.html](https://github.com/user-attachments/files/26226202/index.html.html)
<!DOCTYPE html>
<html lang="pt">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Edgar da Silva Coutinho — Portfólio</title>
  <link href="https://fonts.googleapis.com/css2?family=Cormorant+Garamond:ital,wght@0,300;0,400;0,600;1,300&family=DM+Sans:wght@300;400;500&display=swap" rel="stylesheet"/>
  <style>
    :root {
      --cream: #f5f0e8;
      --ink: #1a1612;
      --gold: #b8976a;
      --gold-light: #d4b896;
      --muted: #6b5f52;
      --border: rgba(184,151,106,0.25);
      --bg-card: rgba(255,255,255,0.55);
    }

    *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

    html { scroll-behavior: smooth; }

    body {
      background-color: var(--cream);
      color: var(--ink);
      font-family: 'DM Sans', sans-serif;
      font-weight: 300;
      line-height: 1.7;
      min-height: 100vh;
      overflow-x: hidden;
    }

    /* Grain texture overlay */
    body::before {
      content: '';
      position: fixed;
      inset: 0;
      background-image: url("data:image/svg+xml,%3Csvg viewBox='0 0 256 256' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='noise'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.9' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23noise)' opacity='0.04'/%3E%3C/svg%3E");
      pointer-events: none;
      z-index: 999;
      opacity: 0.4;
    }

    /* Decorative background shapes */
    .bg-decoration {
      position: fixed;
      border-radius: 50%;
      filter: blur(80px);
      pointer-events: none;
      z-index: 0;
    }
    .bg-decoration.one {
      width: 500px; height: 500px;
      top: -150px; right: -100px;
      background: radial-gradient(circle, rgba(184,151,106,0.12), transparent 70%);
    }
    .bg-decoration.two {
      width: 400px; height: 400px;
      bottom: 100px; left: -100px;
      background: radial-gradient(circle, rgba(184,151,106,0.08), transparent 70%);
    }

    /* ─── LAYOUT ─── */
    .container {
      max-width: 860px;
      margin: 0 auto;
      padding: 0 2rem;
      position: relative;
      z-index: 1;
    }

    /* ─── HEADER / HERO ─── */
    header {
      padding: 5rem 0 3rem;
      text-align: center;
      animation: fadeUp 0.9s ease both;
    }

    .eyebrow {
      font-family: 'DM Sans', sans-serif;
      font-size: 0.72rem;
      font-weight: 500;
      letter-spacing: 0.22em;
      text-transform: uppercase;
      color: var(--gold);
      margin-bottom: 1.2rem;
    }

    h1 {
      font-family: 'Cormorant Garamond', serif;
      font-size: clamp(2.8rem, 7vw, 4.8rem);
      font-weight: 300;
      line-height: 1.05;
      color: var(--ink);
      margin-bottom: 0.4rem;
    }

    h1 em {
      font-style: italic;
      color: var(--gold);
    }

    .subtitle {
      font-size: 0.92rem;
      color: var(--muted);
      letter-spacing: 0.04em;
      margin-top: 1rem;
      margin-bottom: 2rem;
    }

    .divider-ornament {
      display: flex;
      align-items: center;
      justify-content: center;
      gap: 0.8rem;
      margin: 2rem 0;
    }
    .divider-ornament::before,
    .divider-ornament::after {
      content: '';
      display: block;
      width: 60px;
      height: 1px;
      background: var(--gold-light);
    }
    .divider-ornament span {
      color: var(--gold);
      font-size: 1rem;
    }

    /* ─── SECTION TITLES ─── */
    .section-label {
      font-family: 'DM Sans', sans-serif;
      font-size: 0.68rem;
      font-weight: 500;
      letter-spacing: 0.2em;
      text-transform: uppercase;
      color: var(--gold);
      margin-bottom: 0.6rem;
    }

    h2 {
      font-family: 'Cormorant Garamond', serif;
      font-size: clamp(1.8rem, 4vw, 2.6rem);
      font-weight: 300;
      color: var(--ink);
      margin-bottom: 1.5rem;
    }

    /* ─── SECTIONS ─── */
    section {
      padding: 3.5rem 0;
      border-top: 1px solid var(--border);
      animation: fadeUp 0.8s ease both;
    }

    section:nth-child(2) { animation-delay: 0.1s; }
    section:nth-child(3) { animation-delay: 0.2s; }
    section:nth-child(4) { animation-delay: 0.3s; }
    section:nth-child(5) { animation-delay: 0.4s; }

    /* ─── SOBRE ─── */
    .about-grid {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 3rem;
      align-items: start;
    }

    .about-text p {
      font-size: 0.95rem;
      color: #3a322a;
      margin-bottom: 1rem;
    }

    .about-details {
      display: flex;
      flex-direction: column;
      gap: 1rem;
    }

    .detail-item {
      display: flex;
      flex-direction: column;
      gap: 0.1rem;
      padding: 0.9rem 1.2rem;
      background: var(--bg-card);
      border: 1px solid var(--border);
      border-radius: 4px;
      backdrop-filter: blur(4px);
    }

    .detail-item .label {
      font-size: 0.65rem;
      letter-spacing: 0.15em;
      text-transform: uppercase;
      color: var(--gold);
      font-weight: 500;
    }

    .detail-item .value {
      font-size: 0.88rem;
      color: var(--ink);
    }

    /* ─── COMPETÊNCIAS ─── */
    .skills-grid {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 1rem;
    }

    .skill-card {
      padding: 1.2rem 1.4rem;
      background: var(--bg-card);
      border: 1px solid var(--border);
      border-radius: 4px;
      backdrop-filter: blur(4px);
      transition: border-color 0.3s, transform 0.3s;
    }

    .skill-card:hover {
      border-color: var(--gold-light);
      transform: translateY(-2px);
    }

    .skill-card .skill-title {
      font-family: 'Cormorant Garamond', serif;
      font-size: 1.1rem;
      font-weight: 400;
      color: var(--ink);
      margin-bottom: 0.4rem;
    }

    .skill-card p {
      font-size: 0.8rem;
      color: var(--muted);
      line-height: 1.5;
    }

    /* ─── EXPERIÊNCIA ─── */
    .timeline {
      position: relative;
      padding-left: 1.8rem;
    }

    .timeline::before {
      content: '';
      position: absolute;
      left: 0;
      top: 6px;
      bottom: 6px;
      width: 1px;
      background: var(--border);
    }

    .timeline-item {
      position: relative;
      margin-bottom: 2.2rem;
    }

    .timeline-item::before {
      content: '';
      position: absolute;
      left: -1.8rem;
      top: 7px;
      width: 7px;
      height: 7px;
      border-radius: 50%;
      background: var(--gold);
      border: 2px solid var(--cream);
      box-shadow: 0 0 0 1px var(--gold);
    }

    .timeline-item .period {
      font-size: 0.7rem;
      letter-spacing: 0.12em;
      text-transform: uppercase;
      color: var(--gold);
      font-weight: 500;
      margin-bottom: 0.2rem;
    }

    .timeline-item h3 {
      font-family: 'Cormorant Garamond', serif;
      font-size: 1.25rem;
      font-weight: 400;
      color: var(--ink);
    }

    .timeline-item .company {
      font-size: 0.82rem;
      color: var(--muted);
      margin-bottom: 0.5rem;
    }

    .timeline-item p {
      font-size: 0.88rem;
      color: #4a3f35;
    }

    /* ─── FORMAÇÃO ─── */
    .education-list {
      display: flex;
      flex-direction: column;
      gap: 1rem;
    }

    .edu-item {
      display: flex;
      gap: 1.5rem;
      align-items: flex-start;
      padding: 1.1rem 1.4rem;
      background: var(--bg-card);
      border: 1px solid var(--border);
      border-radius: 4px;
      backdrop-filter: blur(4px);
    }

    .edu-year {
      font-family: 'Cormorant Garamond', serif;
      font-size: 1.5rem;
      font-weight: 300;
      color: var(--gold-light);
      min-width: 60px;
      line-height: 1;
    }

    .edu-info h4 {
      font-family: 'Cormorant Garamond', serif;
      font-size: 1.1rem;
      font-weight: 400;
      color: var(--ink);
    }

    .edu-info span {
      font-size: 0.8rem;
      color: var(--muted);
    }

    /* ─── IDIOMAS ─── */
    .languages-row {
      display: flex;
      gap: 1rem;
      flex-wrap: wrap;
    }

    .lang-chip {
      display: flex;
      flex-direction: column;
      gap: 0.2rem;
      padding: 0.8rem 1.4rem;
      background: var(--bg-card);
      border: 1px solid var(--border);
      border-radius: 4px;
      backdrop-filter: blur(4px);
      min-width: 120px;
    }

    .lang-chip .lang-name {
      font-family: 'Cormorant Garamond', serif;
      font-size: 1.1rem;
      color: var(--ink);
    }

    .lang-chip .lang-level {
      font-size: 0.7rem;
      letter-spacing: 0.1em;
      text-transform: uppercase;
      color: var(--gold);
      font-weight: 500;
    }

    /* ─── LINKEDIN BADGE ─── */
    .linkedin-section {
      text-align: center;
      padding: 3rem 0;
      border-top: 1px solid var(--border);
    }

    .badge-wrapper {
      display: inline-flex;
      flex-direction: column;
      align-items: center;
      gap: 1rem;
      margin-top: 1.5rem;
    }

    .badge-wrapper p {
      font-size: 0.82rem;
      color: var(--muted);
      letter-spacing: 0.05em;
    }

    /* ─── FOOTER ─── */
    footer {
      text-align: center;
      padding: 2.5rem 0;
      border-top: 1px solid var(--border);
      font-size: 0.78rem;
      color: var(--muted);
      letter-spacing: 0.06em;
    }

    footer a {
      color: var(--gold);
      text-decoration: none;
    }

    /* ─── ANIMATIONS ─── */
    @keyframes fadeUp {
      from { opacity: 0; transform: translateY(22px); }
      to   { opacity: 1; transform: translateY(0); }
    }

    /* ─── RESPONSIVE ─── */
    @media (max-width: 640px) {
      .about-grid { grid-template-columns: 1fr; gap: 2rem; }
      .skills-grid { grid-template-columns: 1fr 1fr; }
      h1 { font-size: 2.6rem; }
    }

    @media (max-width: 420px) {
      .skills-grid { grid-template-columns: 1fr; }
    }
  </style>
</head>
<body>

  <!-- Background decorations -->
  <div class="bg-decoration one"></div>
  <div class="bg-decoration two"></div>

  <div class="container">

    <!-- HERO -->
    <header>
      <p class="eyebrow">Portfólio Profissional</p>
      <h1>Edgar da <em>Silva</em><br>Coutinho</h1>
      <p class="subtitle">Supervisão Operacional &nbsp;·&nbsp; Apoio ao Cliente &nbsp;·&nbsp; Gestão Administrativa &nbsp;·&nbsp; Direito</p>
      <div class="divider-ornament"><span>✦</span></div>
      <p style="font-size:0.9rem; color:var(--muted); max-width:520px; margin:0 auto;">
        Profissional baseado em Maputo, Moçambique, com sólida experiência em atendimento ao cliente, supervisão e administração — aliada à formação académica em Direito.
      </p>
    </header>

    <!-- SOBRE -->
    <section>
      <p class="section-label">Perfil</p>
      <h2>Sobre Mim</h2>
      <div class="about-grid">
        <div class="about-text">
          <p>
            Com cerca de quatro anos de experiência operacional na Primeira Aposta Moçambique, desenvolvi competências sólidas em supervisão de equipas, gestão de reclamações e suporte ao cliente em ambientes de alto volume.
          </p>
          <p>
            Paralelamente à actividade profissional, prossigo estudos em Direito, o que fortalece a minha capacidade analítica, de redacção e de resolução estruturada de problemas — valências cada vez mais relevantes no mercado de trabalho actual.
          </p>
          <p>
            Sou orientado para resultados, comprometido com a excelência no serviço e com forte aptidão para trabalhar tanto de forma autónoma como integrado em equipas multidisciplinares.
          </p>
        </div>
        <div class="about-details">
          <div class="detail-item">
            <span class="label">Localização</span>
            <span class="value">Maputo, Moçambique</span>
          </div>
          <div class="detail-item">
            <span class="label">Área Profissional</span>
            <span class="value">Atendimento ao Cliente / Operações</span>
          </div>
          <div class="detail-item">
            <span class="label">Formação Académica</span>
            <span class="value">Licenciatura em Direito (em curso)</span>
          </div>
          <div class="detail-item">
            <span class="label">Ferramentas</span>
            <span class="value">FreshService · Betobet · Primavera</span>
          </div>
        </div>
      </div>
    </section>

    <!-- COMPETÊNCIAS -->
    <section>
      <p class="section-label">Competências</p>
      <h2>Áreas de Actuação</h2>
      <div class="skills-grid">
        <div class="skill-card">
          <p class="skill-title">Suporte ao Cliente</p>
          <p>Atendimento inbound/outbound, gestão de reclamações, satisfação do utilizador e suporte multicanal.</p>
        </div>
        <div class="skill-card">
          <p class="skill-title">Supervisão Operacional</p>
          <p>Coordenação de equipas, controlo de qualidade, reporte de métricas e gestão de processos.</p>
        </div>
        <div class="skill-card">
          <p class="skill-title">Administração</p>
          <p>Organização documental, arquivo, apoio à gestão e elaboração de relatórios.</p>
        </div>
        <div class="skill-card">
          <p class="skill-title">Análise de Dados</p>
          <p>Tratamento básico de dados, elaboração de tabelas e relatórios de acompanhamento.</p>
        </div>
        <div class="skill-card">
          <p class="skill-title">Direito & Compliance</p>
          <p>Conhecimento do ordenamento jurídico moçambicano, CRM/2004 e legislação complementar.</p>
        </div>
        <div class="skill-card">
          <p class="skill-title">Relações Públicas</p>
          <p>Comunicação institucional, liderança de equipas e gestão de stakeholders internos e externos.</p>
        </div>
      </div>
    </section>

    <!-- EXPERIÊNCIA -->
    <section>
      <p class="section-label">Percurso</p>
      <h2>Experiência Profissional</h2>
      <div class="timeline">
        <div class="timeline-item">
          <p class="period">2020 — Presente</p>
          <h3>Supervisor Operacional</h3>
          <p class="company">Primeira Aposta Moçambique · Maputo</p>
          <p>Supervisão das operações diárias, coordenação da equipa de atendimento ao cliente, controlo de qualidade e gestão de escalamento de reclamações. Implementação de melhorias de processo para aumentar a eficiência operacional.</p>
        </div>
        <div class="timeline-item">
          <p class="period">Anteriormente</p>
          <h3>Agente de Atendimento ao Cliente</h3>
          <p class="company">Primeira Aposta Moçambique · Maputo</p>
          <p>Assistência a clientes via múltiplos canais, resolução de problemas técnicos e comerciais, apoio em campanhas de marketing e retenção.</p>
        </div>
      </div>
    </section>

    <!-- FORMAÇÃO -->
    <section>
      <p class="section-label">Formação</p>
      <h2>Educação & Certificações</h2>
      <div class="education-list">
        <div class="edu-item">
          <span class="edu-year">Em<br>Curso</span>
          <div class="edu-info">
            <h4>Licenciatura em Direito</h4>
            <span>Universidade · Maputo, Moçambique</span>
          </div>
        </div>
        <div class="edu-item">
          <span class="edu-year">Téc.</span>
          <div class="edu-info">
            <h4>Técnico de Contabilidade e Gestão</h4>
            <span>Formação Técnico-Profissional</span>
          </div>
        </div>
        <div class="edu-item">
          <span class="edu-year">Cert.</span>
          <div class="edu-info">
            <h4>Certificações Complementares</h4>
            <span>Relações Públicas · Liderança · Recursos Humanos</span>
          </div>
        </div>
      </div>
    </section>

    <!-- IDIOMAS -->
    <section>
      <p class="section-label">Comunicação</p>
      <h2>Idiomas</h2>
      <div class="languages-row">
        <div class="lang-chip">
          <span class="lang-name">Português</span>
          <span class="lang-level">Fluente</span>
        </div>
        <div class="lang-chip">
          <span class="lang-name">Changana</span>
          <span class="lang-level">Intermediário</span>
        </div>
        <div class="lang-chip">
          <span class="lang-name">Inglês</span>
          <span class="lang-level">Básico</span>
        </div>
      </div>
    </section>

    <!-- LINKEDIN BADGE -->
    <div class="linkedin-section">
      <p class="section-label">Rede Profissional</p>
      <h2 style="font-family:'Cormorant Garamond',serif; font-weight:300;">Conecte-se no LinkedIn</h2>
      <div class="badge-wrapper">
        <!-- LinkedIn Badge -->
        <script src="https://platform.linkedin.com/badges/js/profile.js" async defer type="text/javascript"></script>
        <div class="badge-base LI-profile-badge"
             data-locale="pt_BR"
             data-size="large"
             data-theme="light"
             data-type="HORIZONTAL"
             data-vanity="edgar-da-silva-0927b52a0"
             data-version="v1">
          <a class="badge-base__link LI-simple-link"
             href="https://mz.linkedin.com/in/edgar-da-silva-0927b52a0?trk=profile-badge">
            Edgar Da Silva
          </a>
        </div>
        <p>Perfil verificado · Aberto a novas oportunidades</p>
      </div>
    </div>

    <!-- FOOTER -->
    <footer>
      <p>© 2025 Edgar da Silva Coutinho &nbsp;·&nbsp; Maputo, Moçambique</p>
      <p style="margin-top:0.4rem;">
        <a href="https://mz.linkedin.com/in/edgar-da-silva-0927b52a0">LinkedIn</a>
      </p>
    </footer>

  </div>

</body>
</html>
