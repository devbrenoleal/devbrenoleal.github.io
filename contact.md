<html lang="pt-BR">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>Contato — Obraday</title>
  <meta name="description" content="Página de contato — envie um e-mail para contato@obraday.com.br" />
  <style>
    :root{
      --bg:#0f1724;
      --card:#0b1220;
      --muted:#94a3b8;
      --accent:#06b6d4;
      --text:#e6eef6;
      --glass: rgba(255,255,255,0.03);
      --radius:16px;
      --max-width:880px;
      --shadow: 0 6px 24px rgba(2,6,23,0.6);
      --focus: 0 0 0 4px rgba(6,182,212,0.12);
      font-family: Inter, ui-sans-serif, system-ui, -apple-system, "Segoe UI", Roboto, "Helvetica Neue", Arial;
    }

    @media (prefers-color-scheme: light) {
      :root{
        --bg: #f6f8fb;
        --card: #ffffff;
        --muted:#556073;
        --accent:#0ea5b6;
        --text:#0b1220;
        --glass: rgba(11,18,32,0.03);
        --shadow: 0 6px 24px rgba(12,20,30,0.06);
        --focus: 0 0 0 4px rgba(14,165,182,0.12);
      }
    }

    html,body{height:100%}
    body{
      margin:0;
      min-height:100%;
      background: radial-gradient(1200px 600px at 10% 10%, rgba(6,182,212,0.06), transparent),
                  radial-gradient(900px 400px at 90% 90%, rgba(99,102,241,0.04), transparent),
                  var(--bg);
      color:var(--text);
      display:flex;
      align-items:center;
      justify-content:center;
      padding:48px 20px;
      -webkit-font-smoothing:antialiased;
      -moz-osx-font-smoothing:grayscale;
    }

    .container{
      width:100%;
      max-width:var(--max-width);
      display:grid;
      grid-template-columns: 1fr 420px;
      gap:28px;
      align-items:center;
    }

    @media (max-width:880px){
      .container{grid-template-columns:1fr; padding:0}
    }

    .hero{
      padding:36px;
      background: linear-gradient(180deg, rgba(255,255,255,0.02), transparent);
      border-radius:var(--radius);
      box-shadow: var(--shadow);
      backdrop-filter: blur(6px);
    }

    .eyebrow{
      display:inline-flex;
      gap:10px;
      align-items:center;
      color:var(--muted);
      font-size:13px;
      margin-bottom:18px;
    }

    .title{
      margin:0 0 12px 0;
      font-size:28px;
      line-height:1.05;
      letter-spacing:-0.02em;
    }

    .lead{
      margin:0;
      color:var(--muted);
      font-size:15px;
      line-height:1.6;
      max-width:60ch;
    }

    .card{
      padding:28px;
      border-radius:14px;
      background: linear-gradient(180deg, rgba(255,255,255,0.01), var(--glass));
      border: 1px solid rgba(255,255,255,0.03);
      box-shadow: var(--shadow);
      display:flex;
      flex-direction:column;
      gap:18px;
      align-items:stretch;
    }

    .contact-row{
      display:flex;
      gap:16px;
      align-items:center;
      flex-wrap:wrap;
    }

    .email-badge{
      display:flex;
      gap:12px;
      align-items:center;
      padding:12px 14px;
      border-radius:12px;
      background: linear-gradient(90deg, rgba(255,255,255,0.01), transparent);
      border: 1px solid rgba(255,255,255,0.02);
      min-width:0;
      flex:1 1 auto;
    }

    .email-icon{
      width:44px;
      height:44px;
      display:inline-grid;
      place-items:center;
      border-radius:10px;
      background: linear-gradient(135deg, rgba(6,182,212,0.12), rgba(99,102,241,0.06));
      flex: 0 0 44px;
    }

    .email-text{
      overflow:hidden;
      min-width:0;
    }

    .email-text .label{display:block;color:var(--muted);font-size:12px}
    .email-text .value{
      font-weight:600;
      font-size:15px;
      word-break:break-all;
    }

    .actions{
      display:flex;
      gap:10px;
      align-items:center;
    }

    .btn{
      appearance:none;
      border:0;
      padding:10px 14px;
      border-radius:10px;
      font-weight:600;
      cursor:pointer;
      display:inline-flex;
      gap:10px;
      align-items:center;
      justify-content:center;
      box-shadow:none;
      background:transparent;
      color:var(--text);
      transition:transform .08s ease, box-shadow .12s ease;
      border: 1px solid rgba(255,255,255,0.06);
      backdrop-filter: blur(4px);
    }

    .btn:active{transform:translateY(1px)}
    .btn:focus{outline:none; box-shadow:var(--focus)}

    .btn-primary{
      background: linear-gradient(90deg, var(--accent), color-mix(in srgb, var(--accent) 60%, black 10%));
      color:white;
      border: none;
    }

    .btn-ghost{
      background:transparent;
      color:var(--text);
    }

    .small{
      font-size:13px;
      color:var(--muted);
    }

    .footer{
      margin-top:12px;
      font-size:13px;
      color:var(--muted);
    }

    /* tooltip */
    .tooltip{
      position:relative;
      display:inline-block;
    }
    .tooltip .tip{
      position:absolute;
      bottom:calc(100% + 8px);
      left:50%;
      transform:translateX(-50%) translateY(6px);
      background:rgba(11,18,32,0.9);
      padding:8px 10px;
      border-radius:8px;
      color:white;
      font-size:13px;
      opacity:0;
      pointer-events:none;
      transition:opacity .12s ease, transform .12s ease;
      white-space:nowrap;
    }
    .tooltip.show .tip{opacity:1; transform:translateX(-50%) translateY(0)}

    /* subtle visual */
    .decor{
      display:flex;
      gap:10px;
      align-items:center;
    }

    .brand{
      display:inline-flex;
      gap:12px;
      align-items:center;
    }

    .brand h1{
      margin:0;
      font-size:18px;
      letter-spacing:-0.01em;
    }

    /* focus-visible for keyboard accessibility */
    .btn:focus-visible, .email-badge:focus-visible { outline: none; box-shadow: var(--focus); border-radius:10px; }

  </style>
