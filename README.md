<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8"/>
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>Eunice Raia Dela Cruz</title>
<link href="https://fonts.googleapis.com/css2?family=Syne:wght@400;600;700;800&family=Inter:wght@300;400;500;600&family=Playfair+Display:ital,wght@1,400;1,700&display=swap" rel="stylesheet"/>
<style>
:root {
  --red: #8B0000;
  --red-light: #B22222;
  --red-dim: rgba(139,0,0,0.12);
  --ink: #0D0D0D;
  --ink2: #1a1a1a;
  --cream: #F8F4EF;
  --cream2: #F0EAE2;
  --offwhite: #FAF8F5;
  --muted: #7a7068;
  --border: rgba(13,13,13,0.1);
  --border2: rgba(13,13,13,0.06);
  --white: #ffffff;
}
*,*::before,*::after{margin:0;padding:0;box-sizing:border-box;}
html{scroll-behavior:smooth;font-size:16px;}
body{
  font-family:'Inter',sans-serif;
  background:var(--cream);
  color:var(--ink);
  overflow-x:hidden;
  cursor:none;
}

/* ── CUSTOM CURSOR ── */
.cursor{
  position:fixed;width:10px;height:10px;
  background:var(--red);border-radius:50%;
  pointer-events:none;z-index:99999;
  transition:transform 0.15s ease;
  transform:translate(-50%,-50%);
}
.cursor-ring{
  position:fixed;width:36px;height:36px;
  border:1.5px solid var(--red);border-radius:50%;
  pointer-events:none;z-index:99998;
  transition:transform 0.35s ease, width 0.25s ease, height 0.25s ease, opacity 0.25s;
  transform:translate(-50%,-50%);
  opacity:0.5;
}
.cursor-ring.expand{width:56px;height:56px;opacity:0.25;}

/* ── SMOOTH SCROLL PROGRESS ── */
#progress-bar{
  position:fixed;top:0;left:0;height:2px;
  background:var(--red);z-index:9999;
  width:0%;transition:width 0.1s linear;
}

/* ── NAV ── */
nav{
  position:fixed;top:0;left:0;right:0;z-index:1000;
  display:flex;align-items:center;justify-content:space-between;
  padding:1.2rem 3.5rem;
  background:rgba(248,244,239,0.88);
  backdrop-filter:blur(18px);
  -webkit-backdrop-filter:blur(18px);
  border-bottom:1px solid var(--border2);
  transition:padding 0.3s ease, box-shadow 0.3s ease;
}
nav.scrolled{padding:0.85rem 3.5rem;box-shadow:0 2px 30px rgba(0,0,0,0.06);}
.nav-logo{
  font-family:'Syne',sans-serif;font-weight:800;
  font-size:1.05rem;letter-spacing:-0.02em;
  color:var(--ink);text-decoration:none;
}
.nav-logo span{color:var(--red);}
.nav-links{display:flex;gap:2.5rem;list-style:none;align-items:center;}
.nav-links a{
  font-size:0.78rem;font-weight:500;color:var(--muted);
  text-decoration:none;letter-spacing:0.06em;text-transform:uppercase;
  transition:color 0.2s;position:relative;
}
.nav-links a::after{
  content:'';position:absolute;bottom:-3px;left:0;width:0;height:1px;
  background:var(--red);transition:width 0.25s ease;
}
.nav-links a:hover{color:var(--red);}
.nav-links a:hover::after{width:100%;}
.nav-hire{
  background:var(--ink)!important;color:var(--cream)!important;
  padding:0.55rem 1.35rem;border-radius:100px;
  font-size:0.78rem!important;letter-spacing:0.06em;
  transition:background 0.2s!important;
}
.nav-hire:hover{background:var(--red)!important;}
.nav-hire::after{display:none!important;}

/* ── SECTION WRAPPERS ── */
section{position:relative;overflow:hidden;}
.container{max-width:1200px;margin:0 auto;padding:0 3.5rem;}

/* ── SECTION LABELS ── */
.eyebrow{
  display:inline-flex;align-items:center;gap:0.6rem;
  font-size:0.72rem;font-weight:600;letter-spacing:0.14em;
  text-transform:uppercase;color:var(--red);margin-bottom:1rem;
}
.eyebrow::before{content:'';display:block;width:24px;height:1.5px;background:var(--red);}

/* ── HERO ── */
#hero{
  min-height:100vh;display:flex;flex-direction:column;
  justify-content:center;padding-top:80px;
  background:var(--ink);color:var(--cream);
  position:relative;
}
.hero-bg-grid{
  position:absolute;inset:0;
  background-image:linear-gradient(rgba(248,244,239,0.04) 1px,transparent 1px),
    linear-gradient(90deg,rgba(248,244,239,0.04) 1px,transparent 1px);
  background-size:60px 60px;
  pointer-events:none;
}
.hero-accent-line{
  position:absolute;top:0;left:0;bottom:0;width:3px;
  background:linear-gradient(to bottom,transparent,var(--red),transparent);
}
.hero-content{
  max-width:1200px;margin:0 auto;padding:0 3.5rem;
  display:grid;grid-template-columns:1fr;
  gap:2rem;
}
.hero-tag{
  display:inline-flex;align-items:center;gap:0.5rem;
  font-size:0.72rem;font-weight:600;letter-spacing:0.14em;text-transform:uppercase;
  color:var(--red);border:1px solid rgba(139,0,0,0.4);
  padding:0.4rem 1rem;border-radius:100px;width:fit-content;
  margin-bottom:1.5rem;
}
.hero-tag-dot{width:6px;height:6px;border-radius:50%;background:var(--red);animation:blink 1.5s ease infinite;}
@keyframes blink{0%,100%{opacity:1;}50%{opacity:0.3;}}

.hero-name{
  font-family:'Syne',sans-serif;font-weight:800;
  font-size:clamp(3.2rem,7vw,6.5rem);line-height:0.92;
  letter-spacing:-0.04em;color:var(--cream);
  margin-bottom:1.5rem;
}
.hero-name em{
  font-family:'Playfair Display',serif;
  font-style:italic;font-weight:400;
  color:var(--red);display:block;
}

/* ROLE SWITCHER */
.role-switcher-wrap{
  display:flex;align-items:center;gap:1rem;
  margin-bottom:2rem;
}
.role-prefix{
  font-size:0.8rem;font-weight:500;color:rgba(248,244,239,0.4);
  letter-spacing:0.06em;text-transform:uppercase;flex-shrink:0;
}
.role-switcher{
  font-family:'Syne',sans-serif;font-weight:700;
  font-size:clamp(1rem,2vw,1.3rem);letter-spacing:-0.01em;
  color:var(--red);
  min-height:1.6em;overflow:hidden;display:flex;align-items:center;
}
.role-text{
  display:block;
  animation:roleIn 0.4s cubic-bezier(0.22,1,0.36,1) forwards;
}
@keyframes roleIn{
  from{transform:translateY(100%);opacity:0;}
  to{transform:translateY(0);opacity:1;}
}
@keyframes roleOut{
  from{transform:translateY(0);opacity:1;}
  to{transform:translateY(-100%);opacity:0;}
}
.role-text.out{animation:roleOut 0.3s ease forwards;}

.hero-bio{
  font-size:1.05rem;line-height:1.75;
  color:rgba(248,244,239,0.65);font-weight:300;
  max-width:560px;margin-bottom:2.5rem;
}

.hero-stats{
  display:flex;gap:2.5rem;margin-bottom:2.5rem;flex-wrap:wrap;
}
.hero-stat{}
.hero-stat .num{
  font-family:'Syne',sans-serif;font-weight:800;
  font-size:1.8rem;color:var(--cream);letter-spacing:-0.03em;
}
.hero-stat .num span{color:var(--red);}
.hero-stat .label{
  font-size:0.72rem;color:rgba(248,244,239,0.4);
  letter-spacing:0.08em;text-transform:uppercase;margin-top:0.1rem;
}

