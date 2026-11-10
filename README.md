# abad3
<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
  <title>مدرسة عباد بن بشر للتعليم الأساسي (5-9) | المنصة التفاعلية</title>
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Tajawal:wght@400;500;700;900&display=swap" rel="stylesheet">
  <style>
    :root{
      --green:#0B6B3A;
      --gold:#C9A227;
      --gold-light:#ffdf79;
      --dark:#071a2d;
      --dark-card:rgba(12, 36, 62, 0.55);
      --neon:#00E0C6;
      --neon-glow:rgba(0, 224, 198, 0.45);
      --cream:#F5F3EE;
    }
    *{margin:0;padding:0;box-sizing:border-box;font-family:'Tajawal',sans-serif}
    body{
      background:radial-gradient(ellipse at 50% -10%, #0d3859 0%, #061829 70%, #030e17 100%);
      color:var(--cream);
      overflow-x:hidden;
      min-height:100vh;
      display:flex;
      flex-direction:column;
    }

    body::before{
      content:"";
      position:fixed;inset:0;
      background:
        radial-gradient(circle at 10% 25%, rgba(0,224,198,.18), transparent 40%),
        radial-gradient(circle at 90% 75%, rgba(201,162,39,.16), transparent 45%),
        radial-gradient(circle at 50% 50%, rgba(11,107,58,.12), transparent 50%),
        linear-gradient(rgba(0, 224, 198, 0.035) 1.2px, transparent 1.2px),
        linear-gradient(90deg, rgba(0, 224, 198, 0.035) 1.2px, transparent 1.2px),
        url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='120' height='120' viewBox='0 0 120 120'%3E%3Cpath d='M60 5 L115 60 L60 115 L5 60 Z' fill='none' stroke='%23C9A227' stroke-opacity='.07' stroke-width='1.5'/%3E%3Ccircle cx='60' cy='60' r='24' fill='none' stroke='%2300E0C6' stroke-opacity='.06' stroke-width='1.2' stroke-dasharray='4,4'/%3E%3C/svg%3E");
      background-size: auto, auto, auto, 48px 48px, 48px 48px, auto;
      z-index:-2;
    }

    /* 1) الواجهة الترحيبية */
    #welcome{
      position:fixed;inset:0;
      display:flex;flex-direction:column;
      align-items:center;justify-content:center;
      text-align:center;
      padding:24px 16px;
      background:radial-gradient(circle at 50% 40%, rgba(14, 47, 77, 0.94) 0%, rgba(5, 17, 30, 0.98) 100%);
      z-index:1000;
      overflow-y:auto;
      -webkit-overflow-scrolling:touch;
      transition:opacity .6s cubic-bezier(0.4, 0, 0.2, 1), transform .6s cubic-bezier(0.4, 0, 0.2, 1);
    }
    #welcome.hidden{
      opacity:0;
      transform:scale(1.05);
      pointer-events:none;
      display:none;
    }

    .welcome-bg-art {
      position:absolute;
      inset:0;
      background-image:url("https://moeom-my.sharepoint.com/personal/mohamed7732_moe_om/_layouts/15/download.aspx?share=cQpUcxdbStSvQoe3cB59CV%2DGEgUD%2DYcc8phjF%2D8cqgxdjVYdHg");
      background-size:cover;
      background-position:center;
      opacity:0.28;
      filter:brightness(1.05) contrast(1.1);
      mix-blend-mode:luminosity;
      pointer-events:none;
      z-index:0;
      mask-image:radial-gradient(ellipse at center, rgba(0,0,0,1) 40%, rgba(0,0,0,0) 90%);
      -webkit-mask-image:radial-gradient(ellipse at center, rgba(0,0,0,1) 40%, rgba(0,0,0,0) 90%);
    }

    .welcome-content-layer {
      position:relative;
      z-index:1;
      display:flex;
      flex-direction:column;
      align-items:center;
      justify-content:center;
      width:100%;
    }

    .badge-tag{
      background:linear-gradient(135deg, rgba(201,162,39,.18), rgba(0,224,198,.12));
      border:1px solid rgba(201,162,39,.65);
      color:var(--gold-light);
      padding:6px 20px;
      border-radius:30px;
      font-size:clamp(0.8rem, 1.8vw, 0.95rem);
      font-weight:700;
      margin-bottom:14px;
      box-shadow:0 4px 15px rgba(0,0,0,0.25), inset 0 0 12px rgba(201,162,39,0.2);
      letter-spacing:0.3px;
    }

    .welcome-title{
      font-size:clamp(1.5rem, 4.5vw, 2.8rem);
      font-weight:900;
      margin-bottom:8px;
      background:linear-gradient(90deg, #ffdf79, var(--neon), #ffffff, var(--gold));
      background-size:250% auto;
      -webkit-background-clip:text;background-clip:text;
      -webkit-text-fill-color:transparent;
      animation:shine 5s ease-in-out infinite alternate;
      line-height:1.25;
      text-shadow:0 0 35px rgba(0,224,198,0.2);
    }
    @keyframes shine{0%{background-position:0% center}100%{background-position:100% center}}

    .school-logo-wrap{
      display:flex;
      align-items:center;
      justify-content:center;
      margin-bottom:14px;
      position:relative;
      width:clamp(125px, 20vw, 165px);
      height:clamp(125px, 20vw, 165px);
      flex-shrink:0;
    }
    .school-logo-wrap::before{
      content:"";
      position:absolute;
      inset:-8px;
      border-radius:50%;
      border:2px solid transparent;
      border-top:2px solid var(--neon);
      border-bottom:2px solid var(--gold);
      animation:modernSpin 9s linear infinite;
      filter:drop-shadow(0 0 10px var(--neon));
    }
    .school-logo-wrap::after{
      content:"";
      position:absolute;
      inset:-15px;
      border-radius:50%;
      border:1.5px dashed rgba(0,224,198,0.35);
      animation:modernSpinRev 16s linear infinite;
    }

    @keyframes modernSpin{0%{transform:rotate(0deg);}100%{transform:rotate(360deg);}}
    @keyframes modernSpinRev{0%{transform:rotate(360deg);}100%{transform:rotate(0deg);}}

    .school-logo-img{
      width:88%;
      height:88%;
      object-fit:contain;
      border-radius:50%;
      background: radial-gradient(circle at 40% 30%, rgba(255,255,255,0.22), rgba(0,224,198,0.14) 40%, rgba(8,30,52,0.92) 85%);
      border: 2px solid rgba(255,255,255,0.5);
      box-shadow: 0 0 35px rgba(0,224,198,0.4), 0 12px 30px rgba(0,0,0,0.6), inset 0 0 25px rgba(201,162,39,0.35);
      backdrop-filter:blur(18px);
      -webkit-backdrop-filter:blur(18px);
      padding:clamp(8px, 2vw, 14px);
      position:relative;
      z-index:2;
      transition:transform .4s cubic-bezier(0.34, 1.56, 0.64, 1);
    }
    .school-logo-wrap:hover .school-logo-img{
      transform:scale(1.06);
      border-color:var(--neon);
    }

    .header-logo-wrap{
      display:flex;
      justify-content:center;
      align-items:center;
      margin:0 auto 10px;
      position:relative;
      width:clamp(92px, 15vw, 122px);
      height:clamp(92px, 15vw, 122px);
    }
    .header-logo-wrap::before{
      content:"";
      position:absolute;
      inset:-6px;
      border-radius:50%;
      border:1.8px solid transparent;
      border-top:1.8px solid var(--neon);
      border-bottom:1.8px solid var(--gold);
      animation:modernSpin 11s linear infinite;
      filter:drop-shadow(0 0 8px var(--neon));
    }
    .header-logo-img{
      width:88%;
      height:88%;
      object-fit:contain;
      border-radius:50%;
      background: radial-gradient(circle at 40% 30%, rgba(255,255,255,0.18), rgba(0,224,198,0.12) 45%, rgba(7,27,48,0.9) 90%);
      border:2px solid rgba(255,255,255,0.45);
      box-shadow: 0 0 28px rgba(0,224,198,0.3), 0 10px 24px rgba(0,0,0,0.5), inset 0 0 20px rgba(201,162,39,0.3);
      backdrop-filter:blur(18px);
      -webkit-backdrop-filter:blur(18px);
      padding:clamp(6px, 1.5vw, 10px);
      position:relative;
      z-index:2;
      transition:transform .3s ease;
    }
    .header-logo-wrap:hover .header-logo-img{
      transform:scale(1.06);
      border-color:var(--neon);
    }

    .school-name-badge {
      display: inline-flex;
      align-items: center;
      justify-content: center;
      gap: 6px;
      background: linear-gradient(135deg, rgba(11, 107, 58, 0.45), rgba(201, 162, 39, 0.22));
      border: 1px solid rgba(201, 162, 39, 0.65);
      border-radius: 20px;
      padding: 5px 18px;
      color: var(--gold-light);
      font-size: clamp(0.85rem, 2vw, 1rem);
      font-weight: 800;
      letter-spacing: 0.3px;
      margin-bottom: 12px;
      box-shadow: 0 4px 15px rgba(0,0,0,0.3), inset 0 0 10px rgba(201,162,39,0.25);
    }

    .fallback-emblem {
      display: inline-flex;
      align-items: center;
      justify-content: center;
      border-radius:50%;
      background: radial-gradient(circle at 35% 30%, rgba(255,255,255,0.18), rgba(11,107,58,0.4) 45%, rgba(6,22,38,0.95) 100%) !important;
      border: 2px solid rgba(0,224,198,0.6) !important;
    }

    .welcome-card-box {
      background:linear-gradient(145deg, rgba(255,255,255,0.08), rgba(10,38,66,0.5));
      border:1px solid rgba(0,224,198,0.35);
      border-radius:24px;
      padding:clamp(18px, 4vw, 26px);
      max-width:680px;
      width:100%;
      margin:0 auto 18px;
      backdrop-filter:blur(16px);
      -webkit-backdrop-filter:blur(16px);
      box-shadow:0 15px 40px rgba(0,0,0,0.4), inset 0 1px 1px rgba(255,255,255,0.2);
    }

    .welcome-clock{
      display:flex;gap:12px;flex-wrap:wrap;justify-content:center;
      margin-bottom:22px;
      width:100%;
      max-width:620px;
    }
    .welcome-clock span{
      background:rgba(8, 30, 52, 0.65);
      border:1px solid rgba(0,224,198,.35);
      padding:9px 20px;border-radius:30px;
      font-size:clamp(0.82rem, 2vw, 0.94rem);
      color:var(--cream);
      display:inline-flex;
      align-items:center;
      gap:8px;
      backdrop-filter:blur(10px);
      box-shadow:0 4px 15px rgba(0,0,0,0.25);
    }
    .welcome-clock span b{color:var(--neon);font-weight:700;}

    .enter-btn{
      background:linear-gradient(135deg, #098848 0%, var(--neon) 100%);
      color:#021914;
      border:none;
      padding:clamp(13px, 2.5vw, 17px) clamp(36px, 6vw, 60px);
      font-size:clamp(1.05rem, 2.5vw, 1.25rem);
      font-weight:900;
      border-radius:50px;
      cursor:pointer;
      box-shadow:0 0 35px rgba(0,224,198,.55), 0 8px 25px rgba(0,0,0,0.35);
      transition:all .35s cubic-bezier(0.34, 1.56, 0.64, 1);
      max-width:90%;
      position:relative;
      overflow:hidden;
    }
    .enter-btn:hover{
      transform:translateY(-3px) scale(1.03);
      box-shadow:0 0 50px rgba(0,224,198,.8), 0 14px 30px rgba(0,0,0,0.45);
    }

    .hint{
      font-size:clamp(0.75rem, 1.8vw, 0.85rem);
      color:#859bb3;
      margin-top:14px;
    }

    /* 2) المنصة الرئيسية */
    #main{
      display:none;
      opacity:0;
      transition:opacity .6s ease;
      width:100%;
      min-height:100vh;
      flex-direction:column;
    }
    #main.show{
      display:flex;
      opacity:1;
    }

    header{
      text-align:center;
      padding:clamp(25px, 5vw, 42px) 16px 16px;
      position:relative;
      overflow:hidden;
    }
    .header-bg-art {
      position:absolute;
      inset:0;
      background-image:url("https://moeom-my.sharepoint.com/personal/mohamed7732_moe_om/_layouts/15/download.aspx?share=cQpUcxdbStSvQoe3cB59CV%2DGEgUD%2DYcc8phjF%2D8cqgxdjVYdHg");
      background-size:cover;
      background-position:center;
      opacity:0.28;
      filter:brightness(1.05) contrast(1.1);
      mix-blend-mode:luminosity;
      pointer-events:none;
      z-index:0;
      mask-image:radial-gradient(ellipse at center, rgba(0,0,0,1) 40%, rgba(0,0,0,0) 92%);
      -webkit-mask-image:radial-gradient(ellipse at center, rgba(0,0,0,1) 40%, rgba(0,0,0,0) 92%);
    }
    .header-content {
      position:relative;
      z-index:1;
    }
    h1{
      font-size:clamp(1.55rem, 4vw, 2.6rem);
      font-weight:900;
      background:linear-gradient(90deg, #ffdf79, var(--neon), #ffffff, var(--gold));
      background-size:250% auto;
      -webkit-background-clip:text;background-clip:text;
      -webkit-text-fill-color:transparent;
      animation:shine 5s ease-in-out infinite alternate;
      line-height:1.3;
    }
    header p{
      color:#c2d6e7;
      margin-top:6px;
      font-size:clamp(0.85rem, 2vw, 1.05rem);
      text-shadow:0 2px 8px rgba(0,0,0,0.6);
    }

    .ticker-wrap {
      max-width: 1240px;
      width: 100%;
      margin: 12px auto;
      padding: 0 16px;
    }
    .ticker-box {
      display: flex;
      align-items: center;
      background: linear-gradient(135deg, rgba(11, 107, 58, 0.38), rgba(9, 32, 56, 0.85));
      border: 1px solid rgba(201, 162, 39, 0.55);
      border-radius: 40px;
      overflow: hidden;
      box-shadow: 0 8px 30px rgba(0, 0, 0, 0.35), inset 0 0 20px rgba(0, 224, 198, 0.1);
      backdrop-filter:blur(14px);
    }
    .ticker-badge {
      background: linear-gradient(135deg, var(--gold), #ffe28a);
      color: #03121f;
      padding: 10px 20px;
      font-weight: 900;
      font-size: clamp(0.8rem, 2vw, 0.95rem);
      display: flex;
      align-items: center;
      gap: 8px;
      white-space: nowrap;
      z-index: 2;
      flex-shrink:0;
      box-shadow: 2px 0 12px rgba(0,0,0,0.25);
    }
    .ticker-track {
      flex: 1;
      overflow: hidden;
      position: relative;
      white-space: nowrap;
      padding: 9px 0;
    }
    .ticker-content {
      display: inline-block;
      white-space: nowrap;
      padding-left: 100%;
      animation: tickerMove 28s linear infinite;
      font-weight: 500;
      font-size: clamp(0.85rem, 2vw, 0.95rem);
      color: var(--cream);
    }
    .ticker-track:hover .ticker-content {
      animation-play-state: paused;
      cursor: default;
    }
    .ticker-content span {
      display: inline-block;
      margin-right: 32px;
    }
    .ticker-content span b {
      color: var(--gold-light);
      font-weight: 700;
    }
    .ticker-content span i {
      color: var(--neon);
      font-style: normal;
    }
    @keyframes tickerMove {
      0% { transform: translate3d(0, 0, 0); }
      100% { transform: translate3d(100%, 0, 0); }
    }

    /* 3) شبكة الأيقونات التفاعلية */
    .grid{
      display:grid;
      grid-template-columns: repeat(auto-fit, minmax(245px, 1fr));
      gap: 20px;
      max-width: 1240px;
      width: 100%;
      margin: 22px auto 45px;
      padding: 0 16px;
      flex: 1;
    }
    .card{
      background: var(--dark-card);
      border: 1px solid rgba(0,224,198,.22);
      border-radius: 24px;
      padding: 26px 18px;
      text-align: center;
      cursor: pointer;
      backdrop-filter: blur(14px);
      -webkit-backdrop-filter: blur(14px);
      transition: all .4s cubic-bezier(0.165, 0.84, 0.44, 1);
      position: relative;
      overflow: hidden;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      box-shadow: 0 10px 25px rgba(0,0,0,0.3), inset 0 1px 1px rgba(255,255,255,0.12);
    }
    .card::before {
      content: "";
      position: absolute;
      inset: 0;
      background: radial-gradient(circle at 50% 0%, rgba(0,224,198,0.18), transparent 70%);
      opacity: 0;
      transition: opacity .4s ease;
      pointer-events: none;
    }
    .card:hover{
      transform: translateY(-8px) scale(1.015);
      border-color: var(--neon);
      box-shadow: 0 18px 40px rgba(0,224,198,.3), 0 0 20px rgba(0,224,198,0.15), inset 0 1px 2px rgba(255,255,255,0.25);
      background: rgba(16, 46, 78, 0.7);
    }
    .card:hover::before {
      opacity: 1;
    }
    .icon-wrap{
      width: 68px;
      height: 68px;
      border-radius: 20px;
      background: radial-gradient(circle at 35% 25%, rgba(255,255,255,0.22), rgba(0,224,198,0.12) 55%, rgba(6,25,44,0.92));
      border: 1.5px solid rgba(0,224,198,0.4);
      display: flex;
      align-items: center;
      justify-content: center;
      margin-bottom: 16px;
      position: relative;
      box-shadow: 0 8px 20px rgba(0,0,0,0.4), inset 0 0 14px rgba(0,224,198,0.25);
      transition: all .45s cubic-bezier(0.34, 1.56, 0.64, 1);
      backdrop-filter: blur(12px);
      -webkit-backdrop-filter: blur(12px);
    }
    .icon-wrap::after{
      content: "";
      position: absolute;
      inset: -4px;
      border-radius: 24px;
      border: 1.5px solid transparent;
      border-top-color: var(--neon);
      border-bottom-color: var(--gold);
      opacity: 0.6;
      transition: all .4s ease;
      filter: drop-shadow(0 0 6px var(--neon));
    }
    .card:hover .icon-wrap{
      transform: translateY(-4px) scale(1.12) rotate(3deg);
      border-color: var(--neon);
      box-shadow: 0 12px 30px rgba(0,224,198,0.55), inset 0 0 20px rgba(201,162,39,0.4);
      background: radial-gradient(circle at 35% 25%, rgba(255,255,255,0.3), rgba(0,224,198,0.2) 60%, rgba(7,35,62,0.95));
    }
    .card:hover .icon-wrap::after{
      opacity: 1;
      transform: rotate(180deg);
      inset: -6px;
    }
    .icon-svg{
      width: 36px;
      height: 36px;
      display: block;
      transition: transform .35s ease, filter .35s ease;
      filter: drop-shadow(0 2px 6px rgba(0,0,0,0.35));
    }
    .card:hover .icon-svg{
      transform: scale(1.08);
      filter: drop-shadow(0 0 8px var(--neon));
    }
    .card h3{
      font-size: clamp(1.05rem, 2vw, 1.22rem);
      color: var(--cream);
      font-weight: 700;
      line-height: 1.35;
      transition: color .3s ease;
    }
    .card:hover h3{
      color: #ffffff;
      text-shadow: 0 0 12px rgba(0,224,198,0.4);
    }
    .card small{
      color: #92a7bd;
      font-size: clamp(0.78rem, 1.8vw, 0.86rem);
      display: block;
      margin-top: 6px;
      transition: color .3s ease;
    }
    .card:hover small{
      color: #b8cde0;
    }

    /* 4) النافذة المنبثقة */
    .modal-overlay{
      position:fixed;inset:0;
      background:rgba(4,12,20,.88);
      backdrop-filter:blur(10px);
      -webkit-backdrop-filter:blur(10px);
      display:none;align-items:center;justify-content:center;
      z-index:2000;
      padding:16px;
    }
    .modal-overlay.active{display:flex;}
    .modal{
      background:linear-gradient(150deg,#0e3152,#081b2d);
      border:1.5px solid rgba(0,224,198,0.6);
      border-radius:26px;
      max-width:720px;
      width:100%;
      max-height:88vh;
      overflow-y:auto;
      padding:clamp(22px, 4vw, 34px);
      box-shadow:0 30px 80px rgba(0,224,198,.35), 0 10px 40px rgba(0,0,0,0.6), inset 0 1px 1px rgba(255,255,255,0.25);
      position:relative;
    }
    .modal h2{
      color:var(--gold-light);
      font-size:clamp(1.3rem, 3vw, 1.65rem);
      margin-bottom:18px;
      display:flex;
      align-items:center;
      gap:12px;
      padding-left:38px;
      line-height:1.3;
    }
    .modal p, .modal li{
      line-height:1.9;
      color:#d9e6f2;
      margin-bottom:9px;
      font-size:clamp(0.92rem, 2vw, 1.02rem);
    }
    .modal ul{padding-right:22px}
    .close-btn{
      position:absolute;top:18px;left:18px;
      background:rgba(0,224,198,0.1);border:1px solid var(--neon);
      color:var(--neon);width:38px;height:38px;border-radius:50%;
      font-size:1.25rem;cursor:pointer;transition:.3s;
      display:flex;align-items:center;justify-content:center;
      flex-shrink:0;
      box-shadow:0 2px 10px rgba(0,0,0,0.3);
    }
    .close-btn:hover{
      background:var(--neon);
      color:var(--dark);
      transform:rotate(90deg);
      box-shadow:0 0 18px var(--neon);
    }

    .btn-link{
      display:inline-flex;align-items:center;gap:8px;
      background:linear-gradient(135deg,var(--green),var(--neon));
      color:#001a14;padding:10px 20px;border-radius:28px;
      text-decoration:none;font-weight:800;margin-top:10px;
      font-size:clamp(0.85rem, 2vw, 0.95rem);
      transition:all .3s cubic-bezier(0.34, 1.56, 0.64, 1);
      box-shadow:0 4px 15px rgba(0,224,198,0.3);
    }
    .btn-link:hover{
      transform:translateY(-2px) scale(1.04);
      box-shadow:0 6px 25px rgba(0,224,198,0.55);
    }

    /* 5) التذييل */
    footer{
      text-align:center;
      padding:26px 16px;
      color:#859bb0;
      border-top:1px solid rgba(0,224,198,.15);
      margin-top:auto;
      font-size:clamp(0.8rem, 1.8vw, 0.9rem);
      background:rgba(4, 15, 26, 0.4);
      backdrop-filter:blur(8px);
    }
    footer strong{color:var(--gold-light)}

    @media(min-width: 1025px){
      .grid{
        grid-template-columns: repeat(4, 1fr);
        gap: 24px;
      }
      .card{
        padding: 32px 20px;
      }
    }
    @media(min-width: 651px) and (max-width: 1024px){
      .grid{
        grid-template-columns: repeat(3, 1fr);
        gap: 18px;
      }
    }
    @media(max-width:650px){
      .grid{
        grid-template-columns: repeat(2, 1fr);
        gap: 12px;
        padding: 0 12px;
      }
      .card{
        padding: 20px 10px;
        border-radius: 18px;
      }
      .icon-wrap{
        width: 56px;
        height: 56px;
        border-radius: 16px;
        margin-bottom: 12px;
      }
      .icon-svg{
        width: 30px;
        height: 30px;
      }
      .card small{
        display: -webkit-box;
        -webkit-line-clamp: 2;
        -webkit-box-orient: vertical;
        overflow: hidden;
      }
      .ticker-box {
        flex-direction: row;
        border-radius: 28px;
      }
      .ticker-badge {
        padding: 8px 12px;
      }
      .welcome-clock {
        gap: 8px;
      }
      .welcome-clock span {
        padding: 7px 14px;
        width: 100%;
        justify-content: center;
      }
    }
    @media(max-width: 360px){
      .grid{
        grid-template-columns: 1fr;
      }
    }
  </style>
</head>
<body>

<!-- ================= 1) الواجهة الترحيبية ================= -->
<div id="welcome">
  <div class="welcome-bg-art"></div>
  <div class="welcome-content-layer">
    <div class="school-logo-wrap" id="welcomeLogoWrap">
      <img 
        src="https://moeom-my.sharepoint.com/personal/mohamed7732_moe_om/_layouts/15/download.aspx?share=cQqT0CP48YCfTppsBpFS1huREgUDdECylT6tmPiE4euWpLhkhA" 
        alt="الخنجر العماني - مدرسة عباد بن بشر" 
        class="school-logo-img" 
        crossorigin="anonymous"
        onerror="handleLogoError(this, 'welcome')" 
      />
    </div>
    <div class="school-name-badge">مدرسة عباد بن بشر ( 5 - 9 )</div>
    <div class="badge-tag">سلطنة عُمان | محافظة الظاهرة — ولاية عبري</div>
    <h1 class="welcome-title">أهلاً وسهلاً بكم في بوابتنا الرقمية</h1>
    
    <div class="welcome-card-box">
      <p style="font-size:clamp(1rem, 2.5vw, 1.15rem); font-weight:800; color:var(--gold); margin-bottom:8px;">
        ✨ رسالة ترحيبية من إدارة المدرسة ✨
      </p>
      <p style="font-size:clamp(0.85rem, 2vw, 0.98rem); line-height:1.8; color:#dce7f2;">
        يسرنا ويسعدنا أن نرحب بكم في رحاب صرحنا التعليمي ومنصتنا التفاعلية الذكية. نفتح لكم أبوابنا وقلوبنا في هذا الصرح العلمي الذي نسعى من خلاله إلى غرس القيم الوطنية الأصيلة، وبناء جيل متسلح بمهارات الغد والتقنية الرقمية، متمنين لأبنائنا الطلبة عاماً حافلاً بالإنجاز والتميز.
      </p>
      <div style="margin-top:10px; font-size:clamp(0.75rem, 1.8vw, 0.85rem); color:var(--neon); font-weight:700;">
        «معاً نرتقي بتعليم أبنائنا نحو المستقبل»
      </div>
    </div>

    <div class="welcome-clock">
      <span>📅 <b id="todayDate">—</b></span>
      <span>🕐 <b id="nowTime">—</b></span>
    </div>

    <button class="enter-btn" onclick="enterPlatform()">ادخل إلى المنصة ✦</button>
    <div class="hint">اضغط على الزر أعلاه للدخول إلى المنصة ✦</div>
  </div>
</div>

<!-- ================= 2) المنصة الرئيسية ================= -->
<div id="main">

  <!-- الترويسة الرئيسية -->
  <header>
    <div class="header-bg-art"></div>
    <div class="header-content">
      <div class="header-logo-wrap" id="headerLogoWrap">
        <img 
          src="https://moeom-my.sharepoint.com/personal/mohamed7732_moe_om/_layouts/15/download.aspx?share=cQqT0CP48YCfTppsBpFS1huREgUDdECylT6tmPiE4euWpLhkhA" 
          alt="الخنجر العماني - مدرسة عباد بن بشر" 
          class="header-logo-img" 
          crossorigin="anonymous"
          onerror="handleLogoError(this, 'header')" 
        />
      </div>
      <div class="school-name-badge">مدرسة عباد بن بشر ( 5 - 9 )</div>
      <h1>أهلاً بكم في بوابتكم التعليمية والتربوية</h1>
      <p>نافذتكم الرقمية نحو التميز العلمي وبناء مهارات المستقبل ✨</p>
    </div>
  </header>

  <!-- شريط الإعلانات والتنبيهات المدرسية المتحرك -->
  <div class="ticker-wrap">
    <div class="ticker-box">
      <div class="ticker-badge">📢 إعلانات وتنبيهات</div>
      <div class="ticker-track">
        <div class="ticker-content">
          <span>✨ <b>أهلاً وسهلاً</b> بجميع الطلبة وأولياء الأمور في مدرسة عباد بن بشر للتعليم الأساسي (٥-٩).</span>
          <span>⏰ <b>تذكير:</b> يبدأ الطابور الصباحي في تمام الساعة <i>٧:١٥ صباحاً</i> — نرجو الالتزام بالحضور المبكر.</span>
          <span>👔 <b>الزي المدرسي:</b> نؤكد على أهمية الالتزام بالدشداشة العمانية والمصر/الكمة تعزيزاً للهوية الوطنية.</span>
          <span>📱 <b>التواصل الرسمي:</b> تابعوا أحدث الفعاليات والأنشطة عبر حسابنا الرسمي في منصة X.</span>
          <span>📞 <b>هاتف المدرسة:</b> للرد على استفساراتكم يمكنكم التواصل على الرقم المباشر: <i>٢٢٤٩٥١٤٣</i>.</span>
        </div>
      </div>
    </div>
  </div>

  <!-- شبكة الأيقونات التفاعلية -->
  <main class="grid" id="grid"></main>

  <!-- التذييل -->
  <footer>
    <p>© مدرسة <strong>عباد بن بشر للتعليم الأساسي (٥-٩)</strong> — محافظة الظاهرة، ولاية عبري</p>
  </footer>

</div>

<!-- ================= 3) النافذة المنبثقة ================= -->
<div class="modal-overlay" id="modal">
  <div class="modal">
    <button class="close-btn" onclick="closeModal()">✕</button>
    <h2 id="modalTitle"></h2>
    <div id="modalBody"></div>
  </div>
