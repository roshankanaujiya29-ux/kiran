<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>For Badi Waali Didi 👑</title>
<style>
  :root{ --bg:#2E0B14; --gold:#D4AF6A; --rose:#E8927C; --paper:#F7ECDD; }
  *{box-sizing:border-box; margin:0; padding:0; font-family:sans-serif;}
  body{
    background: radial-gradient(ellipse at 50% 0%, rgba(212,175,106,0.15), transparent), var(--bg);
    color:var(--paper); min-height:100vh; padding: 40px 20px;
  }
  .wrap{max-width:500px; margin:0 auto;}
  header{text-align:center; margin-bottom:40px;}
  .crest{width:80px; height:80px; margin:0 auto 15px;}
  h1{font-size:32px; font-weight:normal; margin-bottom:8px;}
  h1 em{color:var(--gold); font-style:normal;}
  .sub{opacity:0.7; font-size:14px; line-height:1.5;}
  
  .divider{display:flex; align-items:center; gap:10px; margin:40px 0 20px; font-size:12px; color:var(--gold); letter-spacing:2px; text-transform:uppercase;}
  .divider::after, .divider::before{content:''; flex:1; height:1px; background:linear-gradient(90deg, transparent, rgba(212,175,106,0.3), transparent);}
  
  .gallery{display:grid; grid-template-columns:1fr 1fr; gap:12px;}
  .frame{
    aspect-ratio:1; border-radius:12px; position:relative; overflow:hidden;
    background:rgba(212,175,106,0.05); border:1px dashed rgba(212,175,106,0.3);
  }
  .frame:nth-child(3){
    grid-column: span 2; 
    aspect-ratio: 16 / 9;
  }
  .frame span{
    position:absolute; inset:0; display:flex; align-items:center; justify-content:center;
    font-size:11px; color:var(--gold); opacity:0.6; text-align:center; padding:10px; z-index:1;
  }
  .frame img{width:100%; height:100%; object-fit:cover; display:block; position:absolute; z-index:2;}

  .quiz-card{background:rgba(212,175,106,0.05); border:1px solid rgba(212,175,106,0.15); border-radius:16px; padding:20px; margin-bottom:15px;}
  .qnum{font-size:11px; color:var(--gold); text-transform:uppercase; margin-bottom:8px; opacity:0.8;}
  .qtext{font-size:18px; margin-bottom:15px;}
  .opts{display:flex; flex-direction:column; gap:8px;}
  .opt{
    text-align:left; font-size:14px; background:rgba(247,236,221,0.04); 
    border:1px solid rgba(247,236,221,0.15); color:var(--paper); padding:12px; border-radius:10px; cursor:pointer;
  }
  .opt:hover, .opt.chosen{border-color:var(--gold); background:rgba(212,175,106,0.1);}
  .feedback{font-size:13px; margin-top:12px; color:var(--rose); display:none;}
  
  .next-btn{
    display:none; margin:15px auto 0; font-size:12px; color:#000;
    background:var(--gold); border:none; padding:8px 20px; border-radius:20px; cursor:pointer;
  }

  /* RESET PAGES TO DISPLAY NONE INITIALLY */
  #q2, #sibling-note, #final { display:none; text-align:center; padding:30px 10px; }
  
  .msg{font-size:20px; margin-bottom:20px; font-style:italic; line-height:1.6;}
  .heart-btn{background:transparent; border:1px solid var(--gold); color:var(--gold); padding:10px 24px; border-radius:20px; cursor:pointer;}
  .heart-btn:hover{background:var(--gold); color:#000;}
  .heart-response{margin-top:15px; font-size:14px; color:var(--rose); display:none;}
</style>
</head>
<body>

<div class="wrap">
  <header>
    <svg class="crest" viewBox="0 0 110 110" fill="none">
      <rect x="10" y="10" width="90" height="90" rx="4" fill="none" stroke="#D4AF6A" stroke-width="1" opacity="0.4"/>
      <path d="M55 20 L64 42 L88 42 L68 56 L76 78 L55 64 L34 78 L42 56 L22 42 L46 42 Z" fill="#D4AF6A" opacity="0.9"/>
      <circle cx="55" cy="55" r="7" fill="#2E0B14"/>
    </svg>
    <h1>Happy Rakhi, <em>Badi Waali Didi</em></h1>
    <p class="sub">Aap toh hamesha bhaari padi ho, chahe umar ho ya pyaar — aapke bhai ki taraf se!</p>
  </header>

  <div class="divider">Pics</div>
  <div class="gallery">
    <div class="frame"><img src="w.jpeg"><span>of you two 🤝</span></div>
    <div class="frame"><img src="v.jpeg"><span>from home 🏡</span></div>
    <div class="frame"><img src="u.jpeg"><span>favorite memory ✨</span></div>
  </div>

  <div class="divider">Quick Quiz</div>

  <!-- QUESTION 1 (Visible at start) -->
  <div class="quiz-card" id="q1" style="display: block;">
    <div class="qnum">Q1</div>
    <div class="qtext">Ghar mein sabse zyada order kaun chalati hai?</div>
    <div class="opts">
      <button class="opt" data-fb="Bilkul sahi. Badi Waali Didi ka hukum chalta hai! 👑">Meri Badi Waali Didi</button>
      <button class="opt" data-fb="Nice try, par asli boss toh koi aur hai 😄">Papa</button>
      <button class="opt" data-fb="Haha, sochne mein galti nahi hai, par nahi 😉">Main khud</button>
    </div>
    <div class="feedback"></div>
    <button class="next-btn">Next →</button>
  </div>

  <!-- QUESTION 2 (Hidden) -->
  <div class="quiz-card" id="q2">
    <div class="qnum">Q2</div>
    <div class="qtext">Chhote bhai ki sabse zyada daant kis baat par padi hai?</div>
    <div class="opts">
      <button class="opt" data-fb="Classic. Yeh toh har baar hota tha! 😂">Der raat tak jagna</button>
      <button class="opt" data-fb="Yeh bhi sach hai x) 😅">Kaam time pe na karna</button>
      <button class="opt" data-fb="In sab ka combo chal raha tha! 🤣">In sab ka combo</button>
    </div>
    <div class="feedback"></div>
    <button class="next-btn">See Message →</button>
  </div>

  <!-- EMOTIONAL CLOTHES MESSAGE SCREEN (Hidden) -->
  <div id="sibling-note">
    <div class="msg">"Wapis mere kapde chupalo please taaki mai kahi nhi jau bss apki kod me soya rahu 🥺🥺"</div>
    <button class="next-btn" id="to-final-btn" style="display: block; margin: 25px auto 0; padding: 10px 24px;">Tap here, one last thing... 👀</button>
  </div>

  <!-- FINAL THANK YOU SCREEN (Hidden) -->
  <div id="final">
    <div class="msg">"Thank you hamesha mera khayal rakhne ke liye aur har mushkil mein sahi rasta dikhane ke liye. Happy Rakhi Didi!"</div>
    <button class="heart-btn">Send Love ❤️</button>
    <div class="heart-response">Hugs incoming! 🤗✨</div>
  </div>
</div>

<script>
  // Setup Question 1 interactions
  const q1 = document.getElementById('q1');
  const q1Opts = q1.querySelectorAll('.opt');
  const q1Feedback = q1.querySelector('.feedback');
  const q1Next = q1.querySelector('.next-btn');

  q1Opts.forEach(opt => {
    opt.addEventListener('click', () => {
      q1Opts.forEach(o => o.style.borderColor = 'rgba(247,236,221,0.15)');
      opt.style.borderColor = '#D4AF6A';
      q1Feedback.textContent = opt.getAttribute('data-fb');
      q1Feedback.style.display = 'block';
      q1Next.style.display = 'block';
    });
  });

  q1Next.addEventListener('click', () => {
    q1.style.display = 'none';
    document.getElementById('q2').style.display = 'block';
  });

  // Setup Question 2 interactions
  const q2 = document.getElementById('q2');
  const q2Opts = q2.querySelectorAll('.opt');
  const q2Feedback = q2.querySelector('.feedback');
  const q2Next = q2.querySelector('.next-btn');

  q2Opts.forEach(opt => {
    opt.addEventListener('click', () => {
      q2Opts.forEach(o => o.style.borderColor = 'rgba(247,236,221,0.15)');
      opt.style.borderColor = '#D4AF6A';
      q2Feedback.textContent = opt.getAttribute('data-fb');
      q2Feedback.style.display = 'block';
      q2Next.style.display = 'block';
    });
  });

  // Triggering your clothes message screen directly on click
  q2Next.addEventListener('click', () => {
    q2.style.display = 'none';
    document.getElementById('sibling-note').style.display = 'block';
  });

  // Move from clothes message to the final window screen
  document.getElementById('to-final-btn').addEventListener('click', () => {
    document.getElementById('sibling-note').style.display = 'none';
    document.getElementById('final').style.display = 'block';
  });

  // Send Love interaction
  document.querySelector('.heart-btn').addEventListener('click', () => {
    document.querySelector('.heart-response').style.display = 'block';
  });
</script>

</body>
</html>