.hero-btns{display:flex;gap:1rem;flex-wrap:wrap;}
.btn-red{
  background:var(--red);color:var(--cream);
  padding:0.9rem 2.2rem;border-radius:100px;
  font-family:'Inter',sans-serif;font-size:0.88rem;font-weight:600;
  text-decoration:none;letter-spacing:0.03em;
  transition:transform 0.2s,box-shadow 0.2s,background 0.2s;
  display:inline-flex;align-items:center;gap:0.5rem;
}
.btn-red:hover{transform:translateY(-3px);box-shadow:0 12px 32px rgba(139,0,0,0.35);background:var(--red-light);}
.btn-ghost{
  color:var(--cream);padding:0.9rem 2.2rem;border-radius:100px;
  border:1px solid rgba(248,244,239,0.2);
  font-family:'Inter',sans-serif;font-size:0.88rem;font-weight:500;
  text-decoration:none;letter-spacing:0.03em;
  transition:border-color 0.2s,color 0.2s,transform 0.2s;
  display:inline-flex;align-items:center;gap:0.5rem;
}
.btn-ghost:hover{border-color:var(--red);color:var(--red);transform:translateY(-3px);}

.hero-scroll-hint{
  position:absolute;bottom:2.5rem;left:50%;transform:translateX(-50%);
  display:flex;flex-direction:column;align-items:center;gap:0.5rem;
  font-size:0.68rem;letter-spacing:0.12em;text-transform:uppercase;
  color:rgba(248,244,239,0.3);
}
.scroll-line{width:1px;height:48px;background:linear-gradient(to bottom,rgba(139,0,0,0.8),transparent);animation:scrollPulse 2s ease infinite;}
@keyframes scrollPulse{0%,100%{transform:scaleY(1);}50%{transform:scaleY(0.5);}}

/* ── MARQUEE ── */
.marquee-wrap{
  background:var(--red);padding:0.85rem 0;overflow:hidden;
  border-top:1px solid rgba(139,0,0,0.3);
  border-bottom:1px solid rgba(139,0,0,0.3);
}
.marquee-track{
  display:flex;gap:0;width:max-content;
  animation:marquee 20s linear infinite;
}
@keyframes marquee{from{transform:translateX(0);}to{transform:translateX(-50%);}}
.marquee-item{
  font-family:'Syne',sans-serif;font-weight:700;
  font-size:0.78rem;letter-spacing:0.12em;text-transform:uppercase;
  color:var(--cream);padding:0 2rem;white-space:nowrap;
  display:flex;align-items:center;gap:2rem;
}
.marquee-item::after{content:'✦';font-size:0.6rem;opacity:0.6;}

/* ── ABOUT ── */
#about{padding:9rem 0;background:var(--cream);}
.about-grid{
  display:grid;grid-template-columns:1fr 1.1fr;
  gap:6rem;align-items:center;
}
.about-photo-col{position:relative;}
.about-photo-frame{
  position:relative;border-radius:4px;overflow:hidden;
  aspect-ratio:4/5;background:var(--ink);
}
.about-photo-frame img{width:100%;height:100%;object-fit:cover;display:block;filter:grayscale(15%);}
.about-photo-border{
  position:absolute;inset:0;border:2px solid var(--red);
  border-radius:4px;transform:translate(12px,12px);
  z-index:-1;
}
.about-photo-tag{
  position:absolute;bottom:1.5rem;left:-1.5rem;
  background:var(--red);color:var(--cream);
  font-family:'Syne',sans-serif;font-weight:700;
  font-size:0.72rem;letter-spacing:0.1em;text-transform:uppercase;
  padding:0.6rem 1.2rem;border-radius:4px;
  box-shadow:0 8px 24px rgba(0,0,0,0.2);
}
.about-text-col{}
.about-greeting{
  font-family:'Playfair Display',serif;
  font-style:italic;font-size:1.8rem;
  color:var(--red);margin-bottom:0.75rem;
  display:block;
}
.about-text-col h2{
  font-family:'Syne',sans-serif;font-weight:800;
  font-size:clamp(2rem,3.5vw,3rem);
  letter-spacing:-0.04em;line-height:1.05;
  margin-bottom:1.5rem;
}
.about-text-col h2 span{color:var(--red);}
.about-body{
  font-size:0.98rem;line-height:1.82;color:var(--muted);
  font-weight:400;margin-bottom:1.5rem;
}
.about-body strong{color:var(--ink);font-weight:600;}
.about-traits{
  display:grid;grid-template-columns:1fr 1fr;
  gap:0.85rem;margin-top:2rem;
}
.trait{
  background:var(--white);border:1px solid var(--border2);
  border-radius:8px;padding:1.1rem 1.2rem;
  transition:border-color 0.2s,transform 0.2s;
}
.trait:hover{border-color:var(--red);transform:translateY(-2px);}
.trait-title{
  font-family:'Syne',sans-serif;font-weight:700;
  font-size:0.82rem;color:var(--ink);margin-bottom:0.3rem;
}
.trait-desc{font-size:0.78rem;color:var(--muted);line-height:1.55;}

/* ── EDUCATION ── */
#education{padding:9rem 0;background:var(--ink);color:var(--cream);}
#education .eyebrow{color:var(--red);}
#education h2{
  font-family:'Syne',sans-serif;font-weight:800;
  font-size:clamp(2rem,3.5vw,3rem);letter-spacing:-0.04em;
  color:var(--cream);margin-bottom:3.5rem;
}
#education h2 span{color:var(--red);}
.edu-grid{display:grid;grid-template-columns:1fr 1fr;gap:1.5rem;}
.edu-card{
  background:rgba(248,244,239,0.04);
  border:1px solid rgba(248,244,239,0.08);
  border-radius:12px;padding:2.2rem;
  position:relative;overflow:hidden;
  transition:border-color 0.25s,transform 0.25s;
}
.edu-card::before{
  content:'';position:absolute;top:0;left:0;right:0;height:2px;
  background:var(--red);transform:scaleX(0);transform-origin:left;
  transition:transform 0.4s ease;
}
.edu-card:hover{border-color:rgba(139,0,0,0.4);transform:translateY(-4px);}
.edu-card:hover::before{transform:scaleX(1);}
.edu-level{
  font-size:0.68rem;font-weight:600;letter-spacing:0.14em;
  text-transform:uppercase;color:var(--red);margin-bottom:1rem;
  display:flex;align-items:center;gap:0.5rem;
}
.edu-level::before{content:'';width:20px;height:1px;background:var(--red);}
.edu-school{
  font-family:'Syne',sans-serif;font-weight:700;
  font-size:1.05rem;color:var(--cream);margin-bottom:0.4rem;line-height:1.3;
}
.edu-degree{
  font-size:0.85rem;color:rgba(248,244,239,0.55);
  line-height:1.5;margin-bottom:1.25rem;
}
.edu-year{
  font-size:0.72rem;color:var(--red);font-weight:600;
  letter-spacing:0.06em;margin-bottom:1rem;
}
.edu-badges{display:flex;flex-wrap:wrap;gap:0.4rem;}
.edu-badge{
  font-size:0.7rem;padding:0.3rem 0.75rem;
  background:rgba(139,0,0,0.18);color:rgba(248,244,239,0.8);
  border:1px solid rgba(139,0,0,0.25);
  border-radius:100px;font-weight:500;
}