</div>

<!-- ================= 4) JavaScript ================= -->
<script>
function handleLogoError(imgElement, context) {
  const wrap = imgElement.parentElement;
  if (!wrap) return;
  const size = context === 'welcome' ? '85%' : '80%';
  wrap.innerHTML = `
    <div class="fallback-emblem" style="width:${size}; height:${size};">
      <svg viewBox="0 0 100 100" style="width:72%; height:72%;">
        <defs>
          <linearGradient id="cyberGold" x1="0%" y1="0%" x2="100%" y2="100%">
            <stop offset="0%" stop-color="#fff" />
            <stop offset="40%" stop-color="#ffd859" />
            <stop offset="80%" stop-color="#C9A227" />
            <stop offset="100%" stop-color="#00E0C6" />
          </linearGradient>
        </defs>
        <path d="M50 18 L60 48 L40 48 Z" fill="url(#cyberGold)" opacity="0.95" />
        <line x1="16" y1="18" x2="84" y2="84" stroke="url(#cyberGold)" stroke-width="4.5" stroke-linecap="round" />
        <line x1="84" y1="18" x2="16" y2="84" stroke="url(#cyberGold)" stroke-width="4.5" stroke-linecap="round" />
        <rect x="36" y="47" width="28" height="9" rx="3.5" fill="#0B6B3A" stroke="url(#cyberGold)" stroke-width="1.8" />
        <path d="M48 56 C48 74 38 83 24 85 C22 81 29 74 35 71 C40 68 42 63 42 56 Z" fill="url(#cyberGold)" />
        <circle cx="50" cy="50" r="42" fill="none" stroke="url(#cyberGold)" stroke-width="1.5" stroke-dasharray="4,4" opacity="0.6"/>
      </svg>
    </div>
  `;
}

