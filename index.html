import { useState, useEffect, useRef, useCallback } from "react";

/* ─── smooth scroll helper ────────────────────────────────── */
const scrollTo = (id) => {
  const el = document.getElementById(id);
  if (el) el.scrollIntoView({ behavior: "smooth", block: "start" });
};

/* ─── reliable image URLs (picsum CDN, always resolves) ────── */
const IMG = {
  hero:    "https://images.unsplash.com/photo-1517248135467-4c7edcad34c4?w=1920&q=80",
  story:   "https://images.unsplash.com/photo-1414235077428-338989a2e8c0?w=900&q=80",
  mBreak:  "https://images.unsplash.com/photo-1533089860892-a7c6f0a88666?w=1400&q=75",
  mLunch:  "https://images.unsplash.com/photo-1546069901-ba9599a7e63c?w=1400&q=75",
  mDinner: "https://images.unsplash.com/photo-1555396273-367ea4eb4db5?w=1400&q=75",
  mCoffee: "https://images.unsplash.com/photo-1509042239860-f550ce710b93?w=1400&q=75",
  g0: "https://images.unsplash.com/photo-1550966871-3ed3cba5831f?w=900&q=75",
  g1: "https://images.unsplash.com/photo-1484723091739-30a097e8f929?w=600&q=75",
  g2: "https://images.unsplash.com/photo-1559339352-11d035aa65de?w=600&q=75",
  g3: "https://images.unsplash.com/photo-1495474472287-4d71bcdd2085?w=800&q=75",
  g4: "https://images.unsplash.com/photo-1571997478779-2adcbbe9ab2f?w=800&q=75",
  g5: "https://images.unsplash.com/photo-1546833999-b9f581a1996d?w=600&q=75",
  g6: "https://images.unsplash.com/photo-1568901346375-23c9450c58cd?w=600&q=75",
  g7: "https://images.unsplash.com/photo-1572116469696-31de0f17cc34?w=900&q=75",
};
/* fallback gradient shown if CSP blocks external images */
const IMG_FALLBACK = "linear-gradient(135deg,#1a1208 0%,#0d0a06 100%)";

/* ─── inject fonts + global CSS once ─────────────────────── */
const CSS = `
@import url('https://fonts.googleapis.com/css2?family=Cormorant+Garamond:ital,wght@0,300;0,400;0,600;1,300;1,400&family=DM+Sans:opsz,wght@9..40,300;9..40,400;9..40,500&display=swap');

*,*::before,*::after{box-sizing:border-box;margin:0;padding:0}
:root{
  --gold:#C9A84C;--gold-lt:#E8C97A;--gold-dim:rgba(201,168,76,.12);
  --ch:#111;--ch2:#1c1c1c;--ch3:#2a2a2a;
  --cr:#F5F0E8;--mu:#88887f;
  --serif:'Cormorant Garamond',Georgia,serif;
  --sans:'DM Sans',system-ui,sans-serif;
  --ease:cubic-bezier(.22,1,.36,1);
}
html{scroll-behavior:smooth}
body{background:var(--ch);color:var(--cr);font-family:var(--sans);font-weight:300;line-height:1.7;overflow-x:hidden}
::-webkit-scrollbar{width:3px}
::-webkit-scrollbar-track{background:var(--ch)}
::-webkit-scrollbar-thumb{background:var(--gold);border-radius:2px}

/* reveal */
.rv{opacity:0;transform:translateY(28px);transition:opacity .8s var(--ease),transform .8s var(--ease)}
.rv.in{opacity:1;transform:none}
.rv.d1{transition-delay:.1s}.rv.d2{transition-delay:.22s}.rv.d3{transition-delay:.34s}

/* shimmer */
@keyframes shimmer{0%{background-position:-200% center}100%{background-position:200% center}}
.shimmer{
  background:linear-gradient(90deg,var(--gold) 25%,var(--gold-lt) 50%,var(--gold) 75%);
  background-size:200% auto;-webkit-background-clip:text;-webkit-text-fill-color:transparent;
  background-clip:text;animation:shimmer 4s linear infinite
}

/* hero anims */
@keyframes fup{from{opacity:0;transform:translateY(36px)}to{opacity:1;transform:none}}
.ht{animation:fup 1.2s var(--ease) .3s both}
.hs{animation:fup 1.2s var(--ease) .6s both}
.hc{animation:fup 1.2s var(--ease) .9s both}

/* ken burns */
@keyframes kb{0%{transform:scale(1)}100%{transform:scale(1.07) translate(-1%,-.5%)}}
.kb{animation:kb 20s ease-in-out infinite alternate}

/* pulse */
@keyframes pulse{0%,100%{box-shadow:0 0 0 0 rgba(201,168,76,.45)}50%{box-shadow:0 0 0 16px rgba(201,168,76,0)}}
.pulse{animation:pulse 2.6s ease infinite}

/* bob */
@keyframes bob{0%,100%{transform:translateX(-50%) translateY(0)}50%{transform:translateX(-50%) translateY(8px)}}
.bob{animation:bob 2.2s ease-in-out infinite}

/* nav underline */
.nl{position:relative}
.nl::after{content:'';position:absolute;bottom:-2px;left:0;width:0;height:1px;background:var(--gold);transition:width .3s}
.nl:hover::after{width:100%}

/* tab */
.tb{transition:all .3s;border-bottom:2px solid transparent}
.tb.on{border-bottom-color:var(--gold)!important;color:var(--gold)!important}

/* menu card */
.mc{transition:transform .3s,box-shadow .3s}
.mc:hover{transform:translateY(-4px);box-shadow:0 18px 40px rgba(0,0,0,.5)}

/* gallery */
.gi{overflow:hidden;position:relative;cursor:pointer}
.gi img{position:absolute;inset:0;width:100%;height:100%;object-fit:cover;
  transition:transform .6s var(--ease),filter .6s;filter:brightness(.8)}
.gi:hover img{transform:scale(1.07);filter:brightness(1)}
.glabel{position:absolute;bottom:0;left:0;right:0;
  padding:22px 14px 12px;background:linear-gradient(to top,rgba(0,0,0,.72),transparent)}
.glabel span{font-family:var(--sans);font-size:.65rem;letter-spacing:.14em;text-transform:uppercase;color:rgba(245,240,232,.6)}

/* input */
.inp{background:var(--ch3);border:1px solid rgba(201,168,76,.2);color:var(--cr);
  font-family:var(--sans);font-size:.87rem;padding:13px 16px;width:100%;
  outline:none;border-radius:2px;transition:border-color .3s}
.inp:focus{border-color:var(--gold)}
.inp::placeholder{color:var(--mu)}
.inp option{background:var(--ch3)}

/* ghost number */
.ghost{position:absolute;font-family:var(--serif);font-size:clamp(80px,13vw,170px);
  font-weight:300;color:rgba(201,168,76,.04);line-height:1;
  pointer-events:none;user-select:none;letter-spacing:-.02em}

/* mobile */
@keyframes sd{from{opacity:0;transform:translateY(-8px)}to{opacity:1;transform:none}}
.mob{animation:sd .25s ease}

@media(max-width:768px){
  .dnav{display:none!important}
  .hmb{display:flex!important}
  .gg{grid-template-columns:repeat(2,1fr)!important;grid-auto-rows:160px!important}
  .fg{grid-template-columns:1fr!important}
  .sw{display:none!important}
}
`;