/* ── SKILLS ── */
#skills{padding:9rem 0;background:var(--cream);}
#skills h2{
  font-family:'Syne',sans-serif;font-weight:800;
  font-size:clamp(2rem,3.5vw,3rem);letter-spacing:-0.04em;
  margin-bottom:3.5rem;
}
#skills h2 span{color:var(--red);}
.skills-grid{
  display:grid;grid-template-columns:repeat(3,1fr);gap:1.5rem;
}
.skill-card{
  background:var(--white);border:1px solid var(--border2);
  border-radius:12px;padding:2rem;
  position:relative;overflow:hidden;
  transition:transform 0.25s,box-shadow 0.25s;
}
.skill-card-top{
  position:absolute;top:0;left:0;right:0;height:2px;
  background:var(--red);transform:scaleX(0);transform-origin:left;
  transition:transform 0.4s ease;
}
.skill-card:hover{transform:translateY(-5px);box-shadow:0 20px 50px rgba(0,0,0,0.09);}
.skill-card:hover .skill-card-top{transform:scaleX(1);}
.skill-card-icon{
  width:38px;height:38px;border-radius:8px;
  background:var(--red-dim);display:flex;align-items:center;justify-content:center;
  margin-bottom:1.1rem;
}
.skill-card-icon svg{width:18px;height:18px;stroke:var(--red);fill:none;stroke-width:1.8;}
.skill-card-title{
  font-family:'Syne',sans-serif;font-weight:700;
  font-size:0.95rem;margin-bottom:1.25rem;
}
.skill-row{
  display:flex;align-items:center;justify-content:space-between;
  margin-bottom:0.85rem;
}
.skill-label{font-size:0.8rem;color:var(--muted);}
.skill-bar-wrap{width:90px;height:4px;background:#e8e3dc;border-radius:100px;overflow:hidden;}
.skill-bar{height:100%;border-radius:100px;background:var(--red);width:0;transition:width 1.2s cubic-bezier(0.22,1,0.36,1);}

/* ── EXPERIENCE ── */
#experience{padding:9rem 0;background:var(--offwhite);border-top:1px solid var(--border2);}
#experience h2{
  font-family:'Syne',sans-serif;font-weight:800;
  font-size:clamp(2rem,3.5vw,3rem);letter-spacing:-0.04em;
  margin-bottom:3.5rem;
}
#experience h2 span{color:var(--red);}
.exp-layout{display:grid;grid-template-columns:240px 1fr;gap:3.5rem;}
.exp-tabs{display:flex;flex-direction:column;gap:0.4rem;}
.exp-tab{
  padding:0.9rem 1.1rem;border-radius:8px;
  font-size:0.85rem;font-weight:500;color:var(--muted);
  border:1px solid transparent;background:none;
  text-align:left;cursor:pointer;
  transition:all 0.2s;display:flex;flex-direction:column;gap:0.15rem;
}
.exp-tab small{font-size:0.72rem;font-weight:400;color:rgba(122,112,104,0.7);}
.exp-tab:hover{background:var(--white);border-color:var(--border2);color:var(--ink);}
.exp-tab.active{background:var(--white);border-color:rgba(139,0,0,0.2);color:var(--red);}
.exp-tab.active small{color:rgba(139,0,0,0.5);}
.exp-panel{display:none;animation:panelIn 0.35s ease;}
.exp-panel.active{display:block;}
@keyframes panelIn{from{opacity:0;transform:translateY(12px);}to{opacity:1;transform:translateY(0);}}
.exp-title{
  font-family:'Syne',sans-serif;font-weight:800;
  font-size:1.7rem;letter-spacing:-0.03em;margin-bottom:0.3rem;
}
.exp-company{font-size:0.9rem;color:var(--red);font-weight:600;margin-bottom:0.25rem;}
.exp-meta{
  font-size:0.75rem;color:var(--muted);
  display:inline-flex;align-items:center;gap:0.5rem;
  margin-bottom:1.5rem;
}
.exp-meta::before{content:'';display:block;width:20px;height:1px;background:var(--muted);}
.exp-desc{font-size:0.92rem;line-height:1.8;color:var(--muted);margin-bottom:1.5rem;font-weight:400;}
.exp-tags{display:flex;flex-wrap:wrap;gap:0.45rem;}
.exp-tag{
  font-size:0.72rem;padding:0.3rem 0.8rem;
  background:var(--cream2);border:1px solid var(--border);
  border-radius:100px;color:var(--ink);font-weight:500;
}