const svgIcons = {
  vision: `
    <svg class="icon-svg" viewBox="0 0 48 48" fill="none" xmlns="http://www.w3.org/2000/svg">
      <defs>
        <linearGradient id="gVision" x1="0%" y1="0%" x2="100%" y2="100%">
          <stop offset="0%" stop-color="#ffdf79"/>
          <stop offset="100%" stop-color="#00E0C6"/>
        </linearGradient>
      </defs>
      <circle cx="24" cy="24" r="19" stroke="url(#gVision)" stroke-width="2.5" stroke-dasharray="4 3" opacity="0.6"/>
      <circle cx="24" cy="24" r="13" fill="rgba(0,224,198,0.12)" stroke="url(#gVision)" stroke-width="2.2"/>
      <circle cx="24" cy="24" r="5" fill="#C9A227"/>
      <path d="M24 5V11M24 37V43M5 24H11M37 24H43" stroke="url(#gVision)" stroke-width="2.5" stroke-linecap="round"/>
      <path d="M34 14L37 11M14 34L11 37" stroke="#ffdf79" stroke-width="2" stroke-linecap="round"/>
    </svg>`,
  
  info: `
    <svg class="icon-svg" viewBox="0 0 48 48" fill="none" xmlns="http://www.w3.org/2000/svg">
      <defs>
        <linearGradient id="gInfo" x1="0%" y1="0%" x2="100%" y2="100%">
          <stop offset="0%" stop-color="#00E0C6"/>
          <stop offset="100%" stop-color="#0B6B3A"/>
        </linearGradient>
      </defs>
      <path d="M6 14C6 11.8 7.8 10 10 10H38C40.2 10 42 11.8 42 14V34C42 36.2 40.2 38 38 38H10C7.8 38 6 36.2 6 34V14Z" fill="rgba(11,107,58,0.2)" stroke="url(#gInfo)" stroke-width="2.5"/>
      <circle cx="24" cy="20" r="4.5" fill="#ffdf79"/>
      <path d="M16 32C16 28 19.5 26.5 24 26.5C28.5 26.5 32 28 32 32" stroke="#ffdf79" stroke-width="2.5" stroke-linecap="round"/>
      <path d="M35 18H37M35 24H37" stroke="url(#gInfo)" stroke-width="2.5" stroke-linecap="round"/>
    </svg>`,

  partnership: `
    <svg class="icon-svg" viewBox="0 0 48 48" fill="none" xmlns="http://www.w3.org/2000/svg">
      <defs>
        <linearGradient id="gPart" x1="0%" y1="0%" x2="100%" y2="100%">
          <stop offset="0%" stop-color="#ffdf79"/>
          <stop offset="100%" stop-color="#00E0C6"/>
        </linearGradient>
      </defs>
      <path d="M8 20L18 29L24 23L15 14L8 20Z" fill="rgba(201,162,39,0.25)" stroke="url(#gPart)" stroke-width="2.2" stroke-linejoin="round"/>
      <path d="M40 20L30 29L24 23L33 14L40 20Z" fill="rgba(0,224,198,0.2)" stroke="url(#gPart)" stroke-width="2.2" stroke-linejoin="round"/>
      <path d="M18 29L24 35L30 29" stroke="url(#gPart)" stroke-width="2.5" stroke-linecap="round" stroke-linejoin="round"/>
      <circle cx="24" cy="11" r="3.5" fill="#00E0C6"/>
      <path d="M21 41H27" stroke="#ffdf79" stroke-width="2.5" stroke-linecap="round"/>
    </svg>`,

  awards: `
    <svg class="icon-svg" viewBox="0 0 48 48" fill="none" xmlns="http://www.w3.org/2000/svg">
      <defs>
        <linearGradient id="gTrophy" x1="0%" y1="0%" x2="100%" y2="100%">
          <stop offset="0%" stop-color="#ffdf79"/>
          <stop offset="100%" stop-color="#C9A227"/>
        </linearGradient>
      </defs>
      <path d="M14 9H34V20C34 26 29.5 30 24 30C18.5 30 14 26 14 20V9Z" fill="rgba(201,162,39,0.25)" stroke="url(#gTrophy)" stroke-width="2.5"/>
      <path d="M14 13H8C6.9 13 6 13.9 6 15C6 19 9 22 14 22V13Z" stroke="#00E0C6" stroke-width="2.2" stroke-linejoin="round"/>
      <path d="M34 13H40C41.1 13 42 13.9 42 15C42 19 39 22 34 22V13Z" stroke="#00E0C6" stroke-width="2.2" stroke-linejoin="round"/>
      <path d="M24 30V37M17 41H31" stroke="url(#gTrophy)" stroke-width="2.5" stroke-linecap="round"/>
      <polygon points="24,14 25.5,18 29.5,18.5 26.5,21 27.5,25 24,22.8 20.5,25 21.5,21 18.5,18.5 22.5,18" fill="url(#gTrophy)"/>
    </svg>`,

  exams: `
    <svg class="icon-svg" viewBox="0 0 48 48" fill="none" xmlns="http://www.w3.org/2000/svg">
      <defs>
        <linearGradient id="gExam" x1="0%" y1="0%" x2="100%" y2="100%">
          <stop offset="0%" stop-color="#00E0C6"/>
          <stop offset="100%" stop-color="#ffdf79"/>
        </linearGradient>
      </defs>
      <path d="M10 8H32L38 14V40C38 41.1 37.1 42 36 42H10C8.9 42 8 41.1 8 40V10C8 8.9 8.9 8 10 8Z" fill="rgba(8,30,52,0.6)" stroke="url(#gExam)" stroke-width="2.5"/>
      <path d="M32 8V14H38" stroke="url(#gExam)" stroke-width="2.2"/>
      <path d="M15 22H27M15 28H31M15 34H23" stroke="#00E0C6" stroke-width="2.2" stroke-linecap="round"/>
      <circle cx="31" cy="34" r="2.5" fill="#ffdf79"/>
    </svg>`,

  schedule: `
    <svg class="icon-svg" viewBox="0 0 48 48" fill="none" xmlns="http://www.w3.org/2000/svg">
      <defs>
        <linearGradient id="gSched" x1="0%" y1="0%" x2="100%" y2="100%">
          <stop offset="0%" stop-color="#00E0C6"/>
          <stop offset="100%" stop-color="#C9A227"/>
        </linearGradient>
      </defs>
      <rect x="7" y="10" width="34" height="31" rx="6" fill="rgba(0,224,198,0.12)" stroke="url(#gSched)" stroke-width="2.5"/>
      <path d="M7 18H41" stroke="url(#gSched)" stroke-width="2"/>
      <path d="M15 6V11M33 6V11" stroke="#ffdf79" stroke-width="2.5" stroke-linecap="round"/>
      <circle cx="16" cy="25" r="2" fill="#00E0C6"/>
      <circle cx="24" cy="25" r="2" fill="#ffdf79"/>
      <circle cx="32" cy="25" r="2" fill="#00E0C6"/>
      <circle cx="16" cy="33" r="2" fill="#ffdf79"/>
      <circle cx="24" cy="33" r="2" fill="#00E0C6"/>
      <circle cx="32" cy="33" r="2" fill="#ffdf79"/>
    </svg>`,

  gallery: `
    <svg class="icon-svg" viewBox="0 0 48 48" fill="none" xmlns="http://www.w3.org/2000/svg">
      <defs>
        <linearGradient id="gGal" x1="0%" y1="0%" x2="100%" y2="100%">
          <stop offset="0%" stop-color="#ffdf79"/>
          <stop offset="100%" stop-color="#00E0C6"/>
        </linearGradient>
      </defs>
      <rect x="7" y="9" width="34" height="30" rx="5" fill="rgba(11,107,58,0.2)" stroke="url(#gGal)" stroke-width="2.5"/>
      <circle cx="16" cy="18" r="3.5" fill="#ffdf79"/>
      <path d="M8 34L18 24L28 33L33 28L40 34" stroke="url(#gGal)" stroke-width="2.5" stroke-linecap="round" stroke-linejoin="round"/>
    </svg>`,

  activities: `
    <svg class="icon-svg" viewBox="0 0 48 48" fill="none" xmlns="http://www.w3.org/2000/svg">
      <defs>
        <linearGradient id="gAct" x1="0%" y1="0%" x2="100%" y2="100%">
          <stop offset="0%" stop-color="#00E0C6"/>
          <stop offset="100%" stop-color="#ffdf79"/>
        </linearGradient>
      </defs>
      <path d="M24 7L39 15L24 23L9 15L24 7Z" fill="rgba(0,224,198,0.22)" stroke="url(#gAct)" stroke-width="2.5" stroke-linejoin="round"/>
      <path d="M14 20.5V31C14 34.5 18.5 38 24 38C29.5 38 34 34.5 34 31V20.5" stroke="url(#gAct)" stroke-width="2.2"/>
      <path d="M39 15V27M41 27H37" stroke="#ffdf79" stroke-width="2.2" stroke-linecap="round"/>
    </svg>`,

  contact: `
    <svg class="icon-svg" viewBox="0 0 48 48" fill="none" xmlns="http://www.w3.org/2000/svg">
      <defs>
        <linearGradient id="gCont" x1="0%" y1="0%" x2="100%" y2="100%">
          <stop offset="0%" stop-color="#ffdf79"/>
          <stop offset="100%" stop-color="#00E0C6"/>
        </linearGradient>
      </defs>
      <rect x="13" y="6" width="22" height="36" rx="5" fill="rgba(8,30,52,0.7)" stroke="url(#gCont)" stroke-width="2.5"/>
      <line x1="21" y1="10" x2="27" y2="10" stroke="#00E0C6" stroke-width="2" stroke-linecap="round"/>
      <circle cx="24" cy="36" r="2.2" fill="#ffdf79"/>
      <path d="M6 18C4 23 4 27 6 32" stroke="url(#gCont)" stroke-width="2.2" stroke-linecap="round"/>
      <path d="M42 18C44 23 44 27 42 32" stroke="url(#gCont)" stroke-width="2.2" stroke-linecap="round"/>
    </svg>`,

  indicators: `
    <svg class="icon-svg" viewBox="0 0 48 48" fill="none" xmlns="http://www.w3.org/2000/svg">
      <defs>
        <linearGradient id="gInd" x1="0%" y1="0%" x2="100%" y2="100%">
          <stop offset="0%" stop-color="#00E0C6"/>
          <stop offset="100%" stop-color="#C9A227"/>
        </linearGradient>
      </defs>
      <path d="M7 40H41" stroke="#ffdf79" stroke-width="2.5" stroke-linecap="round"/>
      <rect x="11" y="26" width="6" height="11" rx="2" fill="rgba(0,224,198,0.3)" stroke="url(#gInd)" stroke-width="2"/>
      <rect x="21" y="18" width="6" height="19" rx="2" fill="rgba(201,162,39,0.3)" stroke="url(#gInd)" stroke-width="2"/>
      <rect x="31" y="11" width="6" height="26" rx="2" fill="rgba(0,224,198,0.5)" stroke="url(#gInd)" stroke-width="2"/>
      <path d="M12 21L21 13L29 17L38 8" stroke="#ffdf79" stroke-width="2.2" stroke-linecap="round" stroke-linejoin="round"/>
      <circle cx="38" cy="8" r="2" fill="#00E0C6"/>
    </svg>`
};