/* ─── data ────────────────────────────────────────────────── */
const MENU_DATA = {
  Breakfast: {
    img: IMG.mBreak,
    items: [
      { name:"Saffron Ricotta Toast",    desc:"Whipped ricotta, saffron honey, candied walnuts on charcoal sourdough.", price:"AED 55", chef:true },
      { name:"Shakshuka Al Furjan",       desc:"Slow-simmered tomato ragout, spiced eggs, za'atar & dukkah crust.",     price:"AED 62" },
      { name:"Smashed Avocado Royale",    desc:"Hass avocado, poached egg, sumac, micro herbs, pickled red onion.",     price:"AED 68", chef:true },
      { name:"Aurum French Toast",        desc:"Brioche, orange blossom custard, edible gold dust, seasonal berries.",  price:"AED 72" },
      { name:"Labneh & Herb Plate",       desc:"House labneh, heirloom tomatoes, olives, fresh herbs, warm khubz.",    price:"AED 48" },
    ],
  },
  Lunch: {
    img: IMG.mLunch,
    items: [
      { name:"Wagyu Beef Sliders",        desc:"Wagyu patty, black truffle aioli, caramelised onion, brioche bun.",     price:"AED 128", chef:true },
      { name:"Seared Salmon Niçoise",     desc:"Pan-seared salmon, Kalamata olives, haricots verts, quail eggs.",       price:"AED 115" },
      { name:"Burrata & Heritage Tomato", desc:"Creamy burrata, heritage tomatoes, basil oil, aged balsamic.",          price:"AED 88", chef:true },
      { name:"Lamb Kofta Flatbread",      desc:"Spiced lamb kofta, harissa labneh, fresh herbs, sumac onions.",         price:"AED 105" },
      { name:"Mezze Selection",           desc:"Hummus, baba ghanoush, fattoush, warm pita — for the table.",           price:"AED 78" },
    ],
  },
  Dinner: {
    img: IMG.mDinner,
    items: [
      { name:"Black Truffle Risotto",     desc:"Carnaroli rice, aged parmesan, Périgord truffle, chive oil.",           price:"AED 185", chef:true },
      { name:"Charcoal Grilled Branzino", desc:"Mediterranean seabass, chermoula, preserved lemon, ras el hanout.",     price:"AED 210" },
      { name:"Slow Braised Short Rib",    desc:"48h wagyu short rib, bone marrow jus, roasted celeriac purée.",         price:"AED 265", chef:true },
      { name:"Stuffed Portobello",        desc:"Quinoa, roasted peppers, pine nuts, manchego, balsamic glaze.",         price:"AED 120" },
      { name:"Seared Duck Breast",        desc:"Duck magret, pomegranate molasses, spiced red cabbage, port jus.",      price:"AED 235" },
    ],
  },
  "Specialty Coffee": {
    img: IMG.mCoffee,
    items: [
      { name:"Aurum Signature Latte",     desc:"Single-origin espresso, house cardamom syrup, steamed oat milk.",       price:"AED 32", chef:true },
      { name:"Rose Oud Cold Brew",        desc:"18h cold-brew, rose water, hint of oud bitters, hand-cut ice.",         price:"AED 38", chef:true },
      { name:"Saffron Cortado",           desc:"Ristretto, saffron-infused whole milk, a whisper of raw honey.",        price:"AED 35" },
      { name:"Dallah Pour Over",          desc:"Single-origin Ethiopian, cardamom, served with a Medjool date.",        price:"AED 42" },
      { name:"Classic Espresso",          desc:"House blend — dark chocolate, caramel, subtle floral finish.",          price:"AED 22" },
    ],
  },
};

const GALLERY = [
  { label:"The Interior",         img:IMG.g0, col:2, row:2 },
  { label:"Saffron Toast",        img:IMG.g1, col:1, row:1 },
  { label:"Evening Ambiance",     img:IMG.g2, col:1, row:1 },
  { label:"Specialty Coffee Bar", img:IMG.g3, col:1, row:1 },
  { label:"Al Furjan Terrace",    img:IMG.g4, col:1, row:1 },
  { label:"Chef's Table",         img:IMG.g5, col:1, row:1 },
  { label:"Wagyu Sliders",        img:IMG.g6, col:1, row:1 },
  { label:"The Bar",              img:IMG.g7, col:2, row:2 },
];

const HOURS = [
  { day:"Monday – Friday", time:"7:00 AM – 11:00 PM" },
  { day:"Saturday",        time:"8:00 AM – 12:00 AM" },
  { day:"Sunday",          time:"8:00 AM – 11:00 PM" },
];

const NAV_LINKS = [
  { label:"Story",   id:"story"   },
  { label:"Menu",    id:"menu"    },
  { label:"Gallery", id:"gallery" },
  { label:"Reserve", id:"reserve" },
];

const FOOTER_LINKS = [
  { label:"Our Story",       id:"story"   },
  { label:"The Menu",        id:"menu"    },
  { label:"Gallery",         id:"gallery" },
  { label:"Reserve a Table", id:"reserve" },
];

/* ─── useReveal hook ─────────────────────────────────────── */
function useReveal() {
  const ref = useRef(null);
  useEffect(() => {
    const el = ref.current;
    if (!el) return;
    const io = new IntersectionObserver(
      ([e]) => { if (e.isIntersecting) { el.classList.add("in"); io.disconnect(); } },
      { threshold: 0.08 }
    );
    io.observe(el);
    return () => io.disconnect();
  }, []);
  return ref;
}

/* ─── GoldLine ───────────────────────────────────────────── */
function GoldLine() {
  return (
    <div style={{ display:"flex", alignItems:"center", gap:12, margin:"22px 0" }}>
      <div style={{ flex:1, height:1, background:"linear-gradient(90deg,transparent,var(--gold))" }} />
      <div style={{ width:5, height:5, background:"var(--gold)", transform:"rotate(45deg)", flexShrink:0 }} />
      <div style={{ flex:1, height:1, background:"linear-gradient(90deg,var(--gold),transparent)" }} />
    </div>
  );
}

/* ─── SecLabel ───────────────────────────────────────────── */
function SecLabel({ n, t }) {
  return (
    <div style={{ display:"flex", alignItems:"center", gap:10, marginBottom:14 }}>
      <span style={{ fontFamily:"var(--serif)", fontSize:".8rem", color:"var(--gold)", letterSpacing:".15em" }}>{String(n).padStart(2,"0")}</span>
      <div style={{ width:28, height:1, background:"var(--gold)" }} />
      <span style={{ fontFamily:"var(--sans)", fontSize:".68rem", letterSpacing:".22em", textTransform:"uppercase", color:"var(--mu)" }}>{t}</span>
    </div>
  );
}