/* ── PROJECTS ── */
#projects{padding:9rem 0;background:var(--cream);}
.projects-header{
  display:flex;justify-content:space-between;
  align-items:flex-end;margin-bottom:3.5rem;flex-wrap:wrap;gap:1rem;
}
.projects-header h2{
  font-family:'Syne',sans-serif;font-weight:800;
  font-size:clamp(2rem,3.5vw,3rem);letter-spacing:-0.04em;
}
.projects-header h2 span{color:var(--red);}
.projects-header p{max-width:320px;font-size:0.88rem;color:var(--muted);line-height:1.7;}
.projects-grid{
  display:grid;grid-template-columns:repeat(3,1fr);gap:1.25rem;
}
.proj-card{
  background:var(--white);border:1px solid var(--border2);
  border-radius:12px;overflow:hidden;
  transition:transform 0.3s,box-shadow 0.3s;
}
.proj-card:hover{transform:translateY(-6px);box-shadow:0 24px 60px rgba(0,0,0,0.1);}
.proj-card.span2{grid-column:span 2;display:grid;grid-template-columns:1.2fr 1fr;}
.proj-visual{
  height:200px;display:flex;align-items:center;
  justify-content:center;position:relative;overflow:hidden;
}
.proj-card.span2 .proj-visual{height:100%;min-height:240px;}
.proj-visual img{position:absolute;inset:0;width:100%;height:100%;object-fit:cover;}
.proj-visual-placeholder{
  position:relative;z-index:1;
  width:48px;height:48px;display:flex;align-items:center;justify-content:center;
}
.proj-visual-placeholder svg{width:32px;height:32px;stroke:rgba(248,244,239,0.5);fill:none;stroke-width:1.5;}
.pv-1{background:linear-gradient(135deg,#8B0000,#B22222);}
.pv-2{background:linear-gradient(135deg,#1a1a1a,#3a3a3a);}
.pv-3{background:linear-gradient(135deg,#4a1010,#8B0000);}
.pv-4{background:linear-gradient(135deg,#2a0000,#6b0000);}
.pv-5{background:linear-gradient(135deg,#0d0d0d,#8B0000);}
.pv-6{background:linear-gradient(135deg,#1a0000,#4a0000);}
.pv-7{background:linear-gradient(135deg,#8B0000,#1a1a1a);}
.pv-8{background:linear-gradient(135deg,#3a0000,#8B0000);}
.proj-body{padding:1.6rem;}
.proj-cat{
  font-size:0.68rem;font-weight:600;letter-spacing:0.1em;
  text-transform:uppercase;color:var(--muted);margin-bottom:0.5rem;
}
.proj-title{
  font-family:'Syne',sans-serif;font-weight:700;
  font-size:1.05rem;letter-spacing:-0.02em;margin-bottom:0.55rem;
}
.proj-desc{font-size:0.82rem;color:var(--muted);line-height:1.6;margin-bottom:1.1rem;}
.proj-link{
  font-size:0.78rem;font-weight:600;color:var(--red);
  text-decoration:none;display:inline-flex;align-items:center;gap:0.35rem;
  transition:gap 0.2s;
}
.proj-link:hover{gap:0.6rem;}
.proj-link-arrow{font-size:0.9rem;}

/* ── CONTACT ── */
#contact{padding:9rem 0;background:var(--ink);color:var(--cream);position:relative;overflow:hidden;}
.contact-bg-word{
  position:absolute;font-family:'Syne',sans-serif;font-weight:800;
  font-size:clamp(8rem,18vw,18rem);color:rgba(248,244,239,0.025);
  bottom:-2rem;left:50%;transform:translateX(-50%);
  white-space:nowrap;letter-spacing:-0.05em;pointer-events:none;
  user-select:none;
}
.contact-inner{position:relative;z-index:2;}
.contact-header{margin-bottom:4rem;}
#contact .eyebrow{color:var(--red);}
#contact h2{
  font-family:'Syne',sans-serif;font-weight:800;
  font-size:clamp(2.2rem,4vw,3.5rem);letter-spacing:-0.04em;
  color:var(--cream);
}
#contact h2 span{color:var(--red);}
.contact-grid{display:grid;grid-template-columns:1fr 1.3fr;gap:5rem;align-items:start;}
.contact-left h3{
  font-family:'Syne',sans-serif;font-weight:700;
  font-size:1.1rem;color:var(--cream);margin-bottom:0.75rem;
}
.contact-tagline{font-size:0.92rem;color:rgba(248,244,239,0.55);line-height:1.7;margin-bottom:2.5rem;}
.social-list{display:flex;flex-direction:column;gap:0.65rem;}
.social-item{
  display:flex;align-items:center;gap:1rem;
  padding:1rem 1.2rem;border-radius:10px;
  background:rgba(248,244,239,0.04);border:1px solid rgba(248,244,239,0.08);
  text-decoration:none;color:var(--cream);
  transition:all 0.22s;
}
.social-item:hover{background:rgba(139,0,0,0.15);border-color:rgba(139,0,0,0.3);transform:translateX(4px);}
.social-icon{
  width:34px;height:34px;border-radius:8px;
  background:rgba(248,244,239,0.08);
  display:flex;align-items:center;justify-content:center;flex-shrink:0;
}
.social-icon svg{width:16px;height:16px;stroke:var(--cream);fill:none;stroke-width:1.8;}
.social-label{font-size:0.88rem;font-weight:500;}
.social-handle{font-size:0.75rem;color:rgba(248,244,239,0.4);margin-left:auto;}
.contact-form{display:flex;flex-direction:column;gap:1rem;}
.form-row{display:grid;grid-template-columns:1fr 1fr;gap:1rem;}
.form-group{display:flex;flex-direction:column;gap:0.4rem;}
.form-group label{
  font-size:0.72rem;font-weight:600;
  color:rgba(248,244,239,0.45);letter-spacing:0.08em;text-transform:uppercase;
}
.form-group input,.form-group textarea,.form-group select{
  background:rgba(248,244,239,0.05);
  border:1px solid rgba(248,244,239,0.12);
  border-radius:8px;padding:0.85rem 1rem;
  color:var(--cream);font-family:'Inter',sans-serif;
  font-size:0.88rem;outline:none;
  transition:border-color 0.2s,background 0.2s;width:100%;
}
.form-group input::placeholder,.form-group textarea::placeholder{color:rgba(248,244,239,0.2);}
.form-group input:focus,.form-group textarea:focus{
  border-color:var(--red);background:rgba(139,0,0,0.06);
}
.form-group select option{background:#1a1a1a;}
.form-group textarea{min-height:120px;resize:vertical;}
.btn-submit{
  background:var(--red);color:var(--cream);border:none;
  padding:1rem 2rem;border-radius:100px;
  font-family:'Inter',sans-serif;font-size:0.92rem;font-weight:600;
  cursor:pointer;width:100%;
  transition:transform 0.2s,box-shadow 0.2s;
  display:flex;align-items:center;justify-content:center;gap:0.5rem;
}
.btn-submit:hover{transform:translateY(-2px);box-shadow:0 10px 30px rgba(139,0,0,0.4);}
#formSuccess{display:none;text-align:center;color:#4ade80;font-size:0.88rem;margin-top:0.5rem;font-weight:500;}
#formError{display:none;text-align:center;color:#f87171;font-size:0.82rem;margin-top:0.5rem;}

/* ── FOOTER ── */
footer{
  background:#080808;padding:1.75rem 3.5rem;
  display:flex;align-items:center;justify-content:space-between;
  border-top:1px solid rgba(248,244,239,0.05);
  font-size:0.75rem;color:rgba(248,244,239,0.25);
}
footer a{color:var(--red);text-decoration:none;}

/* ── REVEAL ANIMATIONS ── */
.reveal{opacity:0;transform:translateY(40px);transition:opacity 0.8s cubic-bezier(0.22,1,0.36,1),transform 0.8s cubic-bezier(0.22,1,0.36,1);}
.reveal.from-left{transform:translateX(-50px);}
.reveal.from-right{transform:translateX(50px);}
.reveal.visible{opacity:1;transform:translate(0);}
.reveal-delay-1{transition-delay:0.1s;}
.reveal-delay-2{transition-delay:0.2s;}
.reveal-delay-3{transition-delay:0.3s;}
.reveal-delay-4{transition-delay:0.4s;}

/* ── RESPONSIVE ── */
@media(max-width:900px){
  nav{padding:1rem 1.5rem;}
  .nav-links{display:none;}
  .container{padding:0 1.5rem;}
  .hero-content{padding:0 1.5rem;}
  section{padding:5rem 0;}
  #hero{padding-top:70px;}
  .about-grid,.exp-layout,.contact-grid{grid-template-columns:1fr;gap:3rem;}
  .edu-grid,.skills-grid,.projects-grid{grid-template-columns:1fr;}
  .proj-card.span2{grid-column:span 1;grid-template-columns:1fr;}
  .proj-card.span2 .proj-visual{height:200px;}
  .form-row{grid-template-columns:1fr;}
  footer{flex-direction:column;gap:0.5rem;text-align:center;padding:1.5rem;}
}
</style>
</head>
<body>

<div class="cursor" id="cursor"></div>
<div class="cursor-ring" id="cursorRing"></div>
<div id="progress-bar"></div>

<!-- NAV -->
<nav id="mainNav">
  <a href="#hero" class="nav-logo">Eunice<span>.</span></a>
  <ul class="nav-links">
    <li><a href="#about">About</a></li>
    <li><a href="#education">Education</a></li>
    <li><a href="#skills">Skills</a></li>
    <li><a href="#experience">Experience</a></li>
    <li><a href="#projects">Projects</a></li>
    <li><a href="#contact" class="nav-hire">Hire Me</a></li>
  </ul>
</nav>

<!-- HERO -->
<section id="hero">
  <div class="hero-bg-grid"></div>
  <div class="hero-accent-line"></div>
  <div class="hero-content">
    <div>
      <div class="hero-tag">
        <span class="hero-tag-dot"></span>
        Available for freelance work
      </div>
      <h1 class="hero-name">
        Eunice Raia<br/>
        <em>Dela Cruz</em>
      </h1>
      <div class="role-switcher-wrap">
        <span class="role-prefix">I am a</span>
        <div class="role-switcher" id="roleSwitcher">
          <span class="role-text" id="roleText">Graphic Designer</span>
        </div>
      </div>
      <p class="hero-bio">
        Creative mind, strategic heart. I blend design thinking with the precision of a VA to help your brand show up beautifully — and work smoothly behind the scenes.
      </p>
      <div class="hero-stats">
        <div class="hero-stat">
          <div class="num">3<span>+</span></div>
          <div class="label">Years Experience</div>
        </div>
        <div class="hero-stat">
          <div class="num">40<span>+</span></div>
          <div class="label">Projects Done</div>
        </div>
        <div class="hero-stat">
          <div class="num">100<span>%</span></div>
          <div class="label">Commitment</div>
        </div>
      </div>
      <div class="hero-btns">
        <a href="#contact" class="btn-red">
          Let's Work Together
          <svg width="14" height="14" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5"><path d="M5 12h14M12 5l7 7-7 7"/></svg>
        </a>
        <a href="#projects" class="btn-ghost">
          See My Work
          <svg width="14" height="14" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5"><path d="M5 12h14M12 5l7 7-7 7"/></svg>
        </a>
      </div>
    </div>
  </div>
  <div class="hero-scroll-hint">
    <div class="scroll-line"></div>
    <span>scroll</span>
  </div>
</section>

<!-- MARQUEE -->
<div class="marquee-wrap">
  <div class="marquee-track" id="marqueeTrack">
    <div class="marquee-item">Graphic Designer</div>
    <div class="marquee-item">Virtual Assistant</div>
    <div class="marquee-item">Video Editor</div>
    <div class="marquee-item">Director</div>
    <div class="marquee-item">Broadcaster</div>
    <div class="marquee-item">Student Journalist</div>
    <div class="marquee-item">Social Media Manager</div>
    <div class="marquee-item">Student Leader</div>
    <div class="marquee-item">Psychology Student</div>
    <div class="marquee-item">Graphic Designer</div>
    <div class="marquee-item">Virtual Assistant</div>
    <div class="marquee-item">Video Editor</div>
    <div class="marquee-item">Director</div>
    <div class="marquee-item">Broadcaster</div>
    <div class="marquee-item">Student Journalist</div>
    <div class="marquee-item">Social Media Manager</div>
    <div class="marquee-item">Student Leader</div>
    <div class="marquee-item">Psychology Student</div>
  </div>
</div>

<!-- ABOUT -->
<section id="about">
  <div class="container">
    <div class="about-grid">
      <div class="about-photo-col reveal from-left">
        <div class="about-photo-frame">
          <img src="data:image/jpeg;base64,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" alt="Eunice Raia Dela Cruz"/>
        </div>
        <div class="about-photo-border"></div>
        <div class="about-photo-tag">Open to Work &nbsp;&#9679;</div>
      </div>
      <div class="about-text-col reveal reveal-delay-2">
        <div class="eyebrow">About Me</div>
        <span class="about-greeting">Kumusta?</span>
        <h2>I make brands look good <span>&amp; run better.</span></h2>
        <p class="about-body">
          I'm a <strong>multi-hyphenate creative</strong> from the Philippines — graphic designer, video editor, director, virtual assistant, broadcaster, and proud psychology student. I believe good design communicates emotion, and smart admin keeps the momentum going.
        </p>
        <p class="about-body">
          When I'm not designing or directing, you'll find me leading student organizations, writing for campus journalism, behind a microphone, or deep in my Letterboxd reviews. Everything I do is done with <strong>intentionality and a bit of flair</strong>.
        </p>
        <div class="about-traits">
          <div class="trait">
            <div class="trait-title">Visual Storyteller</div>
            <div class="trait-desc">Brand identities, social graphics, layouts — designed with purpose and personality.</div>
          </div>
          <div class="trait">
            <div class="trait-title">Detail-Oriented VA</div>
            <div class="trait-desc">Email, scheduling, research — I keep your business running like clockwork.</div>
          </div>
          <div class="trait">
            <div class="trait-title">Director &amp; Editor</div>
            <div class="trait-desc">From concept to final cut — I direct, film, and edit compelling video content.</div>
          </div>
          <div class="trait">
            <div class="trait-title">Student Leader</div>
            <div class="trait-desc">Leading teams, driving campaigns, and championing causes that matter.</div>
          </div>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- EDUCATION -->
<section id="education">
  <div class="container">
    <div class="eyebrow reveal">Education</div>
    <h2 class="reveal reveal-delay-1">Where I <span>Learned</span></h2>
    <div class="edu-grid">
      <div class="edu-card reveal reveal-delay-1">
        <div class="edu-level">Tertiary</div>
        <div class="edu-school">City College of Angeles</div>
        <div class="edu-degree">Bachelor of Science in Psychology with Professional Education Courses</div>
        <div class="edu-year">'24 — Present &nbsp;·&nbsp; Sophomore</div>
        <div class="edu-badges">
          <span class="edu-badge">Dean's Lister</span>
          <span class="edu-badge">BS Psychology</span>
          <span class="edu-badge">Professional Ed</span>
        </div>
      </div>
      <div class="edu-card reveal reveal-delay-2">
        <div class="edu-level">Secondary</div>
        <div class="edu-school">AMA Computer College University</div>
        <div class="edu-degree">Humanities and Social Sciences</div>
        <div class="edu-year">'21 — '24 &nbsp;·&nbsp; Graduated</div>
        <div class="edu-badges">
          <span class="edu-badge">Top 3 Graduate</span>
          <span class="edu-badge">Emerging Student Leader</span>
          <span class="edu-badge">Best in Work Immersion</span>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- SKILLS -->
<section id="skills">
  <div class="container">
    <div class="eyebrow reveal">What I Do Best</div>
    <h2 class="reveal reveal-delay-1">My <span>Skill Set</span></h2>
    <div class="skills-grid">
      <!-- Graphic Design -->
      <div class="skill-card reveal reveal-delay-1">
        <div class="skill-card-top"></div>
        <div class="skill-card-icon">
          <svg viewBox="0 0 24 24"><path d="M12 2l9 4.5v7L12 18l-9-4.5v-7L12 2z"/><path d="M12 18v4M3 6.5l9 5 9-5"/></svg>
        </div>
        <div class="skill-card-title">Graphic Design</div>
        <div class="skill-row"><span class="skill-label">Canva</span><div class="skill-bar-wrap"><div class="skill-bar" data-w="95"></div></div></div>
        <div class="skill-row"><span class="skill-label">Adobe Photoshop</span><div class="skill-bar-wrap"><div class="skill-bar" data-w="85"></div></div></div>
        <div class="skill-row"><span class="skill-label">Adobe Illustrator</span><div class="skill-bar-wrap"><div class="skill-bar" data-w="80"></div></div></div>
        <div class="skill-row"><span class="skill-label">Brand Identity</span><div class="skill-bar-wrap"><div class="skill-bar" data-w="90"></div></div></div>
        <div class="skill-row"><span class="skill-label">Layout &amp; Typography</span><div class="skill-bar-wrap"><div class="skill-bar" data-w="88"></div></div></div>
      </div>
      <!-- Virtual Assistance -->
      <div class="skill-card reveal reveal-delay-2">
        <div class="skill-card-top"></div>
        <div class="skill-card-icon">
          <svg viewBox="0 0 24 24"><rect x="2" y="3" width="20" height="14" rx="2"/><path d="M8 21h8M12 17v4"/></svg>
        </div>
        <div class="skill-card-title">Virtual Assistance</div>
        <div class="skill-row"><span class="skill-label">Email Management</span><div class="skill-bar-wrap"><div class="skill-bar" data-w="92"></div></div></div>
        <div class="skill-row"><span class="skill-label">Calendar Scheduling</span><div class="skill-bar-wrap"><div class="skill-bar" data-w="90"></div></div></div>
        <div class="skill-row"><span class="skill-label">Research &amp; Reports</span><div class="skill-bar-wrap"><div class="skill-bar" data-w="87"></div></div></div>
        <div class="skill-row"><span class="skill-label">Data Entry</span><div class="skill-bar-wrap"><div class="skill-bar" data-w="93"></div></div></div>
        <div class="skill-row"><span class="skill-label">Google Workspace</span><div class="skill-bar-wrap"><div class="skill-bar" data-w="95"></div></div></div>
      </div>
      <!-- Social Media -->
      <div class="skill-card reveal reveal-delay-3">
        <div class="skill-card-top"></div>
        <div class="skill-card-icon">
          <svg viewBox="0 0 24 24"><circle cx="18" cy="5" r="3"/><circle cx="6" cy="12" r="3"/><circle cx="18" cy="19" r="3"/><path d="M8.59 13.51l6.83 3.98M15.41 6.51l-6.82 3.98"/></svg>
        </div>
        <div class="skill-card-title">Social Media</div>
        <div class="skill-row"><span class="skill-label">Content Strategy</span><div class="skill-bar-wrap"><div class="skill-bar" data-w="88"></div></div></div>
        <div class="skill-row"><span class="skill-label">Instagram &amp; TikTok</span><div class="skill-bar-wrap"><div class="skill-bar" data-w="91"></div></div></div>
        <div class="skill-row"><span class="skill-label">Copywriting</span><div class="skill-bar-wrap"><div class="skill-bar" data-w="85"></div></div></div>
        <div class="skill-row"><span class="skill-label">Community Mgmt</span><div class="skill-bar-wrap"><div class="skill-bar" data-w="82"></div></div></div>
        <div class="skill-row"><span class="skill-label">Analytics &amp; Insights</span><div class="skill-bar-wrap"><div class="skill-bar" data-w="80"></div></div></div>
      </div>
      <!-- Video & Media -->
      <div class="skill-card reveal reveal-delay-1">
        <div class="skill-card-top"></div>
        <div class="skill-card-icon">
          <svg viewBox="0 0 24 24"><polygon points="23 7 16 12 23 17 23 7"/><rect x="1" y="5" width="15" height="14" rx="2"/></svg>
        </div>
        <div class="skill-card-title">Video &amp; Media</div>
        <div class="skill-row"><span class="skill-label">Short-form Editing</span><div class="skill-bar-wrap"><div class="skill-bar" data-w="88"></div></div></div>
        <div class="skill-row"><span class="skill-label">Commercial Production</span><div class="skill-bar-wrap"><div class="skill-bar" data-w="82"></div></div></div>
        <div class="skill-row"><span class="skill-label">Broadcasting</span><div class="skill-bar-wrap"><div class="skill-bar" data-w="87"></div></div></div>
        <div class="skill-row"><span class="skill-label">Script Writing</span><div class="skill-bar-wrap"><div class="skill-bar" data-w="85"></div></div></div>
        <div class="skill-row"><span class="skill-label">Campaign Direction</span><div class="skill-bar-wrap"><div class="skill-bar" data-w="80"></div></div></div>
      </div>
      <!-- Tools -->
      <div class="skill-card reveal reveal-delay-2">
        <div class="skill-card-top"></div>
        <div class="skill-card-icon">
          <svg viewBox="0 0 24 24"><path d="M14.7 6.3a1 1 0 0 0 0 1.4l1.6 1.6a1 1 0 0 0 1.4 0l3.77-3.77a6 6 0 0 1-7.94 7.94l-6.91 6.91a2.12 2.12 0 0 1-3-3l6.91-6.91a6 6 0 0 1 7.94-7.94l-3.76 3.76z"/></svg>
        </div>
        <div class="skill-card-title">Tools &amp; Productivity</div>
        <div class="skill-row"><span class="skill-label">Google Workspace</span><div class="skill-bar-wrap"><div class="skill-bar" data-w="95"></div></div></div>
        <div class="skill-row"><span class="skill-label">Notion</span><div class="skill-bar-wrap"><div class="skill-bar" data-w="88"></div></div></div>
        <div class="skill-row"><span class="skill-label">Trello / Asana</span><div class="skill-bar-wrap"><div class="skill-bar" data-w="82"></div></div></div>
        <div class="skill-row"><span class="skill-label">Capcut / DaVinci</span><div class="skill-bar-wrap"><div class="skill-bar" data-w="85"></div></div></div>
        <div class="skill-row"><span class="skill-label">Microsoft Office</span><div class="skill-bar-wrap"><div class="skill-bar" data-w="90"></div></div></div>
      </div>
      <!-- AI & Coding -->
      <div class="skill-card reveal reveal-delay-3">
        <div class="skill-card-top"></div>
        <div class="skill-card-icon">
          <svg viewBox="0 0 24 24"><polyline points="16 18 22 12 16 6"/><polyline points="8 6 2 12 8 18"/></svg>
        </div>
        <div class="skill-card-title">AI &amp; Coding</div>
        <div class="skill-row"><span class="skill-label">ChatGPT / Claude</span><div class="skill-bar-wrap"><div class="skill-bar" data-w="92"></div></div></div>
        <div class="skill-row"><span class="skill-label">Midjourney / DALL·E</span><div class="skill-bar-wrap"><div class="skill-bar" data-w="85"></div></div></div>
        <div class="skill-row"><span class="skill-label">HTML &amp; CSS</span><div class="skill-bar-wrap"><div class="skill-bar" data-w="78"></div></div></div>
        <div class="skill-row"><span class="skill-label">WordPress / Wix</span><div class="skill-bar-wrap"><div class="skill-bar" data-w="80"></div></div></div>
        <div class="skill-row"><span class="skill-label">Prompt Engineering</span><div class="skill-bar-wrap"><div class="skill-bar" data-w="87"></div></div></div>
      </div>
    </div>
  </div>
</section>

<!-- EXPERIENCE -->
<section id="experience">
  <div class="container">
    <div class="eyebrow reveal">Career</div>
    <h2 class="reveal reveal-delay-1">My <span>Experience</span></h2>
    <div class="exp-layout">
      <div class="exp-tabs reveal from-left">
        <button class="exp-tab active" onclick="switchExp(0)">Graphic Designer Intern<small>Scholarship Guru</small></button>
        <button class="exp-tab" onclick="switchExp(1)">Virtual Assistant<small>4REs Vegetables &amp; Herbs Farm</small></button>
        <button class="exp-tab" onclick="switchExp(2)">Head of Digital Media<small>Student Journalism</small></button>
        <button class="exp-tab" onclick="switchExp(3)">Video Editor<small>Freelance &amp; Campus</small></button>
        <button class="exp-tab" onclick="switchExp(4)">Social Media Manager<small>Publications &amp; Orgs</small></button>
      </div>
      <div class="reveal reveal-delay-2">
        <div class="exp-panel active" id="exp-0">
          <div class="exp-title">Graphic Designer Intern</div>
          <div class="exp-company">Scholarship Guru</div>
          <div class="exp-meta">2024 — 2025 &nbsp;·&nbsp; Remote, Texas US</div>
          <p class="exp-desc">Designed visual assets, social media graphics, and marketing collaterals for an international scholarship platform. Collaborated with the team remotely to produce branded digital content that resonated with student audiences across the globe.</p>
          <div class="exp-tags">
            <span class="exp-tag">Brand Design</span><span class="exp-tag">Canva</span><span class="exp-tag">Social Graphics</span><span class="exp-tag">Remote Work</span>
          </div>
        </div>
        <div class="exp-panel" id="exp-1">
          <div class="exp-title">Virtual Assistant</div>
          <div class="exp-company">4REs Vegetables &amp; Herbs Farm</div>
          <div class="exp-meta">2023 — 2025 &nbsp;·&nbsp; Remote</div>
          <p class="exp-desc">Provided end-to-end VA support — calendar management, email triage, content creation, organized presentations, and admin coordination. Produced a commercial video for the business. Saved the client 15+ hours weekly through streamlined operations.</p>
          <div class="exp-tags">
            <span class="exp-tag">Email Management</span><span class="exp-tag">Scheduling</span><span class="exp-tag">Content Creation</span><span class="exp-tag">Video Production</span>
          </div>
        </div>
        <div class="exp-panel" id="exp-2">
          <div class="exp-title">Head of Digital Media &amp; Broadcasting</div>
          <div class="exp-company">Campus Journalism</div>
          <div class="exp-meta">2024 — Present</div>
          <p class="exp-desc">Leading digital media operations and broadcasting for the campus publication. Managing content strategy, on-air segments, news writing, and social media presence. Overseeing a team of student journalists and digital creatives.</p>
          <div class="exp-tags">
            <span class="exp-tag">Digital Media</span><span class="exp-tag">Broadcasting</span><span class="exp-tag">News Writing</span><span class="exp-tag">Team Leadership</span>
          </div>
        </div>
        <div class="exp-panel" id="exp-3">
          <div class="exp-title">Video Editor &amp; Content Creator</div>
          <div class="exp-company">Freelance &amp; Campus</div>
          <div class="exp-meta">2022 — Present &nbsp;·&nbsp; Remote</div>
          <p class="exp-desc">Filming, producing, and editing short-form videos, commercial content, and advocacy campaigns. Directed the VAWC Awareness Campaign video and 4REs Farm commercial. Delivers polished final cuts with storytelling at the core.</p>
          <div class="exp-tags">
            <span class="exp-tag">Video Editing</span><span class="exp-tag">Production</span><span class="exp-tag">Direction</span><span class="exp-tag">Capcut / DaVinci</span>
          </div>
        </div>
        <div class="exp-panel" id="exp-4">
          <div class="exp-title">Social Media Manager</div>
          <div class="exp-company">Publications &amp; Organizations</div>
          <div class="exp-meta">2022 — Present</div>
          <p class="exp-desc">Managing social media presence for campus organizations and freelance clients — creating content calendars, designing posts, writing captions, engaging communities, and analyzing performance to grow followings and boost engagement.</p>
          <div class="exp-tags">
            <span class="exp-tag">Content Planning</span><span class="exp-tag">Copywriting</span><span class="exp-tag">Instagram</span><span class="exp-tag">Analytics</span>
          </div>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- PROJECTS -->
<section id="projects">
  <div class="container">
    <div class="projects-header">
      <div>
        <div class="eyebrow reveal">Portfolio</div>
        <h2 class="reveal reveal-delay-1">Selected <span>Projects</span></h2>
      </div>
      <p class="reveal reveal-delay-2">A curated look at design, VA, and video work — more project images coming soon.</p>
    </div>
    <div class="projects-grid">
      <!-- Featured -->
      <div class="proj-card span2 reveal">
        <div class="proj-visual pv-1">
          <!-- ADD IMAGE: <img src="culeguran-metanoia.jpg" alt="Culeguran Metanoia"> -->
          <div class="proj-visual-placeholder">
            <svg viewBox="0 0 24 24"><path d="M21 16V8a2 2 0 0 0-1-1.73l-7-4a2 2 0 0 0-2 0l-7 4A2 2 0 0 0 3 8v8a2 2 0 0 0 1 1.73l7 4a2 2 0 0 0 2 0l7-4A2 2 0 0 0 21 16z"/></svg>
          </div>
        </div>
        <div class="proj-body">
          <div class="proj-cat">Branding &amp; Identity · Digital Media</div>
          <div class="proj-title">Culeguran: Metanoia — Brand Identity</div>
          <p class="proj-desc">As Head of Digital Media for Culeguran, I crafted a cohesive brand identity capturing the event's blend of art, love, and Kapampangan cultural pride. Overseeing visual direction, content production, digital campaigns, and audience engagement to bring the theme "Metanoia" to life.</p>
          <a href="mailto:euniceraia.delacruz@gmail.com" class="proj-link">Inquire for Details <span class="proj-link-arrow">→</span></a>
        </div>
      </div>
      <!-- Row 2 -->
      <div class="proj-card reveal reveal-delay-1">
        <div class="proj-visual pv-2">
          <!-- ADD IMAGE: <img src="culeguran-ephemera.jpg" alt="Culeguran Ephemera"> -->
          <div class="proj-visual-placeholder">
            <svg viewBox="0 0 24 24"><rect x="3" y="3" width="18" height="18" rx="2"/><path d="M3 9h18M9 21V9"/></svg>
          </div>
        </div>
        <div class="proj-body">
          <div class="proj-cat">Social Media Design</div>
          <div class="proj-title">Culeguran: Ephemera — Template Pack</div>
          <p class="proj-desc">30+ branded Canva templates for a publication's Facebook feed — consistent, creative, and on-brand for the Ephemera edition.</p>
          <a href="mailto:euniceraia.delacruz@gmail.com" class="proj-link">View Details <span class="proj-link-arrow">→</span></a>
        </div>
      </div>
      <div class="proj-card reveal reveal-delay-2">
        <div class="proj-visual pv-3">
          <!-- ADD IMAGE: <img src="va-support.jpg" alt="VA Support"> -->
          <div class="proj-visual-placeholder">
            <svg viewBox="0 0 24 24"><path d="M22 16.92v3a2 2 0 0 1-2.18 2 19.79 19.79 0 0 1-8.63-3.07A19.5 19.5 0 0 1 4.69 12 19.79 19.79 0 0 1 1.61 3.4 2 2 0 0 1 3.59 1h3a2 2 0 0 1 2 1.72c.127.96.361 1.903.7 2.81a2 2 0 0 1-.45 2.11L7.91 8.56a16 16 0 0 0 6 6l.92-.92a2 2 0 0 1 2.11-.45c.907.339 1.85.573 2.81.7A2 2 0 0 1 22 16.92z"/></svg>
          </div>
        </div>
        <div class="proj-body">
          <div class="proj-cat">Virtual Assistance</div>
          <div class="proj-title">Executive VA Support</div>
          <p class="proj-desc">Ongoing VA services — calendar management, email triage, content creation, organized presentations, saving the client 15+ hours weekly.</p>
          <a href="mailto:euniceraia.delacruz@gmail.com" class="proj-link">Work With Me <span class="proj-link-arrow">→</span></a>
        </div>
      </div>
      <div class="proj-card reveal reveal-delay-1">
        <div class="proj-visual pv-4">
          <!-- ADD IMAGE: <img src="scholarships.jpg" alt="Scholarships Campaign"> -->
          <div class="proj-visual-placeholder">
            <svg viewBox="0 0 24 24"><path d="M4 19.5A2.5 2.5 0 0 1 6.5 17H20"/><path d="M6.5 2H20v20H6.5A2.5 2.5 0 0 1 4 19.5v-15A2.5 2.5 0 0 1 6.5 2z"/></svg>
          </div>
        </div>
        <div class="proj-body">
          <div class="proj-cat">Advocacy · Design</div>
          <div class="proj-title">Scholarships Awareness Campaign</div>
          <p class="proj-desc">Social media templates and magazine mockup addressing lack of educational access for Filipino youth.</p>
          <a href="mailto:euniceraia.delacruz@gmail.com" class="proj-link">View Details <span class="proj-link-arrow">→</span></a>
        </div>
      </div>
      <div class="proj-card reveal reveal-delay-2">
        <div class="proj-visual pv-5">
          <!-- ADD IMAGE: <img src="tulong.jpg" alt="Tulong sa Gulong"> -->
          <div class="proj-visual-placeholder">
            <svg viewBox="0 0 24 24"><circle cx="12" cy="12" r="10"/><path d="M12 8v4l3 3"/></svg>
          </div>
        </div>
        <div class="proj-body">
          <div class="proj-cat">Fundraiser Branding</div>
          <div class="proj-title">Tulong sa Gulong Fundraiser</div>
          <p class="proj-desc">Social media template branding for the Tulong sa Gulong fundraiser — visually compelling assets to rally community support.</p>
          <a href="mailto:euniceraia.delacruz@gmail.com" class="proj-link">View Details <span class="proj-link-arrow">→</span></a>
        </div>
      </div>
      <div class="proj-card reveal reveal-delay-3">
        <div class="proj-visual pv-6">
          <!-- ADD IMAGE: <img src="4res-commercial.jpg" alt="4REs Commercial"> -->
          <div class="proj-visual-placeholder">
            <svg viewBox="0 0 24 24"><polygon points="23 7 16 12 23 17 23 7"/><rect x="1" y="5" width="15" height="14" rx="2"/></svg>
          </div>
        </div>
        <div class="proj-body">
          <div class="proj-cat">Commercial · Video Production</div>
          <div class="proj-title">4REs Vegetable &amp; Herbs Farm — Ad</div>
          <p class="proj-desc">Filmed, produced, and edited a full commercial video for 4REs Vegetable and Herbs Farm — from concept to final cut.</p>
          <a href="mailto:euniceraia.delacruz@gmail.com" class="proj-link">View Details <span class="proj-link-arrow">→</span></a>
        </div>
      </div>
      <div class="proj-card reveal reveal-delay-1">
        <div class="proj-visual pv-7">
          <!-- ADD IMAGE: <img src="id-lace.jpg" alt="Phoenix ID Lace"> -->
          <div class="proj-visual-placeholder">
            <svg viewBox="0 0 24 24"><rect x="5" y="2" width="14" height="20" rx="2"/><path d="M9 7h6M9 11h6M9 15h4"/></svg>
          </div>
        </div>
        <div class="proj-body">
          <div class="proj-cat">Merchandise · Print</div>
          <div class="proj-title">ID Lace — The Phoenix Publication</div>
          <p class="proj-desc">Custom ID lace design for The Phoenix Publication — a branded merchandise piece reflecting the publication's identity.</p>
          <a href="mailto:euniceraia.delacruz@gmail.com" class="proj-link">View Details <span class="proj-link-arrow">→</span></a>
        </div>
      </div>
      <div class="proj-card reveal reveal-delay-2">
        <div class="proj-visual pv-8">
          <!-- ADD IMAGE: <img src="vawc-video.jpg" alt="VAWC Campaign"> -->
          <div class="proj-visual-placeholder">
            <svg viewBox="0 0 24 24"><circle cx="12" cy="12" r="10"/><polygon points="10 8 16 12 10 16 10 8"/></svg>
          </div>
        </div>
        <div class="proj-body">
          <div class="proj-cat">Advocacy · Video Production</div>
          <div class="proj-title">VAWC Awareness Campaign Video</div>
          <p class="proj-desc">Directed, produced, and edited a Violence Against Women and Children advocacy campaign video — storytelling with purpose.</p>
          <a href="mailto:euniceraia.delacruz@gmail.com" class="proj-link">View Details <span class="proj-link-arrow">→</span></a>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- CONTACT -->
<section id="contact">
  <div class="contact-bg-word">HELLO</div>
  <div class="container contact-inner">
    <div class="contact-header reveal">
      <div class="eyebrow">Get In Touch</div>
      <h2>Let's create <span>something great</span> together.</h2>
    </div>
    <div class="contact-grid">
      <div class="reveal from-left">
        <h3>Say hello!</h3>
        <p class="contact-tagline">Whether you need a brand refresh, a reliable VA, or a creative partner — I'm here for it. Let's talk about your vision.</p>
        <div class="social-list">
          <a href="mailto:euniceraia.delacruz@gmail.com" class="social-item">
            <div class="social-icon"><svg viewBox="0 0 24 24"><path d="M4 4h16c1.1 0 2 .9 2 2v12c0 1.1-.9 2-2 2H4c-1.1 0-2-.9-2-2V6c0-1.1.9-2 2-2z"/><polyline points="22,6 12,13 2,6"/></svg></div>
            <span class="social-label">Email Me</span>
            <span class="social-handle">euniceraia.delacruz@gmail.com</span>
          </a>
          <a href="https://instagram.com/glitchingkittens" target="_blank" class="social-item">
            <div class="social-icon"><svg viewBox="0 0 24 24"><rect x="2" y="2" width="20" height="20" rx="5" ry="5"/><path d="M16 11.37A4 4 0 1 1 12.63 8 4 4 0 0 1 16 11.37z"/><line x1="17.5" y1="6.5" x2="17.51" y2="6.5"/></svg></div>
            <span class="social-label">Instagram</span>
            <span class="social-handle">@glitchingkittens</span>
          </a>
          <a href="https://letterboxd.com" target="_blank" class="social-item">
            <div class="social-icon"><svg viewBox="0 0 24 24"><polygon points="23 7 16 12 23 17 23 7"/><rect x="1" y="5" width="15" height="14" rx="2"/></svg></div>
            <span class="social-label">Letterboxd</span>
            <span class="social-handle">Film diary &amp; reviews</span>
          </a>
        </div>
      </div>
      <div class="reveal reveal-delay-2">
        <form class="contact-form" id="contactForm" action="https://formspree.io/f/YOUR_FORM_ID" method="POST">
          <div class="form-row">
            <div class="form-group"><label>Your Name</label><input type="text" name="name" placeholder="Jane Smith" required/></div>
            <div class="form-group"><label>Email Address</label><input type="email" name="email" placeholder="jane@email.com" required/></div>
          </div>
          <div class="form-group">
            <label>Service You Need</label>
            <select name="service">
              <option value="">Select a service…</option>
              <option>Graphic Design</option>
              <option>Virtual Assistance</option>
              <option>Social Media Management</option>
              <option>Branding Package</option>
              <option>Video Editing / Production</option>
              <option>Other</option>
            </select>
          </div>
          <div class="form-group"><label>Subject</label><input type="text" name="subject" placeholder="Project inquiry, collaboration…"/></div>
          <div class="form-group"><label>Your Message</label><textarea name="message" placeholder="Tell me about your project, timeline, and budget…" required></textarea></div>
          <button type="submit" class="btn-submit" id="submitBtn">Send Message
            <svg width="14" height="14" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5"><path d="M5 12h14M12 5l7 7-7 7"/></svg>
          </button>
          <p id="formSuccess">Message sent! I'll get back to you soon.</p>
          <p id="formError">Something went wrong. Email me directly at <a href="mailto:euniceraia.delacruz@gmail.com" style="color:var(--red)">euniceraia.delacruz@gmail.com</a></p>
        </form>
      </div>
    </div>
  </div>
</section>

<footer>
  <span>© 2025 Eunice Raia Dela Cruz. All rights reserved.</span>
  <span>Designed with intention — <a href="#hero">Back to top ↑</a></span>
</footer>

<script>
// ── CURSOR ──
const cursor = document.getElementById('cursor');
const ring = document.getElementById('cursorRing');
let mx=0,my=0,rx=0,ry=0;
document.addEventListener('mousemove',e=>{
  mx=e.clientX;my=e.clientY;
  cursor.style.left=mx+'px';cursor.style.top=my+'px';
});
function animRing(){
  rx+=(mx-rx)*0.12;ry+=(my-ry)*0.12;
  ring.style.left=rx+'px';ring.style.top=ry+'px';
  requestAnimationFrame(animRing);
}animRing();
document.querySelectorAll('a,button,.proj-card,.skill-card,.edu-card,.trait').forEach(el=>{
  el.addEventListener('mouseenter',()=>ring.classList.add('expand'));
  el.addEventListener('mouseleave',()=>ring.classList.remove('expand'));
});

// ── PROGRESS BAR ──
const bar=document.getElementById('progress-bar');
window.addEventListener('scroll',()=>{
  const pct=window.scrollY/(document.body.scrollHeight-window.innerHeight)*100;
  bar.style.width=pct+'%';
});

// ── NAV SCROLL ──
const nav=document.getElementById('mainNav');
window.addEventListener('scroll',()=>{
  nav.classList.toggle('scrolled',window.scrollY>60);
});

// ── ROLE SWITCHER ──
const roles=['Graphic Designer','Virtual Assistant','Video Editor','Director','Broadcaster','Student Journalist','Social Media Manager','Student Leader','Letterboxd Enthusiast'];
let ri=0;
const roleEl=document.getElementById('roleText');
function switchRole(){
  roleEl.classList.add('out');
  setTimeout(()=>{
    ri=(ri+1)%roles.length;
    roleEl.textContent=roles[ri];
    roleEl.classList.remove('out');
  },300);
}
setInterval(switchRole,1500);

// ── REVEAL ON SCROLL ──
const reveals=document.querySelectorAll('.reveal');
const obs=new IntersectionObserver(entries=>{
  entries.forEach(e=>{if(e.isIntersecting){e.target.classList.add('visible');}});
},{threshold:0.1});
reveals.forEach(r=>obs.observe(r));

// ── SKILL BARS ──
const skillObs=new IntersectionObserver(entries=>{
  entries.forEach(e=>{
    if(e.isIntersecting){
      e.target.querySelectorAll('.skill-bar').forEach(b=>{b.style.width=b.dataset.w+'%';});
    }
  });
},{threshold:0.3});
document.querySelectorAll('.skill-card').forEach(c=>skillObs.observe(c));

// ── EXPERIENCE TABS ──
function switchExp(i){
  document.querySelectorAll('.exp-tab').forEach((t,idx)=>t.classList.toggle('active',idx===i));
  document.querySelectorAll('.exp-panel').forEach((p,idx)=>p.classList.toggle('active',idx===i));
}

// ── FORMSPREE ──
const form=document.getElementById('contactForm');
if(form){
  form.addEventListener('submit',async e=>{
    e.preventDefault();
    const btn=document.getElementById('submitBtn');
    const ok=document.getElementById('formSuccess');
    const err=document.getElementById('formError');
    btn.textContent='Sending…';btn.disabled=true;
    try{
      const res=await fetch(form.action,{method:'POST',body:new FormData(form),headers:{'Accept':'application/json'}});
      if(res.ok){ok.style.display='block';err.style.display='none';form.reset();btn.textContent='Sent!';}
      else throw new Error();
    }catch{err.style.display='block';ok.style.display='none';btn.textContent='Send Message';btn.disabled=false;}
  });
}

// ── SMOOTH SECTION TRANSITIONS ──
document.querySelectorAll('a[href^="#"]').forEach(a=>{
  a.addEventListener('click',e=>{
    const target=document.querySelector(a.getAttribute('href'));
    if(target){e.preventDefault();target.scrollIntoView({behavior:'smooth',block:'start'});}
  });
});
</script>
</body>
</html>
