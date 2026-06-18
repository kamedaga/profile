<script lang="ts">
  import wf201Character from "./assets/wf201Character.png";
  import { onMount } from 'svelte';

  const name = "Kamezuki";
  let activeSection = 'profile';

  onMount(() => {
    const sectionIds = ['profile', 'nilo', 'pine-online', 'pachaos', 'kobox', 'tools'];

    const update = () => {
      const scrollY = window.scrollY;
      for (let i = sectionIds.length - 1; i >= 0; i--) {
        const el = document.getElementById(sectionIds[i]);
        if (el && el.offsetTop - window.innerHeight * 0.4 <= scrollY) {
          activeSection = sectionIds[i];
          break;
        }
      }
    };

    window.addEventListener('scroll', update, { passive: true });
    update();
    return () => window.removeEventListener('scroll', update);
  });
</script>

<div class="layout">
  <aside class="sidebar">
    <div class="sidebar-inner">
      <div class="sidebar-brand">
        <span class="brand-mark">Kame</span>
        <span class="brand-name">KAMEZUKI</span>
      </div>

      <nav class="sidebar-nav" aria-label="セクション">
        <a href="#profile" class:active={activeSection === 'profile'}><span class="nav-num">01</span>Profile</a>
        <a href="#nilo" class:active={activeSection === 'nilo'}><span class="nav-num">02</span>nilo</a>
        <a href="#pine-online" class:active={activeSection === 'pine-online'}><span class="nav-num">03</span>pine-online</a>
        <a href="#pachaos" class:active={activeSection === 'pachaos'}><span class="nav-num">04</span>PachaOS</a>
        <a href="#kobox" class:active={activeSection === 'kobox'}><span class="nav-num">05</span>kobox</a>
        <a href="#tools" class:active={activeSection === 'tools'}><span class="nav-num">06</span>Tools</a>
      </nav>

      <div class="sidebar-footer">
        <div class="sidebar-divider"></div>
        <a class="sidebar-ext" href="https://github.com/kamedaga" target="_blank" rel="noreferrer">GitHub <span aria-hidden="true">↗</span></a>
        <a class="sidebar-ext" href="https://zenn.dev/kamerty">Zenn <span aria-hidden="true">↗</span></a>
        <div class="sidebar-divider"></div>
        <div class="sidebar-tags">
          <span>Zsh</span><span>Bash</span><span>C</span>
        </div>
      </div>
    </div>
  </aside>

  <main class="page">
    <section id="profile" class="hero-card" aria-label="プロフィール">
      <div class="intro">
        <p class="eyebrow">PROFILE</p>
        <h1>{name}</h1>
        <p class="lead">プログラミング, いろいろ</p>
        <div class="actions" aria-label="リンク">
          <a class="primary" href="https://github.com/kamedaga" target="_blank" rel="noreferrer">GitHub</a>
          <a class="secondary" href="https://zenn.dev/kamerty">Zenn</a>
        </div>
        <div class="small">(ぜひフォローよろしくお願いします。)</div>
      </div>

      <div class="note-stack" aria-hidden="true">
        <div class="note note-lime">Zsh</div>
        <div class="note note-pink">Bash</div>
        <div class="note note-lilac">C</div>
      </div>
    </section>

    <section id="nilo" class="project-card" aria-labelledby="project-nilo">
      <div class="project-copy">
        <p class="eyebrow">WORK 01</p>
        <h2 id="project-nilo">nilo</h2>
        <p class="project-kind">UI framework</p>
        <p class="project-description">
          宣言的DSLでUIを設計できるUIフレームワーク。
        </p>
        <a
          class="primary"
          href="https://github.com/kamedaga/nilo"
          target="_blank"
          rel="noreferrer"
        >
          GitHub
        </a>
      </div>

      <div class="dsl-preview" aria-label="nilo DSL preview">
        <span>timeline Calc &#123;</span>
        <span class="indent">font: "japanese"</span>
        <span class="indent">VStack(style: &#123;</span>
        <span class="indent-2">width: 100ww,</span>
        <span class="indent-2">height: 100wh,</span>
        <span class="indent-2">...</span>
        <span class="indent">&#125;</span>
        <span>&#125;</span>
      </div>
    </section>

    <section id="pine-online" class="project-card project-card-pine" aria-labelledby="project-pine-online">
      <div class="project-copy">
        <p class="eyebrow">WORK 02</p>
        <h2 id="project-pine-online">pine-online</h2>
        <p class="project-kind">microservices experiment</p>
        <p class="project-description">
          興味でAIに複数の言語を使ってマイクロサービスを作らせるも、どこにもデプロイできず自宅鯖で運営していたが結局終了したため供養。
        </p>
        <a
          class="primary"
          href="https://github.com/kamedaga/pine-online"
          target="_blank"
          rel="noreferrer"
        >
          GitHub
        </a>
      </div>

      <div class="language-board" aria-label="pine-online language breakdown">
        <div class="language-bar" aria-hidden="true">
          <span class="lang-csharp"></span>
          <span class="lang-typescript"></span>
          <span class="lang-go"></span>
          <span class="lang-css"></span>
          <span class="lang-html"></span>
          <span class="lang-scala"></span>
          <span class="lang-other"></span>
        </div>
        <dl class="language-list">
          <div><dt><span class="dot lang-csharp"></span>C#</dt><dd>36.1%</dd></div>
          <div><dt><span class="dot lang-typescript"></span>TypeScript</dt><dd>31.0%</dd></div>
          <div><dt><span class="dot lang-go"></span>Go</dt><dd>14.7%</dd></div>
          <div><dt><span class="dot lang-css"></span>CSS</dt><dd>10.6%</dd></div>
          <div><dt><span class="dot lang-html"></span>HTML</dt><dd>3.6%</dd></div>
          <div><dt><span class="dot lang-scala"></span>Scala</dt><dd>1.9%</dd></div>
          <div><dt><span class="dot lang-other"></span>Other</dt><dd>2.1%</dd></div>
        </dl>
      </div>
    </section>

    <section id="pachaos" class="project-card project-card-pacha" aria-labelledby="project-pachaos">
      <div class="project-copy">
        <p class="eyebrow">WORK 03</p>
        <h2 id="project-pachaos">PachaOS</h2>
        <p class="project-kind">microkernel OS</p>
        <p class="project-description">
          Linux互換を目指して作っているZig製マイクロカーネル。(ユーザー空間はほとんどC)<br />
          Python、Vim、Clang、apk などをユーザーランドで動かす実験をしています。
        </p>
        <a
          class="primary"
          href="https://github.com/kamedaga/os"
          target="_blank"
          rel="noreferrer"
        >
          GitHub
        </a>
      </div>

      <div class="terminal-board" aria-label="PachaOS terminal preview">
        <span class="prompt"># python3</span>
        <span>Python 3.12.13 on linux</span>
        <span class="prompt">&gt;&gt;&gt; import os</span>
        <span class="prompt">&gt;&gt;&gt; os.uname()</span>
        <span>sysname='Linux'</span>
        <span>release='6.0.0-capabilityos'</span>
        <span class="prompt"># apk add nano clang</span>
        <span>OK: userland-first</span>
      </div>
    </section>

    <section id="kobox" class="project-card project-card-kobox" aria-labelledby="project-kobox">
      <div class="project-copy">
        <p class="eyebrow">WORK 04</p>
        <h2 id="project-kobox">kobox</h2>
        <p class="project-kind">driver runtime</p>
        <p class="project-description">
          Linux カーネルモジュールをユーザーランドで動かすランタイム。<br />
          NVMe や USB Storage を Linux VFIO / PachaOS Capsule backend で動かしています。
        </p>
        <a
          class="primary"
          href="https://github.com/kamedaga/kobox"
          target="_blank"
          rel="noreferrer"
        >
          GitHub
        </a>
      </div>

      <div class="flow-board" aria-label="kobox driver flow">
        <div class="flow-node">Linux Driver<br />.ko</div>
        <div class="flow-arrow">↓</div>
        <div class="flow-node">libc shim</div>
        <div class="flow-arrow">↓</div>
        <div class="flow-node">backend API</div>
        <div class="flow-arrow">↓</div>
        <div class="flow-node flow-device">NVMe / USB</div>
      </div>
    </section>

    <section id="tools" class="tech-section" aria-labelledby="tech-title">
      <div class="tech-copy">
        <p class="eyebrow">TOOLS</p>
        <h2 id="tech-title">使ってる技術</h2>
        <p class="tech-lead">
          いろいろできます。
        </p>
        <div class="tech-grid" aria-label="技術一覧">
          <span>Zig</span>
          <span>C</span>
          <span>Go</span>
        </div>
      </div>

      <img
        class="tech-character"
        src={wf201Character}
        alt=""
        aria-hidden="true"
        loading="lazy"
        decoding="async"
      />
    </section>
  </main>
</div>

<style>
  :global(*) {
    box-sizing: border-box;
  }

  :global(body) {
    margin: 0;
    min-width: 320px;
    color: #000000;
    background: #ffffff;
    font-family:
      "Comic Sans MS", "Yu Gothic", "Hiragino Maru Gothic ProN", system-ui,
      sans-serif;
    scroll-behavior: smooth;
  }

  /* ── LAYOUT ── */
  .layout {
    display: flex;
    min-height: 100svh;
  }

  /* ── SIDEBAR ── */
  .sidebar {
    position: fixed;
    top: 0;
    left: 0;
    width: 220px;
    height: 100svh;
    background: #0d0d0d;
    color: #ffffff;
    z-index: 200;
    display: flex;
    flex-direction: column;
    overflow-y: auto;
  }

  .sidebar-inner {
    display: flex;
    flex-direction: column;
    min-height: 100%;
    padding: 32px 22px;
  }

  .sidebar-brand {
    display: flex;
    flex-direction: column;
    gap: 4px;
    margin-bottom: 40px;
  }

  .brand-mark {
    font-family: "Courier New", ui-monospace, monospace;
    font-size: 0.7rem;
    font-weight: 700;
    letter-spacing: 0.25em;
    color: #444444;
  }

  .brand-name {
    font-family: "Courier New", ui-monospace, monospace;
    font-size: 0.8rem;
    font-weight: 700;
    letter-spacing: 0.18em;
    color: #ffffff;
    line-height: 1.3;
  }

  .sidebar-nav {
    flex: 1;
    display: flex;
    flex-direction: column;
    gap: 2px;
  }

  .sidebar-nav a {
    position: relative;
    display: flex;
    align-items: center;
    gap: 10px;
    padding: 8px 10px;
    border-radius: 6px;
    color: #777777;
    font-family: "Courier New", ui-monospace, monospace;
    font-size: 0.8rem;
    font-weight: 700;
    letter-spacing: 0.05em;
    text-decoration: none;
    min-height: unset;
    justify-content: flex-start;
    border: none;
    background: none;
    transition: color 0.15s, background 0.15s;
  }

  .sidebar-nav a:hover {
    color: #ffffff;
    background: rgba(255, 255, 255, 0.07);
  }

  .sidebar-nav a.active {
    color: #ffffff;
  }

  .sidebar-nav a.active .nav-num {
    color: #666666;
  }

  .sidebar-nav a.active::after {
    content: '';
    position: absolute;
    left: 0;
    top: 50%;
    transform: translateY(-50%);
    width: 2px;
    height: 14px;
    background: #ffffff;
    border-radius: 1px;
  }

  .nav-num {
    font-size: 0.65rem;
    color: #3a3a3a;
    flex: 0 0 auto;
    letter-spacing: 0.05em;
  }

  .sidebar-footer {
    display: flex;
    flex-direction: column;
    gap: 4px;
    margin-top: 20px;
  }

  .sidebar-divider {
    height: 1px;
    background: rgba(255, 255, 255, 0.1);
    margin: 6px 0;
  }

  .sidebar-ext {
    display: flex;
    align-items: center;
    justify-content: space-between;
    padding: 7px 10px;
    color: #555555;
    font-family: "Courier New", ui-monospace, monospace;
    font-size: 0.75rem;
    font-weight: 700;
    letter-spacing: 0.05em;
    text-decoration: none;
    min-height: unset;
    border: none;
    background: none;
    border-radius: 4px;
    transition: color 0.15s;
  }

  .sidebar-ext:hover {
    color: #bbbbbb;
  }

  .sidebar-tags {
    display: flex;
    flex-wrap: wrap;
    gap: 5px;
    padding: 4px 10px;
  }

  .sidebar-tags span {
    font-family: "Courier New", ui-monospace, monospace;
    font-size: 0.65rem;
    font-weight: 700;
    letter-spacing: 0.06em;
    color: #3a3a3a;
    border: 1px solid #2a2a2a;
    border-radius: 3px;
    padding: 2px 6px;
  }

  /* ── MAIN CONTENT ── */
  .page {
    margin-left: 220px;
    flex: 1;
    min-width: 0;
    min-height: 100svh;
    padding: 14px;
    display: flex;
    flex-direction: column;
    gap: 0;
  }

  .hero-card {
    margin-bottom: 14px;
  }

  .hero-card {
    width: 100%;
    min-height: calc(100svh - 28px);
    display: grid;
    grid-template-columns: minmax(0, 1.35fr) minmax(320px, 0.65fr);
    align-items: center;
    gap: 32px;
    position: relative;
    overflow: hidden;
    border-radius: 24px;
    background-color: #f4ecd6;
    background-image:
      linear-gradient(rgba(0, 0, 0, 0.055) 1px, transparent 1px),
      linear-gradient(90deg, rgba(0, 0, 0, 0.055) 1px, transparent 1px);
    background-size: 34px 34px;
    padding: 56px;
  }

  .hero-card::before {
    content: "";
    position: absolute;
    inset: 0;
    pointer-events: none;
    background:
      radial-gradient(circle at 18% 22%, rgba(255, 255, 255, 0.34), transparent 24%),
      linear-gradient(rgba(255, 255, 255, 0.18), rgba(255, 255, 255, 0));
  }

  .intro,
  .note-stack {
    position: relative;
    z-index: 1;
  }

  .intro {
    max-width: 860px;
  }

  .eyebrow {
    margin: 0 0 18px;
    font-family: "Courier New", ui-monospace, monospace;
    font-size: 0.95rem;
    font-weight: 700;
    letter-spacing: 0;
  }

  h1 {
    margin: 0;
    font-size: clamp(4.5rem, 10vw, 11rem);
    line-height: 0.92;
    font-weight: 900;
    letter-spacing: 0;
    text-wrap: balance;
  }

  .lead {
    max-width: 520px;
    margin: 28px 0 0;
    font-size: clamp(1.35rem, 3vw, 2.2rem);
    font-weight: 800;
    line-height: 1.45;
  }
  .small {
    max-width: 520px;
    margin: 28px 0 0;
    font-size: clamp(0.5rem, 1vw, 1.4rem);
    font-weight: 800;
    line-height: 1.45;
  }

  .actions {
    display: flex;
    flex-wrap: wrap;
    gap: 12px;
    margin-top: 34px;
  }

  a {
    min-height: 48px;
    display: inline-flex;
    align-items: center;
    justify-content: center;
    border-radius: 9999px;
    padding: 10px 24px;
    color: #000000;
    font-size: 1.1rem;
    font-weight: 800;
    letter-spacing: 0;
    text-decoration: none;
  }

  .primary {
    color: #ffffff;
    background: #000000;
  }

  .secondary {
    background: #ffffff;
  }

  .note-stack {
    position: relative;
    min-height: 520px;
    overflow: visible;
  }

  .note {
    position: absolute;
    display: grid;
    place-items: center;
    width: clamp(150px, 20vw, 270px);
    aspect-ratio: 1;
    border: 3px solid #000000;
    border-radius: 18px;
    color: #000000;
    font-size: clamp(1.6rem, 4vw, 3.2rem);
    font-weight: 900;
    letter-spacing: 0;
  }

  .note-lime {
    top: 8%;
    right: 24%;
    rotate: -8deg;
    background: #dceeb1;
  }

  .note-pink {
    top: 36%;
    right: 0;
    rotate: 7deg;
    background: #efd4d4;
  }

  .note-lilac {
    bottom: 2%;
    right: 34%;
    rotate: 4deg;
    background: #c5b0f4;
  }

  .project-card {
    width: calc(100% + 28px);
    margin-inline: -14px;
    min-height: 78svh;
    display: grid;
    grid-template-columns: minmax(0, 0.88fr) minmax(280px, 1.12fr);
    align-items: center;
    gap: 48px;
    position: relative;
    overflow: hidden;
    border-radius: 0;
    background-color: #dceeb1;
    padding: 150px 70px 104px;
    color: #000000;
  }

  .project-card::before {
    content: "";
    position: absolute;
    inset: 0 0 auto;
    height: 112px;
    pointer-events: none;
    background: linear-gradient(180deg, #ffffff 0%, #f7fbec 42%, #dceeb1 100%);
  }

  .project-card > * {
    position: relative;
    z-index: 1;
  }

  .project-card-pine {
    background-color: #f3c9b6;
  }

  .project-card-pine::before {
    height: 72px;
    background: linear-gradient(180deg, #dceeb1 0%, #ead6b7 46%, #f3c9b6 100%);
  }

  .project-card-pacha {
    background-color: #ffffff;
    background-image:
      linear-gradient(rgba(0, 0, 0, 0.05) 1px, transparent 1px),
      linear-gradient(90deg, rgba(0, 0, 0, 0.05) 1px, transparent 1px);
    background-size: 34px 34px;
    color: #000000;
  }

  .project-card-pacha::before {
    display: none;
  }

  .project-card-kobox {
    background-color: #ffffff;
    background-image:
      linear-gradient(rgba(0, 0, 0, 0.05) 1px, transparent 1px),
      linear-gradient(90deg, rgba(0, 0, 0, 0.05) 1px, transparent 1px);
    background-size: 34px 34px;
    color: #000000;
  }

  .project-card-kobox::before {
    display: none;
  }

  .project-card-kobox .project-kind {
    color: #000000;
    background: #dceeb1;
  }

  .project-card-kobox .primary {
    color: #ffffff;
    background: #000000;
  }

  .project-card-pacha .project-kind {
    color: #000000;
  }

  .project-card-pacha .primary {
    color: #ffffff;
    background: #000000;
  }

  .project-copy {
    max-width: 560px;
    min-width: 0;
  }

  h2 {
    margin: 0;
    font-size: clamp(4rem, 10vw, 8.5rem);
    font-weight: 900;
    line-height: 0.92;
    letter-spacing: 0;
    overflow-wrap: anywhere;
  }

  .project-kind {
    width: fit-content;
    margin: 20px 0 0;
    border: 3px solid #000000;
    border-radius: 9999px;
    padding: 8px 18px;
    background: #ffffff;
    font-size: 1.15rem;
    font-weight: 900;
  }

  .project-description {
    margin: 24px 0 28px;
    font-size: clamp(1.35rem, 2.7vw, 2.1rem);
    font-weight: 800;
    line-height: 1.45;
  }

  .dsl-preview {
    display: grid;
    max-width: 100%;
    gap: 10px;
    border: 3px solid #000000;
    border-radius: 18px;
    padding: 28px;
    background: #ffffff;
    font-family: "Courier New", ui-monospace, monospace;
    font-size: clamp(1rem, 2vw, 1.6rem);
    font-weight: 700;
    line-height: 1.35;
    rotate: 1.5deg;
  }

  .indent {
    padding-left: 1.4em;
  }

  .indent-2 {
    padding-left: 2.8em;
  }

  .language-board {
    position: relative;
    min-width: 0;
    display: grid;
    gap: 24px;
    border: 3px solid #000000;
    border-radius: 18px;
    padding: 28px;
    background: rgba(255, 255, 255, 0.78);
    rotate: -1deg;
  }

  .language-bar {
    height: 30px;
    display: flex;
    overflow: hidden;
    border: 3px solid #000000;
    border-radius: 9999px;
    background: #ffffff;
  }

  .language-bar span {
    display: block;
    height: 100%;
  }

  .language-bar .lang-csharp {
    width: 36.1%;
  }

  .language-bar .lang-typescript {
    width: 31%;
  }

  .language-bar .lang-go {
    width: 14.7%;
  }

  .language-bar .lang-css {
    width: 10.6%;
  }

  .language-bar .lang-html {
    width: 3.6%;
  }

  .language-bar .lang-scala {
    width: 1.9%;
  }

  .language-bar .lang-other {
    width: 2.1%;
  }

  .language-list {
    display: grid;
    grid-template-columns: repeat(2, minmax(0, 1fr));
    gap: 14px 22px;
    margin: 0;
  }

  .language-list div {
    display: flex;
    align-items: baseline;
    justify-content: space-between;
    gap: 12px;
  }

  .language-list dt,
  .language-list dd {
    margin: 0;
    font-size: clamp(1rem, 1.7vw, 1.35rem);
    font-weight: 900;
  }

  .language-list dt {
    display: inline-flex;
    align-items: center;
    gap: 8px;
  }

  .dot {
    width: 14px;
    height: 14px;
    flex: 0 0 auto;
    border: 2px solid #000000;
    border-radius: 9999px;
  }

  .lang-csharp {
    background: #178600;
  }

  .lang-typescript {
    background: #3178c6;
  }

  .lang-go {
    background: #00add8;
  }

  .lang-css {
    background: #563d7c;
  }

  .lang-html {
    background: #e34c26;
  }

  .lang-scala {
    background: #c22d40;
  }

  .lang-other {
    background: #ededed;
  }

  .terminal-board {
    display: grid;
    max-width: 100%;
    gap: 10px;
    border: 3px solid #000000;
    border-radius: 18px;
    padding: 28px;
    background: #000000;
    color: #dceeb1;
    font-family: "Courier New", ui-monospace, monospace;
    font-size: clamp(0.95rem, 1.7vw, 1.35rem);
    font-weight: 700;
    line-height: 1.35;
    rotate: 1deg;
  }

  .flow-board {
    display: grid;
    min-width: 0;
    justify-items: center;
    gap: 10px;
    border: 3px solid #000000;
    border-radius: 18px;
    padding: 28px;
    background: rgba(255, 255, 255, 0.78);
    color: #000000;
    rotate: -1deg;
  }

  .flow-node {
    width: min(100%, 420px);
    min-height: 74px;
    display: grid;
    place-items: center;
    border: 3px solid #000000;
    border-radius: 16px;
    padding: 12px 20px;
    background: #ffffff;
    color: #000000;
    text-align: center;
    font-size: clamp(1.15rem, 2vw, 1.8rem);
    font-weight: 900;
    line-height: 1.18;
  }

  .flow-device {
    background: #dceeb1;
  }

  .flow-arrow {
    font-size: 2rem;
    font-weight: 900;
    line-height: 1;
  }

  .tech-section {
    position: relative;
    width: calc(100% + 28px);
    min-height: 72svh;
    margin-inline: -14px;
    overflow: hidden;
    background: #000000;
    color: #ffffff;
    padding: 112px 70px 120px;
  }

  .tech-copy {
    position: relative;
    z-index: 1;
    max-width: 760px;
    min-width: 0;
  }

  .tech-section .eyebrow {
    color: #dceeb1;
  }

  .tech-section h2 {
    white-space: nowrap;
    font-size: clamp(3.2rem, 9vw, 8.5rem);
  }

  .tech-lead {
    max-width: 560px;
    margin: 24px 0 0;
    font-size: clamp(1.35rem, 2.7vw, 2.1rem);
    font-weight: 800;
    line-height: 1.45;
  }

  .tech-grid {
    width: min(100%, 720px);
    display: flex;
    flex-wrap: wrap;
    gap: 12px;
    margin-top: 34px;
  }

  .tech-grid span {
    min-height: 46px;
    display: inline-flex;
    align-items: center;
    border: 2px solid #ffffff;
    border-radius: 9999px;
    padding: 8px 18px;
    background: #ffffff;
    color: #000000;
    font-size: clamp(1rem, 1.6vw, 1.25rem);
    font-weight: 900;
  }

  .tech-grid span:nth-child(3n + 1) {
    background: #dceeb1;
  }

  .tech-grid span:nth-child(3n + 2) {
    background: #f3c9b6;
  }

  .tech-grid span:nth-child(3n) {
    background: #c5b0f4;
  }

  .tech-character {
    position: absolute;
    right: min(5vw, 72px);
    bottom: -14svh;
    z-index: 0;
    width: min(42vw, 520px);
    max-width: 58%;
    filter: drop-shadow(0 16px 48px rgba(255, 255, 255, 0.18));
    pointer-events: none;
    user-select: none;
  }

  .prompt {
    color: #ffffff;
  }

  /* ── MOBILE ── */
  @media (max-width: 900px) {
    .sidebar {
      display: none;
    }

    .page {
      margin-left: 0;
    }
  }

  @media (max-width: 820px) {
    .page {
      padding: 0;
    }

    .hero-card {
      min-height: 100svh;
      grid-template-columns: 1fr;
      gap: 28px;
      border-radius: 0;
      padding: 40px 24px 32px;
    }

    h1 {
      font-size: clamp(3.7rem, 18vw, 6rem);
    }

    h2 {
      font-size: clamp(3.3rem, 16vw, 5.8rem);
    }

    .lead,
    .project-description,
    .tech-lead {
      font-size: clamp(1.15rem, 5.4vw, 1.55rem);
    }

    .small {
      font-size: 0.95rem;
    }

    .actions {
      width: 100%;
    }

    .actions a {
      flex: 1 1 130px;
    }

    .note-stack {
      min-height: 260px;
    }

    .note {
      width: clamp(112px, 36vw, 170px);
    }

    .note-lime {
      left: 8%;
      right: auto;
    }

    .note-pink {
      right: 2%;
    }

    .note-lilac {
      left: 28%;
      right: auto;
    }

    .project-card {
      min-height: 82svh;
      width: 100%;
      margin-inline: 0;
      grid-template-columns: 1fr;
      gap: 28px;
      border-radius: 0;
      padding: 104px 24px 72px;
    }

    .project-kind {
      max-width: 100%;
      font-size: 1rem;
      overflow-wrap: anywhere;
    }

    .dsl-preview {
      overflow-x: auto;
      rotate: 0deg;
      padding: 20px;
      font-size: 0.95rem;
    }

    .language-board {
      rotate: 0deg;
      padding: 20px;
    }

    .language-list {
      grid-template-columns: 1fr;
    }

    .terminal-board {
      overflow-x: auto;
      rotate: 0deg;
      padding: 20px;
      font-size: 0.9rem;
    }

    .flow-board {
      rotate: 0deg;
      padding: 20px;
    }

    .flow-node {
      min-height: 64px;
      font-size: 1.05rem;
    }

    .tech-section {
      width: 100%;
      min-height: 78svh;
      margin-inline: 0;
      padding: 72px 24px 260px;
    }

    .tech-character {
      right: -4vw;
      bottom: -8svh;
      width: min(76vw, 380px);
      max-width: none;
    }
  }

  @media (max-width: 560px) {
    .hero-card {
      min-height: auto;
      padding: 36px 18px 28px;
    }

    h1 {
      font-size: clamp(3.2rem, 17vw, 4.6rem);
    }

    h2 {
      font-size: clamp(2.85rem, 15vw, 4.6rem);
    }

    .tech-section h2 {
      font-size: clamp(2.55rem, 12vw, 3.8rem);
    }

    .note-stack {
      min-height: 220px;
    }

    .note {
      width: clamp(96px, 34vw, 136px);
      border-width: 2px;
      border-radius: 14px;
      font-size: clamp(1.3rem, 8vw, 2rem);
    }

    .project-card {
      min-height: auto;
      padding: 88px 18px 64px;
    }

    .project-card-pacha,
    .project-card-kobox {
      padding-top: 64px;
    }

    .project-card::before {
      height: 74px;
    }

    .project-card-pine::before {
      height: 52px;
    }

    a {
      width: 100%;
      min-height: 46px;
      padding-inline: 18px;
    }

    .language-list div {
      align-items: center;
    }

    .language-list dt,
    .language-list dd {
      font-size: 0.95rem;
    }

    .indent {
      padding-left: 1em;
    }

    .indent-2 {
      padding-left: 2em;
    }

    .tech-section {
      min-height: 720px;
      padding: 64px 18px 260px;
    }

    .tech-grid span {
      min-height: 42px;
      padding-inline: 16px;
    }

    .tech-character {
      right: -18vw;
      bottom: -5svh;
      width: min(98vw, 360px);
    }
  }
</style>