/* ─── StarRating ─────────────────────────────────────────── */
function Stars({ full = 4, half = true, sz = 15 }) {
  return (
    <svg width={sz * (full + (half ? 1 : 0)) + (full + (half?1:0) - 1) * 3} height={sz} viewBox={`0 0 ${(sz+3)*(full+(half?1:0))-3} ${sz}`}>
      <defs>
        <linearGradient id="hg" x1="0" x2="1" y1="0" y2="0">
          <stop offset="55%" stopColor="var(--gold)" />
          <stop offset="55%" stopColor="rgba(201,168,76,0.18)" />
        </linearGradient>
      </defs>
      {Array.from({ length: full }).map((_, i) => (
        <polygon key={i}
          transform={`translate(${i*(sz+3)},0) scale(${sz/24})`}
          points="12,2 15.09,8.26 22,9.27 17,14.14 18.18,21.02 12,17.77 5.82,21.02 7,14.14 2,9.27 8.91,8.26"
          fill="var(--gold)" />
      ))}
      {half && (
        <polygon
          transform={`translate(${full*(sz+3)},0) scale(${sz/24})`}
          points="12,2 15.09,8.26 22,9.27 17,14.14 18.18,21.02 12,17.77 5.82,21.02 7,14.14 2,9.27 8.91,8.26"
          fill="url(#hg)" stroke="rgba(201,168,76,.4)" strokeWidth=".5" />
      )}
    </svg>
  );
}

/* ─── Img with gradient fallback ────────────────────────── */
function FImg({ src, alt, className, style: s = {} }) {
  const [ok, setOk] = useState(true);
  return ok
    ? <img src={src} alt={alt} className={className} style={s} onError={() => setOk(false)} />
    : <div className={className} style={{ ...s, background: IMG_FALLBACK }} />;
}

/* ─── NAV ────────────────────────────────────────────────── */
function Nav({ open, setOpen }) {
  const [scrolled, setScrolled] = useState(false);
  useEffect(() => {
    const fn = () => setScrolled(window.scrollY > 55);
    window.addEventListener("scroll", fn, { passive: true });
    return () => window.removeEventListener("scroll", fn);
  }, []);

  const go = (id) => { scrollTo(id); setOpen(false); };

  return (
    <nav style={{
      position:"fixed", top:0, left:0, right:0, zIndex:1000,
      padding:"0 clamp(18px,5vw,64px)",
      background: scrolled ? "rgba(17,17,17,.94)" : "transparent",
      backdropFilter: scrolled ? "blur(16px)" : "none",
      borderBottom: scrolled ? "1px solid rgba(201,168,76,.13)" : "1px solid transparent",
      transition:"background .4s, border-color .4s",
    }}>
      <div style={{ display:"flex", alignItems:"center", justifyContent:"space-between", height:70 }}>
        {/* logo */}
        <button onClick={() => scrollTo("hero")} style={{ background:"none", border:"none", cursor:"pointer", textAlign:"left", padding:0 }}>
          <div style={{ fontFamily:"var(--serif)", fontSize:"1.65rem", fontWeight:300, letterSpacing:".14em", color:"var(--gold)", lineHeight:1 }}>AURUM</div>
          <div style={{ fontSize:".5rem", letterSpacing:".38em", color:"var(--mu)", textTransform:"uppercase", marginTop:2 }}>Restaurant & Cafe</div>
        </button>

        {/* desktop links */}
        <div className="dnav" style={{ display:"flex", gap:32, alignItems:"center" }}>
          {NAV_LINKS.map(({ label, id }) => (
            <button key={id} onClick={() => go(id)} className="nl"
              style={{ background:"none", border:"none", cursor:"pointer", fontFamily:"var(--sans)", fontSize:".74rem", letterSpacing:".16em", textTransform:"uppercase", color:"var(--cr)", fontWeight:400, padding:0 }}>
              {label}
            </button>
          ))}
          <button onClick={() => go("reserve")}
            style={{
              fontFamily:"var(--sans)", fontSize:".72rem", fontWeight:500, letterSpacing:".16em", textTransform:"uppercase",
              background:"var(--gold)", color:"var(--ch)", padding:"9px 22px", border:"none", cursor:"pointer",
              borderRadius:2, transition:"background .25s",
            }}
            onMouseEnter={e => e.currentTarget.style.background = "var(--gold-lt)"}
            onMouseLeave={e => e.currentTarget.style.background = "var(--gold)"}
          >Book Now</button>
        </div>

        {/* hamburger */}
        <button className="hmb" onClick={() => setOpen(!open)}
          style={{ display:"none", background:"none", border:"none", cursor:"pointer", color:"var(--cr)", padding:4, alignItems:"center" }}>
          {open
            ? <svg width={22} height={22} viewBox="0 0 24 24" fill="none" stroke="currentColor" strokeWidth={2}><line x1="18" y1="6" x2="6" y2="18"/><line x1="6" y1="6" x2="18" y2="18"/></svg>
            : <svg width={22} height={22} viewBox="0 0 24 24" fill="none" stroke="currentColor" strokeWidth={2}><line x1="3" y1="6" x2="21" y2="6"/><line x1="3" y1="12" x2="21" y2="12"/><line x1="3" y1="18" x2="21" y2="18"/></svg>
          }
        </button>
      </div>

      {/* mobile menu */}
      {open && (
        <div className="mob" style={{ background:"var(--ch2)", borderTop:"1px solid rgba(201,168,76,.1)", paddingBottom:12 }}>
          {NAV_LINKS.map(({ label, id }) => (
            <button key={id} onClick={() => go(id)}
              style={{ display:"block", width:"100%", textAlign:"left", padding:"13px 0", background:"none", border:"none", borderBottom:"1px solid rgba(255,255,255,.04)", cursor:"pointer", fontFamily:"var(--sans)", fontSize:".82rem", letterSpacing:".15em", textTransform:"uppercase", color:"var(--cr)", fontWeight:300 }}>
              {label}
            </button>
          ))}
          <button onClick={() => go("reserve")}
            style={{ marginTop:10, width:"100%", background:"var(--gold)", color:"var(--ch)", border:"none", cursor:"pointer", padding:"13px 0", fontFamily:"var(--sans)", fontSize:".74rem", letterSpacing:".16em", textTransform:"uppercase", fontWeight:500, borderRadius:2 }}>
            Book a Table
          </button>
        </div>
      )}
    </nav>
  );
}