const sections = [
  {iconKey:"vision", title:"الرؤية والرسالة", sub:"هويتنا وقيمنا",
   content:`
     <div style="text-align:center;padding:10px 0 20px;">
       <div style="display:inline-block;background:linear-gradient(135deg,#0B6B3A,#C9A227);color:#001a14;padding:6px 20px;border-radius:20px;font-weight:900;font-size:.9rem;margin-bottom:14px;">🎯 رؤيتنا</div>
       <p style="font-size:1.15rem;line-height:1.95;color:#e8d9a8;font-weight:700;">
         «إِعْدَادُ جِيلٍ مَتَمَكِّنٍ مِنْ مَهَارَاتِ الْمُسْتَقْبَلِ، مُتَشَبِّعٍ بِقِيَمِ الْمُواطَنَةِ»
       </p>
     </div>
     <hr style="border:none;border-top:1px solid rgba(201,162,39,.3);margin:22px 0;">
     <div style="text-align:center;padding:10px 0;">
       <div style="display:inline-block;background:linear-gradient(135deg,#00E0C6,#0B6B3A);color:#001a14;padding:6px 20px;border-radius:20px;font-weight:900;font-size:.9rem;margin-bottom:14px;">📜 رسالتنا</div>
       <p style="font-size:1rem;line-height:1.95;color:#d7e3ee;text-align:justify;">
         نَلْتَزِمُ فِي مَدْرَسَةِ عَبَّادِ بْنِ بِشْرٍ بِجَوْدَةٍ عَالِيَةٍ فِي الْأَدَاءِ، يُعَزِّزُ الْقِيَمَ الْوَطَنِيَّةَ، وَيُرَكِّزُ عَلَى مَهَارَاتِ التَّفْكِيرِ الْإِبْدَاعِيِّ وَالتَّعَلُّمِ الذَّاتِيِّ وَالْعَمَلِ الْجَمَاعِيِّ، مِنْ خِلَالِ بِيئَةٍ شَامِلَةٍ وَآمِنَةٍ وَشَرَاكَةٍ فَعَّالَةٍ مَعَ الْمُجْتَمَعِ الْمَحَلِّيِّ، لِبِنَاءِ جِيلٍ وَاثِقٍ، مُبَادِرٍ، مُؤَهَّلٍ لِمُوَاكَبَةِ تَحَدِّيَاتِ الْمُسْتَقْبَلِ.
       </p>
     </div>`},

  {iconKey:"info", title:"معلومات عن المدرسة", sub:"إحصائيات وبيانات",
   content:`<ul>
     <li><strong>اسم المدرسة:</strong> مدرسة عباد بن بشر للتعليم الأساسي (٥-٩).</li>
     <li><strong>المحافظة والولاية:</strong> محافظة الظاهرة — ولاية عبري.</li>
     <li><strong>عدد الطلبة:</strong> ٩٢٩ طالباً.</li>
     <li><strong>أعضاء الهيئتين الإدارية والتدريسية:</strong> ٦٨ عضواً.</li>
     <li><strong>المرحلة التعليمية:</strong> الصفوف (٥ – ٩).</li>
   </ul>`},

  {iconKey:"partnership", title:"المبادرات والشراكة المجتمعية", sub:"خدمة المجتمع والبيئة",
   content:`<ul>
     <li>مبادرات مجتمعية لتعزيز التحصيل الدراسي بالتعاون مع أولياء الأمور.</li>
     <li>برامج التشجير وحماية البيئة المدرسية والمحلية.</li>
     <li>مبادرة «تقنيّو المستقبل» لتدريب الطلاب على البرمجة والذكاء الاصطناعي.</li>
     <li>حملات العمل التطوعي وتوثيق صلة الطالب بمجتمعه في ولاية عبري.</li>
   </ul>`},

  {iconKey:"awards", title:"الإنجازات والجوائز", sub:"لوحة شرف المدرسة",
   content:`<ul>
     <li>حصد مراكز متقدمة في مسابقات التنمية المعرفية والابتكارات العلمية على مستوى محافظة الظاهرة.</li>
     <li>مراكز أولى في مسابقة حفظ وإتقان القرآن الكريم.</li>
     <li>درع التميز في الأنشطة الطلابية والمسابقات الكشفية والرياضية.</li>
   </ul>`},

  {iconKey:"exams", title:"جدول الاختبارات النهائية", sub:"مواعيد وضوابط الامتحانات",
   content:`
     <p>حرصاً على تنظيم العملية الاختبارية، نرفق لكم الإرشادات والجدول الزمني للاختبارات النهائية:</p>
     <div style="background:rgba(201,162,39,0.15); border:1px solid rgba(201,162,39,0.4); border-radius:12px; padding:14px; margin:14px 0;">
       <p style="margin:0; font-weight:700; color:var(--gold);">📌 تنبيهات هامة لأبنائنا الطلبة:</p>
       <ul style="margin-top:8px;">
         <li>الحضور إلى المدرسة قبل موعد الاختبار بنصف ساعة على الأقل.</li>
         <li>الالتزام الكامل بالزي العماني الرسمي والأدوات المدرسية المخصصة.</li>
         <li>يمنع تماماً إدخال الهواتف والساعات الذكية داخل قاعات الاختبار.</li>
       </ul>
     </div>
     <p>سيتم نشر تفاصيل جدول الاختبارات النهائية ومواعيد اللجان عبر البوابة التعليمية وقنوات التواصل الرسمية فور اعتمادها.</p>
   `},

  {iconKey:"schedule", title:"الجدول المدرسي", sub:"الحصص والجدول العام للمعلمين",
   content:`
     <div style="background:linear-gradient(135deg, rgba(11,107,58,0.35), rgba(0,224,198,0.15)); border:1px solid var(--neon); border-radius:14px; padding:16px; margin-bottom:18px; text-align:center;">
       <span style="font-size:2.2rem; display:block; margin-bottom:6px;">📑</span>
       <h4 style="color:var(--gold); margin-bottom:4px; font-size:1.15rem;">الجدول العام للمعلمين</h4>
       <p style="font-size:0.9rem; color:#d7e3ee; margin-bottom:12px;">يمكنكم الاطلاع والتحميل المباشر لملف الجدول العام بصيغة PDF:</p>
       <div style="display:flex; flex-wrap:wrap; justify-content:center; gap:10px;">
         <a href="https://moeom-my.sharepoint.com/:b:/r/personal/mohamed7732_moe_om/_layouts/15/onedrive.aspx?id=%2Fpersonal%2Fmohamed7732%5Fmoe%5Fom%2FDocuments%2F%D8%A7%D9%8A%D9%82%D9%88%D9%86%D8%A7%D8%AA%2F%D8%A7%D9%84%D8%AC%D8%AF%D9%88%D9%84%20%D8%A7%D9%84%D8%B9%D8%A7%D9%85%20%D9%84%D9%84%D9%85%D8%B9%D9%84%D9%85%D9%8A%D9%86%2Epdf&parent=%2Fpersonal%2Fmohamed7732%5Fmoe%5Fom%2FDocuments%2F%D8%A7%D9%8A%D9%82%D9%88%D9%86%D8%A7%D8%AA&share=cQq6IoB6LlyvTqWc0nYi3M1FEgUDvf9mi2%5FBQpGhaD%5F32mpFTQ" target="_blank" rel="noopener noreferrer" class="btn-link" style="margin:0;">
           👁️ فتح ومعاينة عبر OneDrive
         </a>
         <a href="https://moeom-my.sharepoint.com/personal/mohamed7732_moe_om/_layouts/15/download.aspx?share=cQq6IoB6LlyvTqWc0nYi3M1FEgUDvf9mi2%5FBQpGhaD%5F32mpFTQ" target="_blank" rel="noopener noreferrer" class="btn-link" style="margin:0; background:linear-gradient(135deg, var(--gold), #ffde7a); color:#0a2540;">
           📥 تحميل مباشر (PDF)
         </a>
       </div>
     </div>

     <hr style="border:none; border-top:1px solid rgba(0,224,198,0.25); margin:16px 0;">

     <h4 style="color:var(--gold); margin-bottom:10px;">⏰ توقيت الحصص واليوم الدراسي:</h4>
     <ul>
       <li><strong>طابور الصباح:</strong> ٧:١٥ – ٧:٣٥ صباحاً</li>
       <li><strong>الحصة الأولى:</strong> ٧:٣٥ – ٨:١٥ صباحاً</li>
       <li><strong>الحصة الثانية:</strong> ٨:٢٠ – ٩:٠٠ صباحاً</li>
       <li><strong>الحصة الثالثة:</strong> ٩:٠٥ – ٩:٤٥ صباحاً</li>
       <li><strong>استراحة الفسحة:</strong> ٩:٤٥ – ١٠:١٥ صباحاً</li>
       <li><strong>الحصة الرابعة:</strong> ١٠:١٥ – ١٠:٥٥ صباحاً</li>
       <li><strong>الحصة الخامسة:</strong> ١١:٠٠ – ١١:٤٠ صباحاً</li>
       <li><strong>الحصة السادسة وصلاة الظهر:</strong> ١١:٤٥ – ١٢:٣٥ ظهراً</li>
       <li><strong>الحصة السابعة:</strong> ١٢:٤٠ – ١:٢٠ ظهراً</li>
       <li><strong>الحصة الثامنة وانصراف الطلبة:</strong> ١:٢٥ – ٢:٠٥ ظهراً</li>
     </ul>`},

  {iconKey:"gallery", title:"معرض الصور", sub:"توثيق الفعاليات المدرسية",
   content:`<p>معرض تفاعلي يوثق أنشطة المدرسة، التكريمات، والمسابقات الطلابية في مدرسة عباد بن بشر.</p>`},

  {iconKey:"activities", title:"الأنشطة الطلابية", sub:"المواهب والابتكارات",
   content:`<ul>
     <li>نادي الروبوت والذكاء الاصطناعي.</li>
     <li>النشاط الرياضي (دوري الفصول وتنس الطاولة والشطرنج).</li>
     <li>الفرقة الموسيقية والفنون التشكيلية.</li>
     <li>جماعة الإذاعة المدرسية والصحافة.</li>
     <li>الفريق الكشفي والإرشادي.</li>
   </ul>`},

  {iconKey:"contact", title:"تواصل معنا", sub:"قنوات الاتصال المباشرة",
   content:`
     <p>يسعدنا دائماً تواصلكم والرد على جميع الاستفسارات:</p>
     <ul style="margin:14px 0;">
       <li><strong>الهاتف المباشر:</strong> ٢٢٤٩٥١٤٣</li>
       <li><strong>الموقع:</strong> سلطنة عُمان — محافظة الظاهرة — ولاية عبري</li>
       <li><strong>حساب منصة X (تويتر سابقاً):</strong> الحساب الرسمي لمدرسة عباد بن بشر</li>
     </ul>
     <div style="display:flex; flex-wrap:wrap; gap:10px; margin-top:14px;">
       <a href="tel:22495143" class="btn-link">📞 اتصال هاتفي الآن (٢٢٤٩٥١٤٣)</a>
       <a href="https://x.com" target="_blank" rel="noopener noreferrer" class="btn-link" style="background:linear-gradient(135deg, #1d9bf0, #0B6B3A); color:#fff;">
         🐦 زيارة حساب المدرسة على منصة X
       </a>
     </div>`},

  {iconKey:"indicators", title:"لوحة المؤشرات", sub:"التحصيل والتطوير الذاتي",
   content:`<p>نظام داخلي لمتابعة مؤشرات الأداء المدرسي والتحصيل الدراسي لطلبة الصفوف (٥-٩) لدعم مسيرة التميز والإتقان.</p>`},
];

