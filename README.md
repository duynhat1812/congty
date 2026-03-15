<!DOCTYPE html>
<html lang="vi">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>GEU-LIM HÀ NAM - Tuyển dụng công nhân may</title>
  <style>
    *{
      margin:0;
      padding:0;
      box-sizing:border-box;
    }

    :root{
      --red:#d90429;
      --red2:#ef233c;
      --orange:#ff9f1c;
      --dark:#0f172a;
      --dark2:#1e293b;
      --text:#1f2937;
      --muted:#6b7280;
      --white:#ffffff;
      --soft:#fff6f6;
      --soft2:#fffaf2;
      --blue:#0068ff;
      --shadow:0 18px 45px rgba(15,23,42,0.08);
    }

    html{
      scroll-behavior:smooth;
    }

    body{
      font-family:Arial, Helvetica, sans-serif;
      background:
        radial-gradient(circle at top left, rgba(255,77,77,0.16), transparent 28%),
        radial-gradient(circle at top right, rgba(255,170,0,0.12), transparent 26%),
        linear-gradient(135deg, #fff5f5 0%, #fffaf2 45%, #f7fbff 100%);
      color:var(--text);
      line-height:1.6;
      overflow-x:hidden;
    }

    a{
      text-decoration:none;
    }

    .container{
      width:min(1200px, calc(100% - 28px));
      margin:0 auto;
    }

    .section{
      margin-top:28px;
      background:rgba(255,255,255,0.96);
      border-radius:28px;
      box-shadow:var(--shadow);
      overflow:hidden;
    }

    .section-head{
      padding:36px 34px 12px;
      text-align:center;
    }

    .section-title{
      font-size:34px;
      font-weight:900;
      color:#111827;
      margin-bottom:10px;
      line-height:1.2;
    }

    .section-sub{
      max-width:860px;
      margin:0 auto;
      font-size:17px;
      color:var(--muted);
    }

    .reveal{
      opacity:0;
      transform:translateY(40px);
      transition:all 0.85s ease;
    }

    .reveal.show{
      opacity:1;
      transform:translateY(0);
    }

    /* floating buttons */
    .floating-actions{
      position:fixed;
      right:18px;
      bottom:18px;
      z-index:9999;
      display:flex;
      flex-direction:column;
      gap:12px;
    }

    .floating-btn{
      width:62px;
      height:62px;
      border-radius:50%;
      display:flex;
      align-items:center;
      justify-content:center;
      color:#fff;
      font-size:26px;
      box-shadow:0 14px 28px rgba(0,0,0,0.2);
      transition:transform 0.25s ease, box-shadow 0.25s ease;
      position:relative;
    }

    .floating-btn span{
      position:absolute;
      right:74px;
      white-space:nowrap;
      background:rgba(17,24,39,0.92);
      color:#fff;
      font-size:14px;
      font-weight:700;
      padding:10px 14px;
      border-radius:12px;
      opacity:0;
      transform:translateX(10px);
      pointer-events:none;
      transition:0.25s ease;
    }

    .floating-btn:hover span{
      opacity:1;
      transform:translateX(0);
    }

    .floating-btn:hover{
      transform:translateY(-3px) scale(1.04);
    }

    .floating-call{
      background:linear-gradient(135deg, var(--red2), var(--red));
      animation:pulseRing 1.6s infinite;
    }

    .floating-zalo{
      background:linear-gradient(135deg, #1a7cff, #0068ff);
      animation:pulseRingBlue 1.6s infinite;
    }

    /* hero */
    .hero{
      margin-top:18px;
      min-height:740px;
      border-radius:32px;
      overflow:hidden;
      position:relative;
      box-shadow:0 26px 60px rgba(217,4,41,0.22);
    }

    .hero-bg{
      position:absolute;
      inset:0;
      background:
        linear-gradient(rgba(8,15,30,0.52), rgba(8,15,30,0.66)),
        url("https://images.unsplash.com/photo-1520607162513-77705c0f0d4a?auto=format&fit=crop&w=1600&q=80") center/cover no-repeat;
      transform:scale(1.03);
    }

    .hero-overlay{
      position:absolute;
      inset:0;
      background:
        radial-gradient(circle at 15% 20%, rgba(255,255,255,0.12), transparent 24%),
        radial-gradient(circle at 80% 20%, rgba(255,159,28,0.22), transparent 20%),
        linear-gradient(135deg, rgba(217,4,41,0.18), rgba(255,107,53,0.06));
    }

    .hero-content{
      position:relative;
      z-index:2;
      min-height:740px;
      display:grid;
      grid-template-columns:1.15fr 0.85fr;
      gap:26px;
      align-items:center;
      padding:54px 40px;
    }

    .hero-left{
      color:#fff;
    }

    .hero-badge{
      display:inline-flex;
      align-items:center;
      gap:10px;
      padding:10px 18px;
      border-radius:999px;
      background:rgba(255,255,255,0.16);
      border:1px solid rgba(255,255,255,0.22);
      backdrop-filter:blur(8px);
      font-size:14px;
      font-weight:800;
      letter-spacing:0.2px;
      margin-bottom:18px;
      animation:floatUp 2.6s ease-in-out infinite;
    }

    .hero h1{
      font-size:60px;
      line-height:1.02;
      font-weight:900;
      margin-bottom:18px;
      text-shadow:0 14px 30px rgba(0,0,0,0.26);
    }

    .hero p{
      font-size:20px;
      color:rgba(255,255,255,0.95);
      max-width:720px;
    }

    .hero-tags{
      display:flex;
      flex-wrap:wrap;
      gap:12px;
      margin-top:24px;
    }

    .hero-tags span{
      padding:11px 15px;
      border-radius:14px;
      background:rgba(255,255,255,0.14);
      border:1px solid rgba(255,255,255,0.22);
      color:#fff;
      font-size:15px;
      font-weight:700;
      backdrop-filter:blur(6px);
    }

    /* shake recruitment banner */
    .shake-banner{
      margin-top:22px;
      display:inline-flex;
      align-items:center;
      gap:10px;
      background:linear-gradient(135deg, #fff, #ffe3e3);
      color:var(--red);
      padding:14px 18px;
      border-radius:16px;
      font-size:18px;
      font-weight:900;
      box-shadow:0 12px 28px rgba(255,255,255,0.2);
      animation:shakeSoft 1.2s infinite;
    }

    .apply-card{
      background:rgba(255,255,255,0.12);
      border:1px solid rgba(255,255,255,0.22);
      backdrop-filter:blur(11px);
      color:#fff;
      border-radius:28px;
      padding:28px;
      box-shadow:0 20px 42px rgba(0,0,0,0.18);
      animation:cardFloat 3s ease-in-out infinite;
    }

    .apply-label{
      display:inline-block;
      padding:8px 14px;
      border-radius:999px;
      background:rgba(255,255,255,0.16);
      font-size:13px;
      font-weight:800;
      letter-spacing:0.4px;
      margin-bottom:12px;
    }

    .apply-card h3{
      font-size:36px;
      line-height:1.12;
      margin-bottom:10px;
      font-weight:900;
    }

    .apply-card p{
      font-size:16px;
      color:rgba(255,255,255,0.95);
    }

    .apply-list{
      list-style:none;
      margin:18px 0 22px;
      display:grid;
      gap:10px;
    }

    .apply-list li{
      background:rgba(255,255,255,0.10);
      border:1px solid rgba(255,255,255,0.08);
      padding:12px 14px;
      border-radius:14px;
      font-weight:700;
    }

    .btn{
      display:inline-flex;
      align-items:center;
      justify-content:center;
      gap:10px;
      border:none;
      border-radius:16px;
      font-weight:900;
      transition:0.25s ease;
      cursor:pointer;
    }

    .btn:hover{
      transform:translateY(-2px) scale(1.01);
    }

    .btn-main{
      width:100%;
      padding:17px 18px;
      background:#fff;
      color:var(--red);
      font-size:19px;
      box-shadow:0 14px 30px rgba(255,255,255,0.16);
      animation:pulse 1.5s infinite;
    }

    .btn-sub{
      width:100%;
      padding:15px 18px;
      background:rgba(255,255,255,0.12);
      color:#fff;
      border:1px solid rgba(255,255,255,0.2);
      font-size:16px;
      margin-top:12px;
    }

    /* stats */
    .stats{
      display:grid;
      grid-template-columns:repeat(4,1fr);
      gap:18px;
      padding:12px 34px 36px;
    }

    .stat{
      background:linear-gradient(180deg, #fff, #fff7f7);
      border:1px solid #ffe4e4;
      border-radius:22px;
      padding:24px 18px;
      text-align:center;
      box-shadow:0 10px 24px rgba(220,38,38,0.05);
    }

    .stat strong{
      display:block;
      font-size:34px;
      color:var(--red);
      line-height:1;
      margin-bottom:10px;
    }

    .stat span{
      color:#4b5563;
      font-size:15px;
      font-weight:700;
    }

    /* benefits */
    .benefit-wrap{
      padding:10px 34px 34px;
      background:
        linear-gradient(180deg, rgba(255,247,247,0.82), rgba(255,255,255,1)),
        url("https://images.unsplash.com/photo-1504384308090-c894fdcc538d?auto=format&fit=crop&w=1600&q=80") center/cover no-repeat;
    }

    .benefits{
      display:grid;
      grid-template-columns:repeat(3,1fr);
      gap:18px;
    }

    .benefit{
      background:rgba(255,255,255,0.9);
      border:1px solid rgba(255,226,226,0.95);
      backdrop-filter:blur(5px);
      border-radius:22px;
      padding:24px 20px;
      transition:transform 0.25s ease, box-shadow 0.25s ease;
      box-shadow:0 12px 25px rgba(220,38,38,0.08);
    }

    .benefit:hover{
      transform:translateY(-5px);
      box-shadow:0 18px 30px rgba(220,38,38,0.14);
    }

    .benefit-icon{
      width:60px;
      height:60px;
      border-radius:18px;
      display:flex;
      align-items:center;
      justify-content:center;
      font-size:28px;
      background:linear-gradient(135deg, #ffe3e3, #fff1d7);
      margin-bottom:16px;
    }

    .benefit h3{
      font-size:21px;
      color:#b91c1c;
      margin-bottom:10px;
    }

    .benefit p{
      color:#4b5563;
      font-size:15px;
    }

    /* job detail */
    .job-detail-grid{
      display:grid;
      grid-template-columns:1fr 1fr;
      gap:22px;
      padding:8px 34px 34px;
    }

    .job-card{
      background:linear-gradient(180deg, #ffffff, #fffafa);
      border:1px solid #ffe5e5;
      border-radius:24px;
      padding:26px;
      box-shadow:0 12px 26px rgba(220,38,38,0.05);
    }

    .job-card h3{
      font-size:26px;
      color:#111827;
      margin-bottom:14px;
    }

    .job-card ul{
      list-style:none;
      display:grid;
      gap:12px;
    }

    .job-card li{
      padding:12px 14px;
      border-radius:14px;
      background:#fff6f6;
      font-weight:700;
      color:#374151;
    }

    /* location */
    .location-area{
      background:
        linear-gradient(180deg, rgba(255,255,255,0.76), rgba(255,255,255,0.96)),
        url("https://images.unsplash.com/photo-1486406146926-c627a92ad1ab?auto=format&fit=crop&w=1600&q=80") center/cover no-repeat;
    }

    .location-grid{
      display:grid;
      grid-template-columns:0.9fr 1.1fr;
      gap:22px;
      padding:10px 34px 34px;
      align-items:stretch;
    }

    .location-card,
    .map-card{
      border-radius:24px;
      overflow:hidden;
      min-height:100%;
    }

    .location-card{
      background:rgba(255,247,237,0.93);
      border:1px solid #fed7aa;
      box-shadow:0 18px 35px rgba(249,115,22,0.1);
      color:#7c2d12;
      padding:28px;
      backdrop-filter:blur(4px);
    }

    .location-pin{
      font-size:46px;
      margin-bottom:10px;
      animation:bounce 1.8s infinite;
    }

    .location-card h3{
      font-size:30px;
      margin-bottom:14px;
    }

    .location-card p{
      font-size:17px;
    }

    .map-actions{
      display:flex;
      flex-wrap:wrap;
      gap:12px;
      margin-top:18px;
    }

    .map-btn{
      display:inline-flex;
      align-items:center;
      justify-content:center;
      padding:14px 18px;
      border-radius:14px;
      font-weight:800;
      transition:0.25s ease;
    }

    .map-btn:hover{
      transform:translateY(-2px);
    }

    .map-btn.primary{
      background:var(--red2);
      color:#fff;
      box-shadow:0 12px 24px rgba(239,35,60,0.22);
    }

    .map-btn.secondary{
      background:#fff;
      color:#b45309;
      border:1px solid #fdba74;
    }

    .qr-box{
      width:220px;
      height:220px;
      margin:20px auto 8px;
      background:#fff;
      border-radius:22px;
      padding:12px;
      box-shadow:0 16px 32px rgba(0,0,0,0.14);
    }

    .qr-box img{
      width:100%;
      height:100%;
      object-fit:contain;
      display:block;
    }

    .map-card{
      background:#fff;
      border:1px solid #ececec;
      box-shadow:0 16px 36px rgba(0,0,0,0.08);
      display:flex;
      flex-direction:column;
    }

    .map-head{
      padding:18px 20px;
      background:linear-gradient(135deg, #111827, #1f2937);
      color:#fff;
      font-weight:800;
      font-size:18px;
    }

    .map-frame{
      width:100%;
      height:100%;
      min-height:520px;
      border:0;
      display:block;
    }

    /* steps */
    .steps-area{
      background:
        linear-gradient(180deg, rgba(255,255,255,0.80), rgba(255,255,255,0.96)),
        url("https://images.unsplash.com/photo-1497366754035-f200968a6e72?auto=format&fit=crop&w=1600&q=80") center/cover no-repeat;
    }

    .steps{
      display:grid;
      grid-template-columns:repeat(3,1fr);
      gap:18px;
      padding:10px 34px 34px;
    }

    .step{
      background:rgba(255,255,255,0.92);
      border:1px solid #ececec;
      border-radius:22px;
      padding:26px 22px;
      text-align:center;
      box-shadow:0 10px 24px rgba(0,0,0,0.06);
      transition:0.25s ease;
    }

    .step:hover{
      transform:translateY(-4px);
      box-shadow:0 16px 28px rgba(0,0,0,0.1);
    }

    .step-number{
      width:58px;
      height:58px;
      border-radius:50%;
      margin:0 auto 14px;
      display:flex;
      align-items:center;
      justify-content:center;
      background:linear-gradient(135deg, var(--red2), var(--orange));
      color:#fff;
      font-size:24px;
      font-weight:900;
      animation:pulse 1.8s infinite;
    }

    .step h4{
      font-size:21px;
      margin-bottom:10px;
      color:#111827;
    }

    .step p{
      font-size:15px;
      color:var(--muted);
    }

    .step-cta{
      text-align:center;
      padding:0 34px 34px;
    }

    /* final */
    .final-cta{
      margin:28px 0 34px;
      border-radius:30px;
      padding:38px 28px;
      text-align:center;
      color:#fff;
      background:linear-gradient(135deg, #0f172a 0%, #1d3557 50%, #e63946 100%);
      box-shadow:0 22px 55px rgba(29,53,87,0.22);
      position:relative;
      overflow:hidden;
    }

    .final-cta::before{
      content:"";
      position:absolute;
      width:180px;
      height:180px;
      border-radius:50%;
      background:rgba(255,255,255,0.08);
      top:-40px;
      right:-40px;
    }

    .final-cta h2{
      position:relative;
      z-index:1;
      font-size:42px;
      margin-bottom:12px;
      line-height:1.1;
    }

    .final-cta p{
      position:relative;
      z-index:1;
      font-size:18px;
      color:rgba(255,255,255,0.92);
      margin-bottom:24px;
    }

    .contact-box{
      position:relative;
      z-index:1;
      display:inline-flex;
      flex-wrap:wrap;
      justify-content:center;
      gap:14px;
    }

    .contact-box a{
      min-width:240px;
      padding:18px 22px;
      border-radius:18px;
      font-size:20px;
      font-weight:900;
      transition:0.25s ease;
    }

    .contact-box a:hover{
      transform:translateY(-3px) scale(1.02);
    }

    .phone-btn{
      background:#fff;
      color:var(--red);
      animation:shakeSoft 1.7s infinite, glow 1.5s infinite;
    }

    .zalo-btn{
      background:rgba(255,255,255,0.12);
      color:#fff;
      border:1px solid rgba(255,255,255,0.22);
    }

    .footer-note{
      text-align:center;
      color:var(--muted);
      font-size:15px;
      font-weight:700;
      margin-bottom:24px;
    }

    /* animations */
    @keyframes pulse{
      0%{transform:scale(1);}
      50%{transform:scale(1.04);}
      100%{transform:scale(1);}
    }

    @keyframes glow{
      0%{box-shadow:0 0 0 rgba(255,255,255,0);}
      50%{box-shadow:0 0 26px rgba(255,255,255,0.55);}
      100%{box-shadow:0 0 0 rgba(255,255,255,0);}
    }

    @keyframes shakeSoft{
      0%{transform:translateX(0);}
      20%{transform:translateX(-2px);}
      40%{transform:translateX(2px);}
      60%{transform:translateX(-2px);}
      80%{transform:translateX(2px);}
      100%{transform:translateX(0);}
    }

    @keyframes bounce{
      0%,100%{transform:translateY(0);}
      50%{transform:translateY(-8px);}
    }

    @keyframes floatUp{
      0%,100%{transform:translateY(0);}
      50%{transform:translateY(-5px);}
    }

    @keyframes cardFloat{
      0%,100%{transform:translateY(0);}
      50%{transform:translateY(-6px);}
    }

    @keyframes pulseRing{
      0%{box-shadow:0 0 0 0 rgba(217,4,41,0.45);}
      70%{box-shadow:0 0 0 16px rgba(217,4,41,0);}
      100%{box-shadow:0 0 0 0 rgba(217,4,41,0);}
    }

    @keyframes pulseRingBlue{
      0%{box-shadow:0 0 0 0 rgba(0,104,255,0.42);}
      70%{box-shadow:0 0 0 16px rgba(0,104,255,0);}
      100%{box-shadow:0 0 0 0 rgba(0,104,255,0);}
    }

    /* responsive */
    @media (max-width: 1024px){
      .hero-content,
      .job-detail-grid,
      .location-grid{
        grid-template-columns:1fr;
      }

      .stats{
        grid-template-columns:repeat(2,1fr);
      }

      .benefits,
      .steps{
        grid-template-columns:1fr;
      }

      .hero{
        min-height:auto;
      }

      .hero-content{
        min-height:auto;
      }

      .hero h1{
        font-size:44px;
      }

      .section-title{
        font-size:28px;
      }

      .final-cta h2{
        font-size:34px;
      }
    }

    @media (max-width: 680px){
      .container{
        width:min(100% - 16px, 1200px);
      }

      .hero{
        border-radius:22px;
      }

      .hero-content{
        padding:28px 18px;
      }

      .hero h1{
        font-size:33px;
      }

      .hero p{
        font-size:17px;
      }

      .shake-banner{
        font-size:16px;
      }

      .apply-card h3{
        font-size:28px;
      }

      .section{
        border-radius:22px;
      }

      .section-head{
        padding:24px 18px 8px;
      }

      .benefit-wrap,
      .job-detail-grid,
      .location-grid,
      .steps,
      .stats,
      .step-cta{
        padding-left:18px;
        padding-right:18px;
      }

      .section-title{
        font-size:24px;
      }

      .stats{
        grid-template-columns:1fr;
      }

      .map-frame{
        min-height:360px;
      }

      .contact-box a{
        width:100%;
        min-width:unset;
      }

      .floating-actions{
        right:12px;
        bottom:12px;
      }

      .floating-btn{
        width:56px;
        height:56px;
        font-size:22px;
      }

      .floating-btn span{
        display:none;
      }

      .qr-box{
        width:180px;
        height:180px;
      }
    }
  </style>
</head>
<body>

  <!-- Nút nổi -->
  <div class="floating-actions">
    <a class="floating-btn floating-call" href="tel:0379281776" aria-label="Gọi điện">
      📞
      <span>Gọi ngay 0379 281 776</span>
    </a>
    <a class="floating-btn floating-zalo" href="https://zalo.me/0379281776" target="_blank" aria-label="Chat Zalo">
      Z
      <span>Chat Zalo ngay</span>
    </a>
  </div>

  <div class="container">

    <!-- HERO -->
    <section class="hero reveal">
      <div class="hero-bg"></div>
      <div class="hero-overlay"></div>

      <div class="hero-content">
        <div class="hero-left">
          <div class="hero-badge">🔥 TUYỂN DỤNG NGÀNH MAY - CƠ HỘI ĐI LÀM NGAY</div>
          <h1>
            CÔNG TY TNHH<br>
            GEU-LIM HÀ NAM<br>
            TUYỂN DỤNG
          </h1>
          <p>
            Bạn đang tìm một công việc <b>ổn định</b>, môi trường làm việc <b>thoáng mát</b>,
            đồng nghiệp <b>thân thiện</b> và có thể <b>gắn bó lâu dài</b>?
            GEU-LIM HÀ NAM đang chào đón các ứng viên mong muốn có một công việc nghiêm túc,
            thu nhập đều và cơ hội phát triển tay nghề trong ngành may.
          </p>

          <div class="hero-tags">
            <span>✅ Công việc ổn định lâu dài</span>
            <span>✅ Môi trường thân thiện</span>
            <span>✅ Thu nhập theo năng lực</span>
          </div>

          <div class="shake-banner">
            🚨 TUYỂN GẤP - LIÊN HỆ NGAY HÔM NAY ĐỂ GIỮ CƠ HỘI VIỆC LÀM TỐT
          </div>
        </div>

        <div class="apply-card">
          <div class="apply-label">APPLY NOW</div>
          <h3>🧵 Tuyển công nhân ngành may</h3>
          <p>
            Chỉ cần bạn muốn đi làm nghiêm túc, mong muốn có môi trường làm việc rõ ràng,
            ổn định và lâu dài, GEU-LIM HÀ NAM luôn sẵn sàng chào đón bạn.
          </p>

          <ul class="apply-list">
            <li>💼 Công việc ổn định quanh năm</li>
            <li>🌿 Không gian làm việc thoáng mát, sạch sẽ</li>
            <li>🤝 Đồng nghiệp hỗ trợ, dễ hòa nhập</li>
            <li>📈 Có cơ hội học hỏi và nâng tay nghề</li>
          </ul>

          <a class="btn btn-main" href="tel:0379281776">📞 Gọi ứng tuyển ngay: 0379 281 776</a>
          <a class="btn btn-sub" href="https://zalo.me/0379281776" target="_blank">💬 Nhắn Zalo để được tư vấn nhanh</a>
        </div>
      </div>
    </section>

    <!-- STATS -->
    <section class="section reveal">
      <div class="section-head">
        <h2 class="section-title">Cơ hội việc làm đáng để bạn bắt đầu ngay hôm nay</h2>
        <p class="section-sub">
          Một nơi làm việc phù hợp cho người muốn có công việc đều, môi trường ổn định và định hướng gắn bó lâu dài.
        </p>
      </div>

      <div class="stats">
        <div class="stat">
          <strong>01</strong>
          <span>Môi trường làm việc thân thiện, dễ hòa nhập</span>
        </div>
        <div class="stat">
          <strong>02</strong>
          <span>Công việc ổn định, phù hợp để gắn bó lâu dài</span>
        </div>
        <div class="stat">
          <strong>03</strong>
          <span>Có cơ hội phát triển tay nghề theo thời gian</span>
        </div>
        <div class="stat">
          <strong>04</strong>
          <span>Liên hệ nhanh qua điện thoại hoặc Zalo</span>
        </div>
      </div>
    </section>

    <!-- BENEFITS -->
    <section class="section reveal">
      <div class="section-head">
        <h2 class="section-title">Vì sao nhiều người chọn GEULIM HÀ NAM?</h2>
        <p class="section-sub">
          Không chỉ là nơi làm việc, đây còn là môi trường phù hợp cho những ai đang cần một công việc rõ ràng,
          thu nhập ổn định và có thể yên tâm gắn bó.
        </p>
      </div>

      <div class="benefit-wrap">
        <div class="benefits">
          <div class="benefit">
            <div class="benefit-icon">💼</div>
            <h3>Công việc ổn định</h3>
            <p>
              Phù hợp cho người đang tìm một công việc lâu dài, nghiêm túc và yên tâm làm việc mỗi ngày.
            </p>
          </div>

          <div class="benefit">
            <div class="benefit-icon">🌿</div>
            <h3>Môi trường thoáng mát</h3>
            <p>
              Không gian làm việc sạch sẽ, dễ chịu, tạo cảm giác thoải mái khi đi làm và gắn bó.
            </p>
          </div>

          <div class="benefit">
            <div class="benefit-icon">🤝</div>
            <h3>Đồng nghiệp thân thiện</h3>
            <p>
              Mọi người hòa đồng, hỗ trợ nhau trong công việc để ứng viên mới dễ thích nghi hơn.
            </p>
          </div>

          <div class="benefit">
            <div class="benefit-icon">📈</div>
            <h3>Phát triển tay nghề</h3>
            <p>
              Có điều kiện học hỏi, rèn kỹ năng và nâng cao tay nghề trong quá trình làm việc.
            </p>
          </div>

          <div class="benefit">
            <div class="benefit-icon">❤️</div>
            <h3>Môi trường ổn định</h3>
            <p>
              Phù hợp cho người đang cần một nơi làm việc nghiêm túc, gắn bó và xây dựng tương lai bền vững.
            </p>
          </div>

          <div class="benefit">
            <div class="benefit-icon">⚡</div>
            <h3>Ứng tuyển nhanh</h3>
            <p>
              Không cần quy trình rườm rà, chỉ cần gọi điện hoặc nhắn Zalo là có thể liên hệ ngay.
            </p>
          </div>
        </div>
      </div>
    </section>

    <!-- JOB DETAILS -->
    <section class="section reveal">
      <div class="section-head">
        <h2 class="section-title">Thông tin tuyển dụng chi tiết</h2>
        <p class="section-sub">
          Nội dung rõ ràng để ứng viên dễ theo dõi, dễ liên hệ và chủ động sắp xếp ứng tuyển.
        </p>
      </div>

      <div class="job-detail-grid">
        <div class="job-card">
          <h3>📌 Vị trí tuyển dụng</h3>
          <ul>
            <li>🧵 Công nhân ngành may</li>
            <li>✅ Phù hợp với người muốn làm việc ổn định, lâu dài</li>
            <li>✅ Phù hợp với người muốn học hỏi và nâng cao tay nghề</li>
            <li>✅ Ưu tiên ứng viên nghiêm túc, có tinh thần làm việc tốt</li>
          </ul>
        </div>

        <div class="job-card">
          <h3>🎯 Quyền lợi nổi bật</h3>
          <ul>
            <li>💰 Thu nhập ổn định theo năng lực và quá trình làm việc</li>
            <li>🌿 Không gian làm việc sạch sẽ, thoáng mát</li>
            <li>🤝 Môi trường đồng nghiệp hòa đồng, hỗ trợ nhau</li>
            <li>📞 Liên hệ ứng tuyển nhanh qua điện thoại hoặc Zalo</li>
          </ul>
        </div>
      </div>
    </section>

    <!-- LOCATION + EMBED MAP -->
    <section class="section location-area reveal">
      <div class="section-head">
        <h2 class="section-title">Địa điểm làm việc</h2>
        <p class="section-sub">
          Ứng viên có thể mở Google Maps, quét mã QR hoặc xem trực tiếp bản đồ ngay trên trang.
        </p>
      </div>

      <div class="location-grid">
        <div class="location-card">
          <div class="location-pin">📍</div>
          <h3>GEU-LIM HÀ NAM</h3>
          <p style="font-weight:800; margin-bottom:8px;">
            Công ty TNHH GEU-LIM HÀ NAM
          </p>
          <p>
            Tổ dân phố 3 - Phường Duy Tiên - Tỉnh Ninh Bình
          </p>

          <div class="map-actions">
            <a class="map-btn primary" href="https://maps.app.goo.gl/Bwc6QhLFz7cETaet7?g_st=ic" target="_blank">
              🗺️ Mở Google Maps
            </a>
            <a class="map-btn secondary" href="https://maps.app.goo.gl/Bwc6QhLFz7cETaet7?g_st=ic" target="_blank">
              📍 Xem vị trí ngay
            </a>
          </div>

          <div class="qr-box">
            <img
              src="https://api.qrserver.com/v1/create-qr-code/?size=260x260&data=https://maps.app.goo.gl/Bwc6QhLFz7cETaet7?g_st=ic"
              alt="QR mở Google Maps tới công ty"
            />
          </div>

          <p style="text-align:center; font-size:14px; color:#9a3412; font-weight:700;">
            Quét QR để mở đúng vị trí công ty trên điện thoại
          </p>
        </div>

        <div class="map-card">
          <div class="map-head">🛰️ Bản đồ nhúng trực tiếp</div>
          <iframe
            class="map-frame"
            src="https://www.google.com/maps?q=Cong%20ty%20TNHH%20GEU-LIM%20Ha%20Nam,%20To%20dan%20pho%203,%20Duy%20Tien,%20Ninh%20Binh&z=16&output=embed"
            loading="lazy"
            referrerpolicy="no-referrer-when-downgrade"
            allowfullscreen>
          </iframe>
        </div>
      </div>
    </section>

    <!-- 3 STEPS -->
    <section class="section steps-area reveal">
      <div class="section-head">
        <h2 class="section-title">Ứng tuyển cực nhanh chỉ với 3 bước</h2>
        <p class="section-sub">
          Quy trình đơn giản, rõ ràng, giúp ứng viên liên hệ nhanh và nắm cơ hội việc làm ngay.
        </p>
      </div>

      <div class="steps">
        <div class="step">
          <div class="step-number">1</div>
          <h4>Xem thông tin</h4>
          <p>
            Đọc đầy đủ nội dung tuyển dụng, quyền lợi, vị trí và địa điểm làm việc để nắm thông tin cần thiết.
          </p>
        </div>

        <div class="step">
          <div class="step-number">2</div>
          <h4>Liên hệ ngay</h4>
          <p>
            Gọi điện trực tiếp hoặc nhắn Zalo để được hướng dẫn ứng tuyển nhanh chóng, thuận tiện.
          </p>
        </div>

        <div class="step">
          <div class="step-number">3</div>
          <h4>Đến công ty</h4>
          <p>
            Mở bản đồ, quét QR hoặc đi theo Google Maps để tới công ty và bắt đầu cơ hội việc làm mới.
          </p>
        </div>
      </div>

      <div class="step-cta">
        <a class="btn btn-main" style="width:auto; min-width:290px;" href="tel:0379281776">
          📞 Ứng tuyển ngay hôm nay
        </a>
      </div>
    </section>

    <!-- FINAL CTA -->
    <section class="final-cta reveal">
      <h2>GEULIM HÀ NAM CHÀO ĐÓN BẠN GIA NHẬP</h2>
      <p>
        Nếu bạn đang cần một công việc ổn định, muốn thay đổi môi trường làm việc hoặc đang tìm cơ hội mới
        trong ngành may, hãy liên hệ ngay hôm nay để không bỏ lỡ cơ hội tốt.
      </p>

      <div class="contact-box">
        <a class="phone-btn" href="tel:0379281776">📞 0379 281 776</a>
        <a class="zalo-btn" href="https://zalo.me/0379281776" target="_blank">💬 Chat Zalo ngay</a>
      </div>
    </section>

    <div class="footer-note">
      GEU-LIM HÀ NAM - Môi trường làm việc ổn định, thân thiện và phù hợp để gắn bó lâu dài.
    </div>
  </div>

  <script>
    const reveals = document.querySelectorAll('.reveal');

    const observer = new IntersectionObserver((entries) => {
      entries.forEach((entry) => {
        if(entry.isIntersecting){
          entry.target.classList.add('show');
        }
      });
    }, { threshold: 0.15 });

    reveals.forEach((el) => observer.observe(el));
  </script>
</body>
</html>