/* ─── HERO ───────────────────────────────────────────────── */
function Hero() {
  return (
    <section id="hero" style={{ position:"relative", height:"100dvh", minHeight:600, overflow:"hidden", display:"flex", alignItems:"center", justifyContent:"center" }}>

      {/* bg photo */}
      <FImg src={IMG.hero} alt="Aurum interior" className="kb"
        style={{ position:"absolute", inset:0, width:"100%", height:"100%", objectFit:"cover", objectPosition:"center" }} />

      {/* overlays */}
      <div style={{ position:"absolute", inset:0, background:"linear-gradient(to bottom,rgba(0,0,0,.3),rgba(0,0,0,.1) 40%,rgba(0,0,0,.55))" }} />
      <div style={{ position:"absolute", inset:0, background:"radial-gradient(ellipse at center,transparent 28%,rgba(0,0,0,.5) 100%)" }} />
      <div style={{ position:"absolute", inset:0, background:"rgba(20,12,0,.22)" }} />
      <div style={{ position:"absolute", bottom:0, left:0, right:0, height:"38%", background:"linear-gradient(to top,#111,transparent)" }} />

      {/* content */}
      <div style={{ position:"relative", zIndex:1, textAlign:"center", padding:"0 clamp(20px,6vw,80px)", maxWidth:820, width:"100%" }}>
        <div className="hs" style={{ fontFamily:"var(--sans)", fontSize:".7rem", letterSpacing:".44em", textTransform:"uppercase", color:"var(--gold)", marginBottom:20, display:"flex", alignItems:"center", justifyContent:"center", gap:14 }}>
          <div style={{ width:26, height:1, background:"var(--gold)" }} />
          Al Furjan, Dubai
          <div style={{ width:26, height:1, background:"var(--gold)" }} />
        </div>

        <h1 className="ht" style={{ fontFamily:"var(--serif)", fontWeight:300, fontSize:"clamp(54px,11vw,116px)", lineHeight:1.02, letterSpacing:"-.015em", marginBottom:10 }}>
          <span className="shimmer">Aurum</span><br />
          <span style={{ fontStyle:"italic", color:"var(--cr)", fontSize:".68em", opacity:.88 }}>Restaurant & Cafe</span>
        </h1>

        <p className="hs" style={{ fontFamily:"var(--serif)", fontStyle:"italic", fontSize:"clamp(.95rem,2vw,1.2rem)", color:"rgba(245,240,232,.62)", lineHeight:1.85, maxWidth:460, margin:"0 auto 46px" }}>
          Where community warmth meets refined dining — crafted with golden intention.
        </p>

        <div className="hc" style={{ display:"flex", gap:13, justifyContent:"center", flexWrap:"wrap" }}>
          <button className="pulse" onClick={() => scrollTo("reserve")}
            style={{ display:"inline-flex", alignItems:"center", gap:9, background:"var(--gold)", color:"var(--ch)", fontFamily:"var(--sans)", fontSize:".74rem", fontWeight:500, letterSpacing:".16em", textTransform:"uppercase", padding:"15px 34px", border:"none", cursor:"pointer", borderRadius:2, transition:"background .25s" }}
            onMouseEnter={e => e.currentTarget.style.background = "var(--gold-lt)"}
            onMouseLeave={e => e.currentTarget.style.background = "var(--gold)"}
          >
            Book a Table
            <svg width={14} height={14} viewBox="0 0 24 24" fill="none" stroke="currentColor" strokeWidth={2}><line x1="5" y1="12" x2="19" y2="12"/><polyline points="12 5 19 12 12 19"/></svg>
          </button>

          <button onClick={() => scrollTo("menu")}
            style={{ display:"inline-flex", alignItems:"center", gap:9, background:"transparent", color:"var(--gold)", fontFamily:"var(--sans)", fontSize:".74rem", fontWeight:400, letterSpacing:".16em", textTransform:"uppercase", padding:"15px 34px", border:"1px solid rgba(201,168,76,.4)", cursor:"pointer", borderRadius:2, transition:"background .25s" }}
            onMouseEnter={e => e.currentTarget.style.background = "rgba(201,168,76,.08)"}
            onMouseLeave={e => e.currentTarget.style.background = "transparent"}
          >Explore Menu</button>
        </div>
      </div>

      {/* scroll hint */}
      <div className="bob" style={{ position:"absolute", bottom:32, left:"50%", display:"flex", flexDirection:"column", alignItems:"center", gap:5, color:"rgba(201,168,76,.48)" }}>
        <span style={{ fontFamily:"var(--sans)", fontSize:".56rem", letterSpacing:".3em", textTransform:"uppercase" }}>Scroll</span>
        <svg width={14} height={14} viewBox="0 0 24 24" fill="none" stroke="currentColor" strokeWidth={2}><polyline points="6 9 12 15 18 9"/></svg>
      </div>
    </section>
  );
}