</head>
<body>
  <main class="container" role="main">
    <section class="hero" aria-labelledby="contact-heading">
      <div class="eyebrow">
        <svg width="18" height="18" viewBox="0 0 24 24" fill="none" aria-hidden="true" focusable="false">
          <path d="M12 2L15.09 8.26L22 9.27L17 14.14L18.18 21.02L12 17.77L5.82 21.02L7 14.14L2 9.27L8.91 8.26L12 2Z" fill="currentColor" opacity="0.12"/>
        </svg>
        <span class="small">Contato rápido</span>
      </div>

      <h2 id="contact-heading" class="title">Fale com a equipe Obraday</h2>
      <p class="lead">Tem alguma dúvida, sugestão ou quer conversar sobre um projeto? Envie um e-mail para o endereço abaixo — responderemos o mais breve possível.</p>

      <div style="height:18px"></div>

      <div class="card" aria-label="Informações de contato">
        <div class="contact-row" role="region" aria-label="Endereço de e-mail">
          <div class="email-badge" tabindex="0">
            <div class="email-icon" aria-hidden="true">
              <!-- Envelope SVG -->
              <svg width="22" height="22" viewBox="0 0 24 24" fill="none" aria-hidden="true" focusable="false">
                <path d="M3 7.5V18a2 2 0 0 0 2 2h14a2 2 0 0 0 2-2V7.5" stroke="currentColor" stroke-width="1.4" stroke-linecap="round" stroke-linejoin="round"/>
                <path d="M21 7.5l-9 6-9-6" stroke="currentColor" stroke-width="1.4" stroke-linecap="round" stroke-linejoin="round"/>
                <path d="M3 7.5V6a2 2 0 0 1 2-2h14a2 2 0 0 1 2 2v1.5" stroke="currentColor" stroke-width="1.2" stroke-linecap="round" stroke-linejoin="round" opacity="0.6"/>
              </svg>
            </div>

            <div class="email-text">
              <span class="label">E-mail</span>
              <span class="value" id="contact-email">contato@obraday.com.br</span>
            </div>
          </div>

          <div class="actions" role="group" aria-label="Ações de contato">
            <a class="btn btn-primary" id="open-mail" href="mailto:contato@obraday.com.br?subject=Contato%20via%20site" title="Abrir cliente de e-mail" role="button">
              <!-- Mail icon -->
              <svg width="16" height="16" viewBox="0 0 24 24" fill="none" aria-hidden="true" focusable="false">
                <path d="M3 8.5l9 6 9-6" stroke="currentColor" stroke-width="1.4" stroke-linecap="round" stroke-linejoin="round"/>
                <path d="M21 8.5V18a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2V8.5" stroke="currentColor" stroke-width="1.2" stroke-linecap="round" stroke-linejoin="round" opacity="0.8"/>
              </svg>
              Enviar e-mail
            </a>

            <div class="tooltip" id="copy-tooltip">
              <button class="btn btn-ghost" id="copy-btn" aria-live="polite" aria-label="Copiar e-mail para a área de transferência">
                <!-- Copy icon -->
                <svg width="15" height="15" viewBox="0 0 24 24" fill="none" aria-hidden="true" focusable="false">
                  <rect x="9" y="9" width="11" height="11" rx="2" stroke="currentColor" stroke-width="1.2"/>
                  <rect x="4" y="4" width="11" height="11" rx="2" stroke="currentColor" stroke-width="1.2" opacity="0.6"/>
                </svg>
                Copiar
              </button>
              <div class="tip" role="status" id="copy-tip">Copiar e-mail</div>
            </div>
          </div>
        </div>

        <div class="footer" aria-hidden="true">
          <span class="small">Preferência de resposta: e-mail</span>
        </div>
      </div>
    </section>

    <aside class="card" aria-labelledby="help-heading">
      <div class="brand" style="margin-bottom:8px">
        <svg width="36" height="36" viewBox="0 0 24 24" aria-hidden="true" focusable="false">
          <circle cx="12" cy="12" r="10" fill="currentColor" opacity="0.06"></circle>
          <path d="M7 12.5h10" stroke="currentColor" stroke-width="1.4" stroke-linecap="round"></path>
          <path d="M7 9.5h10" stroke="currentColor" stroke-width="1.2" stroke-linecap="round" opacity="0.6"></path>
        </svg>
        <div>
          <h1 style="margin:0;font-size:16px">Obraday</h1>
          <div class="small">Respostas via e-mail</div>
        </div>
      </div>

      <h3 id="help-heading" style="margin:0 0 6px 0">Precisa de ajuda?</h3>
      <p class="small" style="margin:0 0 12px 0">Se quiser enviar anexos (contratos, imagens, orçamentos), responda ao e-mail que você receberá ou use o botão <strong>Enviar e-mail</strong> para abrir seu cliente de e-mail com o endereço já preenchido.</p>

      <div style="display:flex;gap:10px;flex-wrap:wrap">
        <a class="btn" href="mailto:contato@obraday.com.br?subject=Anexo%20para%20Obraday" title="Enviar e-mail com assunto predefinido">Enviar com assunto</a>
        <button class="btn" id="report-btn" title="Copiar para report">Copiar e-mail para relatório</button>
      </div>

      <div style="margin-top:12px" class="small">Esta é uma página estática — se desejar um formulário que envie mensagens direto do site, diga-me e eu gero um exemplo com backend ou integração por e-mail (Formspree, Netlify Forms, etc.).</div>
    </aside>
  </main>

  <script>
    (function () {
      const email = 'contato@obraday.com.br';
      const copyBtn = document.getElementById('copy-btn');
      const copyTip = document.getElementById('copy-tip');
      const tooltip = document.getElementById('copy-tooltip');
      const reportBtn = document.getElementById('report-btn');

      async function copyEmail() {
        try {
          if (navigator.clipboard && window.isSecureContext) {
            await navigator.clipboard.writeText(email);
          } else {
            // fallback for insecure contexts
            const ta = document.createElement('textarea');
            ta.value = email;
            ta.style.position = 'fixed';
            ta.style.left = '-9999px';
            document.body.appendChild(ta);
            ta.select();
            document.execCommand('copy');
            document.body.removeChild(ta);
          }
          showTip('Copiado!');
        } catch (err) {
          showTip('Erro ao copiar');
          console.error('clipboard error', err);
        }
      }

      function showTip(message = 'Copiar e-mail') {
        copyTip.textContent = message;
        tooltip.classList.add('show');
        // hide after 1.6s
        clearTimeout(tooltip._hideTimeout);
        tooltip._hideTimeout = setTimeout(() => {
          tooltip.classList.remove('show');
          copyTip.textContent = 'Copiar e-mail';
        }, 1600);
      }

      copyBtn.addEventListener('click', copyEmail);
      copyBtn.addEventListener('keydown', (e) => {
        if (e.key === 'Enter' || e.key === ' ') {
          e.preventDefault();
          copyEmail();
        }
      });

      // Example of other action (copies into a "report" area)
      reportBtn.addEventListener('click', () => {
        try {
          navigator.clipboard && navigator.clipboard.writeText && navigator.clipboard.writeText(`Contato: ${email}`);
          reportBtn.textContent = 'Copiado!';
          setTimeout(() => reportBtn.textContent = 'Copiar e-mail para relatório', 1400);
        } catch (e) {
          reportBtn.textContent = 'Erro';
          setTimeout(() => reportBtn.textContent = 'Copiar e-mail para relatório', 1400);
        }
      });

      // Accessibility: allow focusing the email badge to announce the address
      const emailBadge = document.querySelector('.email-badge');
      emailBadge.addEventListener('focus', () => {
        emailBadge.setAttribute('aria-label', `Endereço de e-mail: ${email}`);
      });
      emailBadge.addEventListener('blur', () => {
        emailBadge.setAttribute('aria-label', 'Endereço de e-mail');
      });
    })();
  </script>
</body>
</html>