const grid = document.getElementById('grid');
sections.forEach((s, i) => {
  const div = document.createElement('div');
  div.className = 'card';
  div.innerHTML = `
    <div class="icon-wrap">
      ${svgIcons[s.iconKey]}
    </div>
    <h3>${s.title}</h3>
    <small>${s.sub}</small>
  `;
  div.onclick = () => openModal(i);
  grid.appendChild(div);
});

function openModal(i){
  const iconMarkup = `<span style="display:inline-block;width:34px;height:34px;vertical-align:middle;margin-left:8px;">${svgIcons[sections[i].iconKey]}</span>`;
  document.getElementById('modalTitle').innerHTML = `${iconMarkup} ${sections[i].title}`;
  document.getElementById('modalBody').innerHTML = sections[i].content;
  document.getElementById('modal').classList.add('active');
  document.body.style.overflow = 'hidden';
}
function closeModal(){
  document.getElementById('modal').classList.remove('active');
  document.body.style.overflow = 'auto';
}
document.getElementById('modal').addEventListener('click', e => {
  if(e.target.id === 'modal') closeModal();
});
document.addEventListener('keydown', e => {
  if(e.key === 'Escape') closeModal();
});

function enterPlatform(){
  const w = document.getElementById('welcome');
  const m = document.getElementById('main');
  w.classList.add('hidden');
  m.classList.add('show');
  window.scrollTo({ top: 0, behavior: 'smooth' });
}