/* ─── STORY ──────────────────────────────────────────────── */
function Story() {
  const r1 = useReveal(), r2 = useReveal(), r3 = useReveal(), r4 = useReveal();

  return (
    <section id="story" style={{ background:"var(--ch)", padding:"clamp(80px,12vw,144px) clamp(18px,5vw,64px)", position:"relative", overflow:"hidden" }}>
      <span className="ghost" style={{ top:-10, right:-6 }}>01</span>

      <div style={{ maxWidth:1200, margin:"0 auto", display:"grid", gridTemplateColumns:"1fr 1fr", gap:"clamp(36px,6vw,88px)", alignItems:"center" }}>
        <div>
          <div ref={r1} className="rv">
            <SecLabel n={1} t="Our Story" />
            <h2 style={{ fontFamily:"var(--serif)", fontSize:"clamp(36px,6vw,70px)", fontWeight:300, lineHeight:1.06, letterSpacing:"-.015em" }}>
              The Meaning of<br /><em className="shimmer">Aurum</em>
            </h2>
          </div>

          <div ref={r2} className="rv d1">
            <GoldLine />
            <p style={{ fontFamily:"var(--serif)", fontSize:"1.18rem", lineHeight:1.88, color:"rgba(245,240,232,.78)", marginBottom:20, fontWeight:300 }}>
              <em>Aurum</em> — Latin for gold — is our promise. Not in palette alone, but in every grain of coffee, every fold of pastry, and every moment you spend with us in Al Furjan.
            </p>
            <p style={{ fontFamily:"var(--sans)", fontSize:".87rem", lineHeight:1.9, color:"var(--mu)", fontWeight:300, marginBottom:34 }}>
              Born from a desire to create a space where the neighbourhood comes together — where the morning espresso is as considered as the evening short rib — Aurum is equal parts community cafe and refined dining destination.
            </p>
            <button onClick={() => scrollTo("reserve")}
              style={{ display:"inline-flex", alignItems:"center", gap:9, background:"transparent", color:"var(--gold)", fontFamily:"var(--sans)", fontSize:".72rem", fontWeight:500, letterSpacing:".16em", textTransform:"uppercase", padding:"12px 26px", border:"1px solid rgba(201,168,76,.38)", cursor:"pointer", borderRadius:2, transition:"all .25s" }}
              onMouseEnter={e => { e.currentTarget.style.background="var(--gold)"; e.currentTarget.style.color="var(--ch)"; }}
              onMouseLeave={e => { e.currentTarget.style.background="transparent"; e.currentTarget.style.color="var(--gold)"; }}
            >
              Reserve a Table
              <svg width={13} height={13} viewBox="0 0 24 24" fill="none" stroke="currentColor" strokeWidth={2}><line x1="5" y1="12" x2="19" y2="12"/><polyline points="12 5 19 12 12 19"/></svg>
            </button>
          </div>

          <div ref={r3} className="rv d2" style={{ display:"grid", gridTemplateColumns:"1fr 1fr", gap:2, marginTop:38 }}>
            {[
              { num:"3+",  label:"Years in Al Furjan", star:false },
              { num:"40+", label:"Menu Creations",      star:false },
              { num:"18",  label:"Specialty Coffees",   star:false },
              { num:null,  label:"Community Rated",     star:true  },
            ].map(({ num, label, star }) => (
              <div key={label} style={{ background:"var(--ch2)", padding:"24px 18px", borderBottom:"1px solid rgba(201,168,76,.06)" }}>
                {star
                  ? <div style={{ marginBottom:6 }}><Stars full={4} half={true} sz={16} /></div>
                  : <div style={{ fontFamily:"var(--serif)", fontSize:"2.4rem", color:"var(--gold)", fontWeight:300, lineHeight:1, marginBottom:6 }}>{num}</div>
                }
                <div style={{ fontFamily:"var(--sans)", fontSize:".66rem", letterSpacing:".14em", textTransform:"uppercase", color:"var(--mu)" }}>{label}</div>
              </div>
            ))}
          </div>
        </div>

        {/* photo */}
        <div ref={r4} className="rv d3 sw" style={{ position:"relative", height:"clamp(480px,68vh,740px)" }}>
          <FImg src={IMG.story} alt="Fine dining at Aurum"
            style={{ width:"100%", height:"100%", objectFit:"cover", objectPosition:"center", borderRadius:2 }} />
          <div style={{ position:"absolute", bottom:-14, left:-14, width:"55%", height:3, background:"var(--gold)" }} />
          <div style={{ position:"absolute", bottom:-14, left:-14, width:3, height:"38%", background:"var(--gold)" }} />
          <div style={{ position:"absolute", bottom:26, right:-18, background:"var(--ch)", border:"1px solid rgba(201,168,76,.22)", padding:"13px 18px" }}>
            <div style={{ fontFamily:"var(--serif)", fontStyle:"italic", fontSize:".86rem", color:"var(--gold)", marginBottom:3 }}>"Golden by Nature"</div>
            <div style={{ fontFamily:"var(--sans)", fontSize:".62rem", letterSpacing:".14em", textTransform:"uppercase", color:"var(--mu)" }}>Aurum Kitchen Philosophy</div>
          </div>
        </div>
      </div>
    </section>
  );
}

/* ─── MENU ───────────────────────────────────────────────── */
function MenuSection() {
  const [tab, setTab] = useState("Breakfast");
  const ref = useReveal();
  const { img, items } = MENU_DATA[tab];

  return (
    <section id="menu" style={{ background:"var(--ch2)", padding:"clamp(80px,12vw,144px) clamp(18px,5vw,64px)", position:"relative", overflow:"hidden" }}>
      <span className="ghost" style={{ top:-10, left:-6 }}>02</span>
      <div style={{ maxWidth:1100, margin:"0 auto" }}>

        <div ref={ref} className="rv" style={{ marginBottom:46 }}>
          <SecLabel n={2} t="The Menu" />
          <h2 style={{ fontFamily:"var(--serif)", fontSize:"clamp(36px,7vw,74px)", fontWeight:300, lineHeight:1.06, letterSpacing:"-.015em" }}>
            Crafted with<br /><em style={{ color:"var(--gold)" }}>Golden Intention</em>
          </h2>
        </div>

        {/* tabs */}
        <div style={{ display:"flex", borderBottom:"1px solid rgba(201,168,76,.13)", marginBottom:0, overflowX:"auto" }}>
          {Object.keys(MENU_DATA).map(t => (
            <button key={t} onClick={() => setTab(t)}
              className={`tb${tab === t ? " on" : ""}`}
              style={{ background:"none", border:"none", cursor:"pointer", fontFamily:"var(--sans)", fontSize:".73rem", letterSpacing:".16em", textTransform:"uppercase", color: tab===t ? "var(--gold)" : "var(--mu)", padding:"13px 22px", whiteSpace:"nowrap", fontWeight: tab===t ? 500 : 300 }}>
              {t}
            </button>
          ))}
        </div>

        {/* banner */}
        <div style={{ position:"relative", marginBottom:30, overflow:"hidden", height:200 }}>
          <FImg key={tab} src={img} alt={tab}
            style={{ width:"100%", height:"100%", objectFit:"cover", objectPosition:"center 40%", filter:"brightness(.5) saturate(.75)", transition:"opacity .5s" }} />
          <div style={{ position:"absolute", inset:0, background:"linear-gradient(to right,rgba(0,0,0,.5),transparent 60%)" }} />
          <div style={{ position:"absolute", bottom:20, left:24 }}>
            <div style={{ fontFamily:"var(--serif)", fontStyle:"italic", fontSize:"clamp(1.6rem,4vw,2.8rem)", color:"var(--cr)", fontWeight:300, lineHeight:1 }}>{tab}</div>
            <div style={{ fontFamily:"var(--sans)", fontSize:".62rem", letterSpacing:".22em", textTransform:"uppercase", color:"var(--gold)", marginTop:5 }}>Aurum Kitchen</div>
          </div>
        </div>

        {/* cards */}
        <div style={{ display:"grid", gridTemplateColumns:"repeat(auto-fill,minmax(290px,1fr))", gap:3 }}>
          {items.map(item => (
            <div key={item.name} className="mc"
              style={{ background:"var(--ch)", padding:"26px 22px", border:"1px solid rgba(201,168,76,.07)", position:"relative" }}>
              {item.chef && (
                <div style={{ position:"absolute", top:13, right:13, display:"flex", alignItems:"center", gap:5, background:"rgba(201,168,76,.09)", border:"1px solid rgba(201,168,76,.25)", padding:"4px 9px", borderRadius:2 }}>
                  <svg width={8} height={8} viewBox="0 0 24 24" fill="var(--gold)"><polygon points="12,2 15.09,8.26 22,9.27 17,14.14 18.18,21.02 12,17.77 5.82,21.02 7,14.14 2,9.27 8.91,8.26"/></svg>
                  <span style={{ fontFamily:"var(--sans)", fontSize:".57rem", letterSpacing:".13em", textTransform:"uppercase", color:"var(--gold)" }}>Chef's Pick</span>
                </div>
              )}
              <h3 style={{ fontFamily:"var(--serif)", fontSize:"1.18rem", fontWeight:400, color:"var(--cr)", marginBottom:8, paddingRight: item.chef ? 85 : 0 }}>{item.name}</h3>
              <p style={{ fontFamily:"var(--sans)", fontSize:".81rem", color:"var(--mu)", lineHeight:1.7, marginBottom:16, fontWeight:300 }}>{item.desc}</p>
              <div style={{ fontFamily:"var(--serif)", fontSize:"1.02rem", color:"var(--gold)", fontStyle:"italic" }}>{item.price}</div>
            </div>
          ))}
        </div>

        <div style={{ textAlign:"center", marginTop:40 }}>
          <p style={{ fontFamily:"var(--serif)", fontStyle:"italic", color:"var(--mu)", fontSize:".86rem" }}>All prices inclusive of 5% VAT. Seasonal menu subject to change.</p>
        </div>
      </div>
    </section>
  );
}

/* ─── GALLERY ────────────────────────────────────────────── */
function Gallery() {
  const ref = useReveal();
  return (
    <section id="gallery" style={{ background:"var(--ch)", padding:"clamp(80px,12vw,144px) clamp(18px,5vw,64px)", position:"relative", overflow:"hidden" }}>
      <span className="ghost" style={{ top:-10, right:-6 }}>03</span>
      <div style={{ maxWidth:1200, margin:"0 auto" }}>

        <div ref={ref} className="rv" style={{ marginBottom:48 }}>
          <SecLabel n={3} t="Gallery" />
          <h2 style={{ fontFamily:"var(--serif)", fontSize:"clamp(36px,7vw,74px)", fontWeight:300, lineHeight:1.06, letterSpacing:"-.015em" }}>
            Life at<br /><em style={{ color:"var(--gold)" }}>Aurum</em>
          </h2>
        </div>

        <div className="gg" style={{ display:"grid", gridTemplateColumns:"repeat(4,1fr)", gridAutoRows:"210px", gap:4 }}>
          {GALLERY.map((g, i) => (
            <div key={i} className="gi" style={{ gridColumn:`span ${g.col}`, gridRow:`span ${g.row}` }}>
              <FImg src={g.img} alt={g.label}
                style={{ position:"absolute", inset:0, width:"100%", height:"100%", objectFit:"cover", transition:"transform .6s, filter .6s", filter:"brightness(.8)" }} />
              <div className="glabel"><span>{g.label}</span></div>
            </div>
          ))}
        </div>

        <div style={{ textAlign:"center", marginTop:30 }}>
          <button
            style={{ display:"inline-flex", alignItems:"center", gap:8, color:"var(--gold)", fontFamily:"var(--sans)", fontSize:".73rem", letterSpacing:".16em", textTransform:"uppercase", background:"none", border:"none", borderBottom:"1px solid rgba(201,168,76,.28)", paddingBottom:3, cursor:"pointer" }}>
            Follow @aurumcafe_ae
            <svg width={13} height={13} viewBox="0 0 24 24" fill="none" stroke="currentColor" strokeWidth={2}><rect x="2" y="2" width="20" height="20" rx="5"/><circle cx="12" cy="12" r="4"/><circle cx="17.5" cy="6.5" r="1" fill="currentColor"/></svg>
          </button>
        </div>
      </div>
    </section>
  );
}