function updateClock(){
  const dEl = document.getElementById('todayDate');
  const tEl = document.getElementById('nowTime');
  if (!dEl || !tEl) return;

  const now = new Date();

  try {
    const dateOpts = { weekday: 'long', year: 'numeric', month: 'long', day: 'numeric', timeZone: 'Asia/Muscat' };
    const timeOpts = { hour: '2-digit', minute: '2-digit', second: '2-digit', hour12: true, timeZone: 'Asia/Muscat' };
    
    dEl.textContent = now.toLocaleDateString('ar-OM', dateOpts);
    tEl.textContent = now.toLocaleTimeString('ar-OM', timeOpts);
  } catch (err) {
    const days = ['الأحد', 'الإثنين', 'الثلاثاء', 'الأربعاء', 'الخميس', 'الجمعة', 'السبت'];
    const months = ['يناير', 'فبراير', 'مارس', 'أبريل', 'مايو', 'يونيو', 'يوليو', 'أغسطس', 'سبتمبر', 'أكتوبر', 'نوفمبر', 'ديسمبر'];
    
    const dayName = days[now.getDay()];
    const day = now.getDate();
    const monthName = months[now.getMonth()];
    const year = now.getFullYear();
    
    let hours = now.getHours();
    const minutes = String(now.getMinutes()).padStart(2, '0');
    const seconds = String(now.getSeconds()).padStart(2, '0');
    const ampm = hours >= 12 ? 'م' : 'ص';
    hours = hours % 12 || 12;

    dEl.textContent = `${dayName}، ${day} ${monthName} ${year}`;
    tEl.textContent = `${hours}:${minutes}:${seconds} ${ampm}`;
  }
}
updateClock();
setInterval(updateClock, 1000);
</script>
</body>
</html>