/* ─── RESERVATION ────────────────────────────────────────── */
function Reservation() {
  const ref = useReveal();
  const [f, setF] = useState({ name:"", email:"", phone:"", date:"", time:"", guests:"2", note:"" });
  const [sent, setSent] = useState(false);

  const submit = (e) => {
    e.preventDefault();
    setSent(true);
    setTimeout(() => setSent(false), 5000);
  };

  return (
    <section id="reserve" style={{ background:"var(--ch2)", padding:"clamp(80px,12vw,144px) clamp(18px,5vw,64px)", position:"relative", overflow:"hidden" }}>
      <span className="ghost" style={{ top:-10, left:-6 }}>04</span>
      <div style={{ maxWidth:1100, margin:"0 auto", display:"grid", gridTemplateColumns:"repeat(auto-fit,minmax(290px,1fr))", gap:"clamp(44px,7vw,88px)", alignItems:"start" }}>

        {/* info */}
        <div ref={ref} className="rv">
          <SecLabel n={4} t="Reserve" />
          <h2 style={{ fontFamily:"var(--serif)", fontSize:"clamp(36px,6vw,62px)", fontWeight:300, lineHeight:1.06, letterSpacing:"-.015em", marginBottom:22 }}>
            Reserve<br /><em style={{ color:"var(--gold)" }}>Your Table</em>
          </h2>
          <p style={{ fontFamily:"var(--sans)", fontSize:".87rem", color:"var(--mu)", lineHeight:1.82, marginBottom:34 }}>
            For groups of 8 or more, or to arrange a private dining experience, please call us directly. We'll ensure every detail is flawless.
          </p>

          <div style={{ display:"flex", flexDirection:"column", gap:15, marginBottom:32 }}>
            {[
              { icon:<svg width={14} height={14} viewBox="0 0 24 24" fill="none" stroke="currentColor" strokeWidth={2}><path d="M21 10c0 7-9 13-9 13s-9-6-9-13a9 9 0 0 1 18 0z"/><circle cx="12" cy="10" r="3"/></svg>, t:"Al Furjan, Dubai, UAE" },
              { icon:<svg width={14} height={14} viewBox="0 0 24 24" fill="none" stroke="currentColor" strokeWidth={2}><path d="M22 16.92v3a2 2 0 0 1-2.18 2 19.79 19.79 0 0 1-8.63-3.07A19.5 19.5 0 0 1 4.69 13.6a19.79 19.79 0 0 1-3.07-8.67A2 2 0 0 1 3.6 3h3a2 2 0 0 1 2 1.72c.127.96.361 1.903.7 2.81a2 2 0 0 1-.45 2.11L7.91 10.6a16 16 0 0 0 6 6l.94-.94a2 2 0 0 1 2.11-.45c.907.339 1.85.573 2.81.7A2 2 0 0 1 22 16.92z"/></svg>, t:"+971 4 123 4567" },
              { icon:<svg width={14} height={14} viewBox="0 0 24 24" fill="none" stroke="currentColor" strokeWidth={2}><path d="M4 4h16c1.1 0 2 .9 2 2v12c0 1.1-.9 2-2 2H4c-1.1 0-2-.9-2-2V6c0-1.1.9-2 2-2z"/><polyline points="22,6 12,13 2,6"/></svg>, t:"hello@aurumcafe.ae" },
            ].map(({ icon, t }) => (
              <div key={t} style={{ display:"flex", alignItems:"center", gap:13 }}>
                <div style={{ width:34, height:34, border:"1px solid rgba(201,168,76,.25)", display:"flex", alignItems:"center", justifyContent:"center", color:"var(--gold)", flexShrink:0 }}>{icon}</div>
                <span style={{ fontFamily:"var(--sans)", fontSize:".85rem", color:"var(--mu)", fontWeight:300 }}>{t}</span>
              </div>
            ))}
          </div>

          {/* map */}
          <div style={{ position:"relative", height:220, border:"1px solid rgba(201,168,76,.1)", overflow:"hidden" }}>
            <iframe
              title="Al Furjan Dubai"
              src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d14445.827541965082!2d55.10378077577637!3d25.031680080059946!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x3e5f6b9b812dfa13%3A0x5e73d5bd1424b1fb!2sAl%20Furjan%20-%20Dubai!5e0!3m2!1sen!2sae!4v1750000000000!5m2!1sen!2sae"
              width="100%" height="220" style={{ border:0, filter:"invert(90%) hue-rotate(180deg) saturate(.65) brightness(.82)", display:"block" }}
              allowFullScreen loading="lazy" referrerPolicy="no-referrer-when-downgrade"
            />
            {[{t:0,l:0,w:"18px",h:"2px"},{t:0,l:0,w:"2px",h:"18px"},{b:0,r:0,w:"18px",h:"2px"},{b:0,r:0,w:"2px",h:"18px"}].map((s,i)=>(
              <div key={i} style={{ position:"absolute", background:"var(--gold)", ...s }} />
            ))}
          </div>
        </div>

        {/* form */}
        <div className="rv d2" style={{ background:"var(--ch)", padding:"clamp(24px,4vw,42px)", border:"1px solid rgba(201,168,76,.09)" }}>
          {sent ? (
            <div style={{ textAlign:"center", padding:"60px 0" }}>
              <div style={{ width:54, height:54, border:"1px solid var(--gold)", borderRadius:"50%", display:"flex", alignItems:"center", justifyContent:"center", margin:"0 auto 22px" }}>
                <svg width={20} height={20} viewBox="0 0 24 24" fill="none" stroke="var(--gold)" strokeWidth={2}><polyline points="20 6 9 17 4 12"/></svg>
              </div>
              <h3 style={{ fontFamily:"var(--serif)", fontSize:"1.65rem", color:"var(--gold)", marginBottom:10, fontWeight:300 }}>Reservation Received</h3>
              <p style={{ fontFamily:"var(--sans)", fontSize:".84rem", color:"var(--mu)" }}>We'll confirm your table within 24 hours.</p>
            </div>
          ) : (
            <form onSubmit={submit} style={{ display:"flex", flexDirection:"column", gap:12 }}>
              <div style={{ fontFamily:"var(--serif)", fontSize:"1.4rem", fontWeight:300, color:"var(--cr)", marginBottom:2 }}>Table Reservation</div>
              <GoldLine />
              <div className="fg" style={{ display:"grid", gridTemplateColumns:"1fr 1fr", gap:10 }}>
                <input className="inp" placeholder="Full Name" value={f.name} onChange={e=>setF({...f,name:e.target.value})} required />
                <input className="inp" type="email" placeholder="Email Address" value={f.email} onChange={e=>setF({...f,email:e.target.value})} required />
                <input className="inp" type="tel" placeholder="Phone Number" value={f.phone} onChange={e=>setF({...f,phone:e.target.value})} />
                <select className="inp" value={f.guests} onChange={e=>setF({...f,guests:e.target.value})}>
                  {[1,2,3,4,5,6,7,8].map(n=><option key={n} value={n}>{n} {n===1?"Guest":"Guests"}</option>)}
                </select>
                <input className="inp" type="date" value={f.date} onChange={e=>setF({...f,date:e.target.value})} required />
                <select className="inp" value={f.time} onChange={e=>setF({...f,time:e.target.value})} required>
                  <option value="">Preferred Time</option>
                  {["07:00","08:00","09:00","12:00","13:00","14:00","19:00","20:00","21:00","22:00"].map(t=><option key={t} value={t}>{t}</option>)}
                </select>
              </div>
              <textarea className="inp" rows={3} placeholder="Special requests or dietary requirements…" value={f.note} onChange={e=>setF({...f,note:e.target.value})} style={{ resize:"vertical" }} />
              <button type="submit"
                style={{ background:"var(--gold)", color:"var(--ch)", fontFamily:"var(--sans)", fontSize:".73rem", fontWeight:500, letterSpacing:".2em", textTransform:"uppercase", border:"none", padding:"15px", cursor:"pointer", marginTop:4, borderRadius:2, transition:"background .25s" }}
                onMouseEnter={e=>e.currentTarget.style.background="var(--gold-lt)"}
                onMouseLeave={e=>e.currentTarget.style.background="var(--gold)"}
              >Confirm Reservation</button>
            </form>
          )}
        </div>
      </div>
    </section>
  );
}

/* ─── FOOTER ─────────────────────────────────────────────── */
function Footer() {
  const [em, setEm] = useState("");
  const [subbed, setSubbed] = useState(false);

  return (
    <footer style={{ background:"var(--ch)", borderTop:"1px solid rgba(201,168,76,.09)" }}>
      <div style={{ padding:"clamp(56px,8vw,96px) clamp(18px,5vw,64px)", display:"grid", gridTemplateColumns:"repeat(auto-fit,minmax(190px,1fr))", gap:"clamp(32px,5vw,56px)", maxWidth:1100, margin:"0 auto" }}>

        {/* brand */}
        <div>
          <div style={{ fontFamily:"var(--serif)", fontSize:"2rem", fontWeight:300, letterSpacing:".14em", color:"var(--gold)", lineHeight:1 }}>AURUM</div>
          <div style={{ fontSize:".52rem", letterSpacing:".36em", color:"var(--mu)", textTransform:"uppercase", marginTop:2, marginBottom:14 }}>Restaurant & Cafe</div>
          <p style={{ fontFamily:"var(--sans)", fontSize:".81rem", color:"var(--mu)", lineHeight:1.82, fontWeight:300, maxWidth:215 }}>
            Al Furjan's destination for refined dining and specialty coffee, rooted in community.
          </p>
          <div style={{ display:"flex", gap:9, marginTop:18 }}>
            {[
              <svg width={13} height={13} viewBox="0 0 24 24" fill="none" stroke="currentColor" strokeWidth={2}><rect x="2" y="2" width="20" height="20" rx="5"/><circle cx="12" cy="12" r="4"/><circle cx="17.5" cy="6.5" r="1" fill="currentColor"/></svg>,
              <svg width={13} height={13} viewBox="0 0 24 24" fill="none" stroke="currentColor" strokeWidth={2}><path d="M18 2h-3a5 5 0 0 0-5 5v3H7v4h3v8h4v-8h3l1-4h-4V7a1 1 0 0 1 1-1h3z"/></svg>,
              <svg width={13} height={13} viewBox="0 0 24 24" fill="none" stroke="currentColor" strokeWidth={2}><path d="M23 3a10.9 10.9 0 0 1-3.14 1.53 4.48 4.48 0 0 0-7.86 3v1A10.66 10.66 0 0 1 3 4s-4 9 5 13a11.64 11.64 0 0 1-7 2c9 5 20 0 20-11.5a4.5 4.5 0 0 0-.08-.83A7.72 7.72 0 0 0 23 3z"/></svg>,
            ].map((icon, i) => (
              <a key={i} href="#"
                style={{ width:32, height:32, border:"1px solid rgba(201,168,76,.16)", display:"flex", alignItems:"center", justifyContent:"center", color:"var(--mu)", textDecoration:"none", transition:"all .25s", borderRadius:2 }}
                onMouseEnter={e=>{ e.currentTarget.style.borderColor="var(--gold)"; e.currentTarget.style.color="var(--gold)"; }}
                onMouseLeave={e=>{ e.currentTarget.style.borderColor="rgba(201,168,76,.16)"; e.currentTarget.style.color="var(--mu)"; }}
              >{icon}</a>
            ))}
          </div>
        </div>

        {/* hours */}
        <div>
          <div style={{ fontFamily:"var(--sans)", fontSize:".66rem", letterSpacing:".22em", textTransform:"uppercase", color:"var(--gold)", marginBottom:14 }}>Opening Hours</div>
          {HOURS.map(({ day, time }) => (
            <div key={day} style={{ marginBottom:11, paddingBottom:11, borderBottom:"1px solid rgba(255,255,255,.04)" }}>
              <div style={{ fontFamily:"var(--sans)", fontSize:".74rem", color:"var(--mu)", marginBottom:1 }}>{day}</div>
              <div style={{ fontFamily:"var(--serif)", fontSize:".9rem", color:"var(--cr)", fontStyle:"italic" }}>{time}</div>
            </div>
          ))}
        </div>

        {/* navigate */}
        <div>
          <div style={{ fontFamily:"var(--sans)", fontSize:".66rem", letterSpacing:".22em", textTransform:"uppercase", color:"var(--gold)", marginBottom:14 }}>Navigate</div>
          {FOOTER_LINKS.map(({ label, id }) => (
            <button key={id} onClick={() => scrollTo(id)}
              style={{ display:"block", width:"100%", textAlign:"left", fontFamily:"var(--sans)", fontSize:".81rem", color:"var(--mu)", background:"none", border:"none", cursor:"pointer", marginBottom:9, fontWeight:300, transition:"color .25s", padding:0 }}
              onMouseEnter={e=>e.currentTarget.style.color="var(--gold)"}
              onMouseLeave={e=>e.currentTarget.style.color="var(--mu)"}
            >{label}</button>
          ))}
          <a href="mailto:careers@aurumcafe.ae"
            style={{ display:"block", fontFamily:"var(--sans)", fontSize:".81rem", color:"var(--mu)", textDecoration:"none", marginBottom:9, fontWeight:300, transition:"color .25s" }}
            onMouseEnter={e=>e.currentTarget.style.color="var(--gold)"}
            onMouseLeave={e=>e.currentTarget.style.color="var(--mu)"}
          >Careers</a>
          <a href="mailto:press@aurumcafe.ae"
            style={{ display:"block", fontFamily:"var(--sans)", fontSize:".81rem", color:"var(--mu)", textDecoration:"none", fontWeight:300, transition:"color .25s" }}
            onMouseEnter={e=>e.currentTarget.style.color="var(--gold)"}
            onMouseLeave={e=>e.currentTarget.style.color="var(--mu)"}
          >Press</a>
        </div>

        {/* newsletter */}
        <div>
          <div style={{ fontFamily:"var(--sans)", fontSize:".66rem", letterSpacing:".22em", textTransform:"uppercase", color:"var(--gold)", marginBottom:14 }}>The Golden Letter</div>
          <p style={{ fontFamily:"var(--sans)", fontSize:".81rem", color:"var(--mu)", lineHeight:1.78, marginBottom:14, fontWeight:300 }}>
            Seasonal menus, private events & exclusive offers — straight to your inbox.
          </p>
          {subbed ? (
            <div style={{ fontFamily:"var(--serif)", fontStyle:"italic", color:"var(--gold)", fontSize:".93rem" }}>Welcome to the circle ✦</div>
          ) : (
            <div style={{ display:"flex", flexDirection:"column", gap:8 }}>
              <input className="inp" type="email" placeholder="Your email address" value={em} onChange={e=>setEm(e.target.value)} />
              <button onClick={() => em && setSubbed(true)}
                style={{ background:"transparent", border:"1px solid var(--gold)", color:"var(--gold)", fontFamily:"var(--sans)", fontSize:".68rem", letterSpacing:".2em", textTransform:"uppercase", padding:"11px", cursor:"pointer", borderRadius:2, transition:"all .25s" }}
                onMouseEnter={e=>{ e.currentTarget.style.background="var(--gold)"; e.currentTarget.style.color="var(--ch)"; }}
                onMouseLeave={e=>{ e.currentTarget.style.background="transparent"; e.currentTarget.style.color="var(--gold)"; }}
              >Subscribe</button>
            </div>
          )}
        </div>
      </div>

      {/* bottom */}
      <div style={{ borderTop:"1px solid rgba(201,168,76,.06)", padding:"16px clamp(18px,5vw,64px)", display:"flex", flexWrap:"wrap", gap:12, alignItems:"center", justifyContent:"space-between", maxWidth:1100, margin:"0 auto" }}>
        <span style={{ fontFamily:"var(--sans)", fontSize:".68rem", color:"var(--mu)" }}>
          © {new Date().getFullYear()} Aurum Restaurant & Cafe, Al Furjan, Dubai.
        </span>
        <div style={{ display:"flex", gap:18 }}>
          {["Privacy Policy","Terms","Allergen Info"].map(l => (
            <a key={l} href="#" style={{ fontFamily:"var(--sans)", fontSize:".68rem", color:"var(--mu)", textDecoration:"none", transition:"color .25s" }}
              onMouseEnter={e=>e.currentTarget.style.color="var(--gold)"}
              onMouseLeave={e=>e.currentTarget.style.color="var(--mu)"}
            >{l}</a>
          ))}
        </div>
      </div>
    </footer>
  );
}

/* ─── ROOT ───────────────────────────────────────────────── */
export default function Aurum() {
  const [open, setOpen] = useState(false);

  useEffect(() => {
    const el = document.createElement("style");
    el.textContent = CSS;
    document.head.appendChild(el);
    return () => document.head.removeChild(el);
  }, []);

  return (
    <div style={{ minHeight:"100vh", background:"var(--ch)" }}>
      <Nav open={open} setOpen={setOpen} />
      <Hero />
      <Story />
      <MenuSection />
      <Gallery />
      <Reservation />
      <Footer />
    </div>
  );
}
