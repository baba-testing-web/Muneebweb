import React, { useState, useMemo, useEffect, useRef } from "react";

const GLOBAL_STYLES = `
@import url('https://fonts.googleapis.com/css2?family=Poppins:wght@600;700&family=Inter:wght@400;500;600;700&display=swap');
html { scroll-behavior: smooth; }
.reveal { opacity: 0; transform: translateY(28px); transition: opacity .7s cubic-bezier(.22,.61,.36,1), transform .7s cubic-bezier(.22,.61,.36,1); }
.reveal-visible { opacity: 1; transform: translateY(0); }
.hover-lift { transition: transform .35s ease, box-shadow .35s ease; }
.hover-lift:hover { transform: translateY(-4px); box-shadow: 0 14px 30px rgba(20,24,28,0.12); }
@keyframes pageFade { from { opacity: 0; transform: translateY(16px); } to { opacity: 1; transform: translateY(0); } }
.page-fade { animation: pageFade .5s cubic-bezier(.22,.61,.36,1); }
@keyframes bump { 0% { transform: scale(1); } 35% { transform: scale(1.4); } 65% { transform: scale(0.92); } 100% { transform: scale(1); } }
.cart-bump { animation: bump .45s ease; }
@keyframes spin { to { transform: rotate(360deg); } }
.spinner { animation: spin .8s linear infinite; }
.btn-pop { transition: transform .2s ease, opacity .2s ease, box-shadow .2s ease; }
.btn-pop:hover { transform: translateY(-2px) scale(1.02); box-shadow: 0 10px 22px rgba(20,24,28,0.22); }
.btn-pop:active { transform: scale(0.97); }
.media-zoom { transition: transform .5s cubic-bezier(.22,.61,.36,1); }
.media-zoom-wrap:hover .media-zoom { transform: scale(1.08) rotate(1deg); }
.step-dot { transition: background .3s ease, color .3s ease, transform .3s ease; }
.fade-swap { animation: pageFade .4s ease; }
@keyframes slideIn { from { transform: translateX(-100%); } to { transform: translateX(0); } }
.menu-slide { animation: slideIn .35s cubic-bezier(.22,.61,.36,1); }
@keyframes fadeIn { from { opacity: 0; } to { opacity: 1; } }
.overlay-fade { animation: fadeIn .35s ease; }
@keyframes dropDown { from { opacity: 0; transform: translateY(-8px); } to { opacity: 1; transform: translateY(0); } }
.drop-down { animation: dropDown .25s ease; }
.no-scrollbar::-webkit-scrollbar { display: none; }
.no-scrollbar { -ms-overflow-style: none; scrollbar-width: none; }
.icon-btn { transition: transform .2s ease, opacity .2s ease; }
.icon-btn:hover { transform: translateY(-2px); opacity: 0.8; }
.chev { transition: transform .3s ease; }
.chev-open { transform: rotate(180deg); }
.acc-body { overflow: hidden; transition: max-height .35s ease; }
`;

/* Neutral, category-agnostic palette: charcoal + slate blue, with warm amber
   as a secondary accent. No single hue reads as "beauty" or "tech-only" so
   it works equally for electronics, office, crafts, or seasonal goods. */
const COLORS = {
  bg: "#FFFFFF",
  cream: "#F6F7F8",
  soft: "#EEF0F2",
  ink: "#1F2328",
  mute: "#6B7280",
  primary: "#33475B",
  accent: "#D98A3D",
  line: "#E5E7EB",
  success: "#3E8E58",
  black: "#111111",
};

const CATS = ["Electronics", "Office", "Crafts", "Seasonal"];
const catColors = {
  Electronics: "#3B6FD6",
  Office: "#D98A3D",
  Crafts: "#4E9B6E",
  Seasonal: "#B65C4D",
};
const SUBCATS = {
  Electronics: ["Audio", "Gadgets", "Accessories"],
  Office: ["Desk", "Stationery", "Organization"],
  Crafts: ["Art Supplies", "DIY Kits", "Sewing"],
  Seasonal: ["Summer", "Winter", "Festive"],
};

const PRODUCTS = [
  { id: 1, name: "Wireless Earbuds Pro", cat: "Electronics", price: 45, swatch: catColors.Electronics, img: "https://picsum.photos/seed/earbuds1/500/500", note: "24hr battery, ANC", desc: "True wireless earbuds with active noise cancellation and a case that gives you a full extra day of charge on the go.", delivery: "2-4 business days", rating: 4.6, reviews: 284, stock: 52 },
  { id: 2, name: "Smart LED Desk Lamp", cat: "Electronics", price: 28, swatch: catColors.Electronics, img: "https://picsum.photos/seed/lamp2/500/500", note: "Touch dimmer, 3 tones", desc: "A touch-controlled desk lamp with three color temperatures and stepless dimming, plus a built-in USB charging port.", delivery: "3-5 business days", rating: 4.5, reviews: 121, stock: 40 },
  { id: 3, name: "Portable Bluetooth Speaker", cat: "Electronics", price: 39, swatch: catColors.Electronics, img: "https://picsum.photos/seed/speaker3/500/500", note: "Water-resistant, 12hr", desc: "Compact speaker with surprisingly full bass, IPX6 water resistance, and 12 hours of playtime on a single charge.", delivery: "2-4 business days", rating: 4.7, reviews: 366, stock: 61 },
  { id: 4, name: "Ergonomic Wireless Mouse", cat: "Office", price: 22, swatch: catColors.Office, img: "https://picsum.photos/seed/mouse4/500/500", note: "Vertical grip design", desc: "A vertical grip reduces wrist strain during long work sessions, with silent clicks and a 6-month battery life.", delivery: "2-4 business days", rating: 4.4, reviews: 98, stock: 70 },
  { id: 5, name: "Leather Desk Organizer", cat: "Office", price: 19, swatch: catColors.Office, img: "https://picsum.photos/seed/organizer5/500/500", note: "Pen, phone & card slots", desc: "A compact organizer that keeps pens, your phone, and cards within reach without cluttering your desk.", delivery: "3-5 business days", rating: 4.6, reviews: 143, stock: 55 },
  { id: 6, name: "Notebook & Pen Set", cat: "Office", price: 14, swatch: catColors.Office, img: "https://picsum.photos/seed/notebook6/500/500", note: "Dot grid, 160 pages", desc: "A dot-grid notebook paired with a smooth gel pen, made for planning, sketching, or daily notes.", delivery: "2-4 business days", rating: 4.7, reviews: 176, stock: 90 },
  { id: 7, name: "Watercolor Paint Set", cat: "Crafts", price: 17, swatch: catColors.Crafts, img: "https://picsum.photos/seed/paint7/500/500", note: "24 vivid colors", desc: "A beginner-friendly set of 24 richly pigmented watercolors with a built-in mixing palette and brush.", delivery: "3-5 business days", rating: 4.5, reviews: 87, stock: 64 },
  { id: 8, name: "Embroidery Starter Kit", cat: "Crafts", price: 12, swatch: catColors.Crafts, img: "https://picsum.photos/seed/embroidery8/500/500", note: "Hoop, thread & needles", desc: "Everything needed to start embroidery: wooden hoop, an assortment of thread colors, needles, and a printed pattern guide.", delivery: "4-6 business days", rating: 4.6, reviews: 59, stock: 48 },
  { id: 9, name: "Hot Glue Gun Kit", cat: "Crafts", price: 15, swatch: catColors.Crafts, img: "https://picsum.photos/seed/glue9/500/500", note: "20 glue sticks included", desc: "A dual-temperature glue gun with 20 glue sticks, ideal for DIY projects, repairs, and craft builds.", delivery: "3-5 business days", rating: 4.3, reviews: 64, stock: 58 },
  { id: 10, name: "Insulated Travel Mug", cat: "Seasonal", price: 16, swatch: catColors.Seasonal, img: "https://picsum.photos/seed/mug10/500/500", note: "Keeps drinks hot 8hr", desc: "Double-walled stainless steel that keeps coffee hot for 8 hours or drinks cold for 12, with a leak-proof lid.", delivery: "2-4 business days", rating: 4.7, reviews: 210, stock: 75 },
  { id: 11, name: "Rechargeable Handheld Fan", cat: "Seasonal", price: 13, swatch: catColors.Seasonal, img: "https://picsum.photos/seed/fan11/500/500", note: "3 speeds, USB-C", desc: "A pocket-sized fan with three speed settings and a USB-C charge that lasts a full day out in the heat.", delivery: "2-4 business days", rating: 4.4, reviews: 132, stock: 66 },
  { id: 12, name: "Festive String Lights", cat: "Seasonal", price: 11, swatch: catColors.Seasonal, img: "https://picsum.photos/seed/lights12/500/500", note: "10m, warm white", desc: "Warm white LED string lights for porches, windows, or gatherings, with a built-in timer so you never forget to switch them off.", delivery: "3-5 business days", rating: 4.6, reviews: 154, stock: 82 },
];

function Reveal({ children, delay = 0, className = "" }) {
  const ref = useRef(null);
  const [visible, setVisible] = useState(false);
  useEffect(() => {
    const el = ref.current;
    if (!el) return;
    const obs = new IntersectionObserver(
      ([entry]) => { if (entry.isIntersecting) { setVisible(true); obs.unobserve(el); } },
      { threshold: 0.15 }
    );
    obs.observe(el);
    return () => obs.disconnect();
  }, []);
  return (
    <div ref={ref} className={`reveal ${visible ? "reveal-visible" : ""} ${className}`} style={{ transitionDelay: `${delay}ms` }}>
      {children}
    </div>
  );
}

function Swatch({ color, size = 14 }) {
  return <span style={{ display: "inline-block", width: size, height: size, borderRadius: "50%", background: color, border: "1px solid rgba(0,0,0,0.08)" }} />;
}

function MenuIcon({ size = 20, color = "currentColor" }) {
  return (
    <svg width={size} height={size} viewBox="0 0 24 24" fill="none">
      <path d="M3 6H21" stroke={color} strokeWidth="1.8" strokeLinecap="round" />
      <path d="M3 12H21" stroke={color} strokeWidth="1.8" strokeLinecap="round" />
      <path d="M3 18H21" stroke={color} strokeWidth="1.8" strokeLinecap="round" />
    </svg>
  );
}

function SearchIcon({ size = 19, color = "currentColor" }) {
  return (
    <svg width={size} height={size} viewBox="0 0 24 24" fill="none">
      <circle cx="11" cy="11" r="7" stroke={color} strokeWidth="1.8" />
      <path d="M21 21L16.65 16.65" stroke={color} strokeWidth="1.8" strokeLinecap="round" />
    </svg>
  );
}

function CartIcon({ size = 21, color = "currentColor" }) {
  return (
    <svg width={size} height={size} viewBox="0 0 24 24" fill="none">
      <path d="M6 8H20L18.5 18.5C18.36 19.42 17.57 20.1 16.64 20.1H8.94C8 20.1 7.21 19.41 7.08 18.49L5.4 6.6C5.32 6.03 4.83 5.6 4.25 5.6H2.5" stroke={color} strokeWidth="1.7" strokeLinecap="round" strokeLinejoin="round" />
      <circle cx="10" cy="23" r="1.4" fill={color} />
      <circle cx="17" cy="23" r="1.4" fill={color} />
    </svg>
  );
}

function CloseIcon({ size = 18, color = "currentColor" }) {
  return (
    <svg width={size} height={size} viewBox="0 0 24 24" fill="none">
      <path d="M5 5L19 19" stroke={color} strokeWidth="1.8" strokeLinecap="round" />
      <path d="M19 5L5 19" stroke={color} strokeWidth="1.8" strokeLinecap="round" />
    </svg>
  );
}

function ChevronIcon({ size = 13, color = "currentColor", open }) {
  return (
    <svg width={size} height={size} viewBox="0 0 24 24" fill="none" className={`chev ${open ? "chev-open" : ""}`}>
      <path d="M6 9L12 15L18 9" stroke={color} strokeWidth="2" strokeLinecap="round" strokeLinejoin="round" />
    </svg>
  );
}

function PlusCartIcon({ size = 14, color = "currentColor" }) {
  return (
    <svg width={size} height={size} viewBox="0 0 24 24" fill="none">
      <path d="M6 8H20L18.5 18.5C18.36 19.42 17.57 20.1 16.64 20.1H8.94C8 20.1 7.21 19.41 7.08 18.49L5.4 6.6C5.32 6.03 4.83 5.6 4.25 5.6H2.5" stroke={color} strokeWidth="1.7" strokeLinecap="round" strokeLinejoin="round" />
      <path d="M14.5 2.5V7.5M12 5H17" stroke={color} strokeWidth="1.7" strokeLinecap="round" />
    </svg>
  );
}

function Stars({ rating }) {
  const full = Math.round(rating);
  return (
    <span style={{ color: COLORS.accent, fontSize: 13, letterSpacing: 1 }}>
      {"\u2605".repeat(full)}<span style={{ color: COLORS.line }}>{"\u2605".repeat(5 - full)}</span>
    </span>
  );
}

function Logo({ light }) {
  return (
    <div className="flex items-center gap-2">
      <div style={{ width: 26, height: 26, borderRadius: 6, background: light ? "#fff" : COLORS.primary, display: "flex", alignItems: "center", justifyContent: "center" }}>
        <span style={{ fontFamily: "'Poppins', sans-serif", color: light ? COLORS.primary : "#fff", fontWeight: 700, fontSize: 14 }}>V</span>
      </div>
      <span style={{ fontFamily: "'Inter', sans-serif", color: light ? "#fff" : COLORS.ink, letterSpacing: "0.1em", fontWeight: 700 }} className="text-base uppercase">
        Vertex Mart
      </span>
    </div>
  );
}

const NAV_ITEMS = ["Home", "About"];

function NavBar({ page, setPage, cartCount, cartBump, onOpenMenu, searchOpen, setSearchOpen, searchTerm, setSearchTerm, onSearchSubmit }) {
  return (
    <div style={{ background: COLORS.black }} className="sticky top-0 z-30">
      <div className="max-w-6xl mx-auto px-4 py-4 flex items-center justify-between">
        <div className="flex items-center gap-4">
          <button onClick={onOpenMenu} aria-label="Menu" className="icon-btn text-white"><MenuIcon /></button>
          <button onClick={() => setSearchOpen(!searchOpen)} aria-label="Search" className="icon-btn text-white"><SearchIcon /></button>
        </div>

        <button onClick={() => setPage("Home")} className="cursor-pointer">
          <Logo light />
        </button>

        <button onClick={() => setPage("Cart")} className={`relative text-white ${cartBump ? "cart-bump" : ""}`} aria-label="Cart">
          <CartIcon />
          <span className="absolute -top-2 -right-2 flex items-center justify-center" style={{ background: "#fff", color: COLORS.black, borderRadius: "50%", width: 17, height: 17, fontSize: 10, fontFamily: "'Inter', sans-serif", fontWeight: 700 }}>
            {cartCount}
          </span>
        </button>
      </div>

      {searchOpen && (
        <div className="drop-down px-4 pb-4">
          <form className="max-w-6xl mx-auto flex items-center gap-2" onSubmit={(e) => { e.preventDefault(); onSearchSubmit(); }}>
            <div className="flex-1 flex items-center gap-2 bg-white rounded-sm px-3">
              <span style={{ color: COLORS.mute }}><SearchIcon size={16} /></span>
              <input
                autoFocus
                value={searchTerm}
                onChange={(e) => setSearchTerm(e.target.value)}
                placeholder="Search products..."
                style={{ fontFamily: "'Inter', sans-serif", border: "none", outline: "none", padding: "10px 4px", flex: 1 }}
              />
            </div>
            <button type="submit" style={{ background: COLORS.primary, color: "#fff", fontFamily: "'Inter', sans-serif" }} className="px-4 py-2.5 rounded-sm text-sm btn-pop">Go</button>
          </form>
        </div>
      )}
    </div>
  );
}

function SlideMenu({ open, onClose, page, setPage, cartCount, goToShop }) {
  const [openAcc, setOpenAcc] = useState(null);
  if (!open) return null;
  return (
    <div className="fixed inset-0 z-40 overlay-fade" style={{ background: "rgba(0,0,0,0.45)" }} onClick={onClose}>
      <div className="menu-slide h-full bg-white flex flex-col" style={{ width: "88%", maxWidth: 380, overflowY: "auto" }} onClick={(e) => e.stopPropagation()}>
        <div className="flex items-center justify-between px-5 py-4" style={{ borderBottom: `1px solid ${COLORS.line}` }}>
          <Logo />
          <button onClick={onClose} aria-label="Close menu" style={{ color: COLORS.ink }}><CloseIcon /></button>
        </div>

        <div className="p-5">
          <div className="rounded-md p-5 flex flex-col gap-1" style={{ background: `linear-gradient(115deg, ${COLORS.primary}, ${COLORS.ink})`, color: "#fff" }}>
            <span style={{ fontFamily: "'Inter', sans-serif", fontSize: 11, letterSpacing: "0.15em" }} className="uppercase opacity-90">Vertex Mart</span>
            <span style={{ fontFamily: "'Poppins', sans-serif" }} className="text-xl font-semibold">Everything you need</span>
            <span style={{ fontFamily: "'Inter', sans-serif", fontSize: 13 }} className="opacity-90">Electronics, office, crafts &amp; seasonal picks in one place</span>
          </div>
        </div>

        <div className="px-5 grid grid-cols-4 gap-2 mb-2">
          {CATS.map((c) => (
            <button key={c} onClick={() => { goToShop(c); onClose(); }} className="flex flex-col items-center gap-2 icon-btn">
              <div style={{ width: 52, height: 52, borderRadius: "50%", background: `${catColors[c]}22`, display: "flex", alignItems: "center", justifyContent: "center" }}>
                <Swatch color={catColors[c]} size={20} />
              </div>
              <span style={{ fontFamily: "'Inter', sans-serif", fontSize: 11, color: COLORS.ink, textAlign: "center" }}>{c}</span>
            </button>
          ))}
        </div>

        <div className="mt-3">
          {NAV_ITEMS.map((it) => (
            <button
              key={it}
              onClick={() => { setPage(it); onClose(); }}
              className="w-full text-left px-5 py-4 flex items-center justify-between"
              style={{ borderTop: `1px solid ${COLORS.line}`, fontFamily: "'Inter', sans-serif", fontSize: 16, fontWeight: 600, color: page === it ? COLORS.primary : COLORS.ink }}
            >
              {it}
            </button>
          ))}

          {CATS.map((c) => (
            <div key={c} style={{ borderTop: `1px solid ${COLORS.line}` }}>
              <button
                onClick={() => setOpenAcc(openAcc === c ? null : c)}
                className="w-full text-left px-5 py-4 flex items-center justify-between"
                style={{ fontFamily: "'Inter', sans-serif", fontSize: 16, fontWeight: 600, color: COLORS.ink }}
              >
                {c}
                <ChevronIcon open={openAcc === c} />
              </button>
              <div className="acc-body px-5" style={{ maxHeight: openAcc === c ? 200 : 0 }}>
                <div className="flex flex-col pb-3">
                  {SUBCATS[c].map((s) => (
                    <button key={s} onClick={() => { goToShop(c); onClose(); }} className="text-left py-2" style={{ fontFamily: "'Inter', sans-serif", fontSize: 14, color: COLORS.mute }}>
                      {s}
                    </button>
                  ))}
                </div>
              </div>
            </div>
          ))}

          <button onClick={() => { setPage("About"); onClose(); }} className="w-full text-left px-5 py-4" style={{ borderTop: `1px solid ${COLORS.line}`, fontFamily: "'Inter', sans-serif", fontSize: 16, fontWeight: 600, color: COLORS.ink }}>
            Bulk &amp; Corporate Orders
          </button>
        </div>
      </div>
    </div>
  );
}

function ProductCard({ p, onAdd, onOpen, compact }) {
  const was = Math.round(p.price * 1.3);
  return (
    <div className="flex flex-col hover-lift" style={{ border: `1px solid ${COLORS.line}`, borderRadius: 6, overflow: "hidden", background: COLORS.bg, minWidth: compact ? 220 : undefined }}>
      <button onClick={() => onOpen(p)} className="media-zoom-wrap block w-full" style={{ background: p.img ? COLORS.cream : `linear-gradient(155deg, ${p.swatch}33, ${COLORS.cream})`, height: 160, overflow: "hidden" }}>
        {p.img ? (
          <img src={p.img} alt={p.name} className="media-zoom w-full h-full" style={{ objectFit: "cover" }} />
        ) : (
          <div className="w-full h-full flex items-center justify-center">
            <div className="media-zoom" style={{ width: 56, height: 56, borderRadius: "50%", background: p.swatch, boxShadow: `0 8px 20px ${p.swatch}55` }} />
          </div>
        )}
      </button>
      <div className="p-4 flex flex-col gap-1 flex-1">
        <span style={{ fontFamily: "'Inter', sans-serif", color: p.swatch, fontSize: 11, letterSpacing: "0.08em" }} className="uppercase font-bold">{p.cat}</span>
        <button onClick={() => onOpen(p)} className="text-left">
          <h3 style={{ fontFamily: "'Poppins', sans-serif", color: COLORS.ink }} className="text-base font-semibold leading-snug hover:underline">{p.name}</h3>
        </button>
        <div className="flex items-center gap-2">
          <Stars rating={p.rating} />
          <span style={{ fontFamily: "'Inter', sans-serif", color: COLORS.mute, fontSize: 12 }}>({p.reviews})</span>
        </div>
        <p style={{ fontFamily: "'Inter', sans-serif", color: COLORS.mute, fontSize: 13 }} className="mb-1">{p.note}</p>
        <div className="mt-auto flex items-center justify-between pt-2">
          <div className="flex items-baseline gap-2">
            <span style={{ fontFamily: "'Inter', sans-serif", color: COLORS.ink }} className="font-semibold">${p.price}</span>
            <span style={{ fontFamily: "'Inter', sans-serif", color: COLORS.mute, fontSize: 12, textDecoration: "line-through" }}>${was}</span>
          </div>
          <button onClick={() => onAdd(p)} aria-label={`Add ${p.name} to cart`} className="btn-pop flex items-center gap-1.5" style={{ fontFamily: "'Inter', sans-serif", background: COLORS.primary, color: "#fff", fontSize: 13 }}>
            <span className="pl-3 pr-3.5 py-2 flex items-center gap-1.5 rounded-sm">
              <PlusCartIcon size={14} color="#fff" />
              Add
            </span>
          </button>
        </div>
      </div>
    </div>
  );
}

function HomePage({ setPage, onAdd, onOpen, goToShop }) {
  const bestSellers = PRODUCTS.slice(0, 6);
  return (
    <div className="page-fade">
      <Reveal>
        <div style={{ background: `linear-gradient(135deg, ${COLORS.primary} 0%, ${COLORS.ink} 100%)` }} className="relative overflow-hidden">
          <div className="max-w-6xl mx-auto px-6 py-20 flex flex-col items-start gap-4 relative z-10">
            <span style={{ fontFamily: "'Inter', sans-serif", color: "#fff", fontSize: 12, letterSpacing: "0.2em" }} className="uppercase opacity-90">Vertex Mart</span>
            <h1 style={{ fontFamily: "'Poppins', sans-serif", color: "#fff", maxWidth: 560 }} className="text-4xl md:text-5xl font-bold leading-tight">
              Everything you need, in every category.
            </h1>
            <p style={{ fontFamily: "'Inter', sans-serif", color: "#fff", maxWidth: 480 }} className="opacity-85">
              Electronics, office essentials, craft supplies, and seasonal picks &mdash; all in one store.
            </p>
          </div>
          <div style={{ position: "absolute", right: -60, top: -40, width: 260, height: 260, borderRadius: "50%", background: "rgba(255,255,255,0.06)" }} />
          <div style={{ position: "absolute", right: 40, bottom: -80, width: 180, height: 180, borderRadius: "50%", background: "rgba(255,255,255,0.06)" }} />
          <div className="flex items-center justify-center gap-2 pb-5 relative z-10">
            {[0, 1, 2].map((d) => (
              <span key={d} style={{ width: d === 0 ? 18 : 6, height: 6, borderRadius: 3, background: d === 0 ? "#fff" : "rgba(255,255,255,0.4)", transition: "width .3s ease" }} />
            ))}
          </div>
        </div>
      </Reveal>

      <div className="max-w-6xl mx-auto px-6 py-8">
        <div className="flex justify-between gap-3 overflow-x-auto no-scrollbar">
          {CATS.map((c, idx) => (
            <Reveal key={c} delay={idx * 60} className="flex-shrink-0">
              <button onClick={() => goToShop(c)} className="flex flex-col items-center gap-2 icon-btn" style={{ width: 88 }}>
                <div style={{ width: 64, height: 64, borderRadius: "50%", background: `${catColors[c]}1f`, display: "flex", alignItems: "center", justifyContent: "center" }}>
                  <Swatch color={catColors[c]} size={24} />
                </div>
                <span style={{ fontFamily: "'Inter', sans-serif", fontSize: 12, color: COLORS.ink, textAlign: "center" }}>{c}</span>
              </button>
            </Reveal>
          ))}
        </div>
      </div>

      <Reveal>
        <div className="max-w-6xl mx-auto px-6">
          <div className="rounded-md flex items-center px-8 py-8 flex-wrap gap-4" style={{ background: `linear-gradient(100deg, ${COLORS.accent}, ${COLORS.primary})` }}>
            <div>
              <span style={{ fontFamily: "'Inter', sans-serif", color: "#fff", fontSize: 12, letterSpacing: "0.15em" }} className="uppercase opacity-90">Limited time</span>
              <div style={{ fontFamily: "'Poppins', sans-serif", color: "#fff" }} className="text-2xl font-bold">Seasonal picks &mdash; up to 30% off</div>
            </div>
          </div>
        </div>
      </Reveal>

      <div className="max-w-6xl mx-auto px-6 py-16">
        <Reveal>
          <div className="flex items-center gap-3 mb-8">
            <Swatch color={COLORS.primary} />
            <h2 style={{ fontFamily: "'Poppins', sans-serif", color: COLORS.ink }} className="text-2xl font-bold">Best sellers</h2>
          </div>
        </Reveal>
        <div className="flex gap-5 overflow-x-auto no-scrollbar pb-2">
          {bestSellers.map((p, idx) => (
            <Reveal key={p.id} delay={idx * 60} className="flex-shrink-0">
              <ProductCard p={p} onAdd={onAdd} onOpen={onOpen} compact />
            </Reveal>
          ))}
        </div>
      </div>
    </div>
  );
}

function ShopPage({ onAdd, onOpen, category, setCategory, searchTerm, clearSearch }) {
  const shown = useMemo(() => {
    if (searchTerm) {
      const q = searchTerm.toLowerCase();
      return PRODUCTS.filter((p) => p.name.toLowerCase().includes(q) || p.note.toLowerCase().includes(q) || p.cat.toLowerCase().includes(q));
    }
    return PRODUCTS.filter((p) => p.cat === category);
  }, [category, searchTerm]);

  return (
    <div className="max-w-6xl mx-auto px-6 py-14 page-fade">
      <h1 style={{ fontFamily: "'Poppins', sans-serif", color: COLORS.ink }} className="text-3xl font-bold mb-2">
        {searchTerm ? `Results for "${searchTerm}"` : "Products"}
      </h1>
      <p style={{ fontFamily: "'Inter', sans-serif", color: COLORS.mute }} className="mb-8">
        {shown.length} products {searchTerm ? "" : `in ${category}`}
      </p>

      {searchTerm ? (
        <button onClick={clearSearch} style={{ fontFamily: "'Inter', sans-serif", fontSize: 13, color: COLORS.primary }} className="mb-8 underline">Clear search &amp; browse categories</button>
      ) : (
        <div className="flex gap-2 mb-8 flex-wrap">
          {CATS.map((c) => (
            <button key={c} onClick={() => setCategory(c)} style={{ fontFamily: "'Inter', sans-serif", fontSize: 13, border: `1px solid ${category === c ? COLORS.primary : COLORS.line}`, color: category === c ? "#fff" : COLORS.ink, background: category === c ? COLORS.primary : "#fff", transition: "background .25s ease, color .25s ease" }} className="px-4 py-2 rounded-full">
              {c}
            </button>
          ))}
        </div>
      )}

      <div className="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-5">
        {shown.map((p, idx) => (
          <Reveal key={p.id} delay={(idx % 3) * 80}>
            <ProductCard p={p} onAdd={onAdd} onOpen={onOpen} />
          </Reveal>
        ))}
        {shown.length === 0 && <p style={{ fontFamily: "'Inter', sans-serif", color: COLORS.mute }}>No products matched.</p>}
      </div>
    </div>
  );
}

function ProductDetailPage({ product, onAdd, setPage, onOpen }) {
  const [qty, setQty] = useState(1);
  const [added, setAdded] = useState(false);
  if (!product) {
    return (
      <div className="max-w-3xl mx-auto px-6 py-20 text-center page-fade">
        <p style={{ fontFamily: "'Inter', sans-serif", color: COLORS.mute }}>No product selected.</p>
        <button onClick={() => setPage("Home")} className="mt-4 underline" style={{ fontFamily: "'Inter', sans-serif", color: COLORS.primary }}>Back to home</button>
      </div>
    );
  }
  const related = PRODUCTS.filter((p) => p.cat === product.cat && p.id !== product.id).slice(0, 3);

  const handleAdd = () => {
    for (let i = 0; i < qty; i++) onAdd(product);
    setAdded(true);
    setTimeout(() => setAdded(false), 1600);
  };

  return (
    <div className="max-w-6xl mx-auto px-6 py-12 page-fade">
      <div style={{ fontFamily: "'Inter', sans-serif", color: COLORS.mute, fontSize: 13 }} className="mb-6 flex items-center gap-2">
        <button onClick={() => setPage("Home")} className="hover:underline">Home</button>
        <span>/</span><span>{product.cat}</span><span>/</span>
        <span style={{ color: COLORS.ink }}>{product.name}</span>
      </div>

      <div className="grid grid-cols-1 md:grid-cols-2 gap-10">
        <Reveal>
          <div className="media-zoom-wrap flex items-center justify-center" style={{ background: product.img ? COLORS.cream : `linear-gradient(155deg, ${product.swatch}33, ${COLORS.cream})`, borderRadius: 8, height: 420, overflow: "hidden" }}>
            {product.img ? (
              <img src={product.img} alt={product.name} className="media-zoom w-full h-full" style={{ objectFit: "cover" }} />
            ) : (
              <div className="media-zoom" style={{ width: 140, height: 140, borderRadius: "50%", background: product.swatch, boxShadow: `0 20px 50px ${product.swatch}66` }} />
            )}
          </div>
        </Reveal>

        <Reveal delay={100}>
          <div className="flex flex-col gap-4">
            <span style={{ fontFamily: "'Inter', sans-serif", color: product.swatch, fontSize: 12, letterSpacing: "0.1em" }} className="uppercase font-medium">{product.cat}</span>
            <h1 style={{ fontFamily: "'Poppins', sans-serif", color: COLORS.ink }} className="text-3xl font-bold leading-tight">{product.name}</h1>
            <div className="flex items-center gap-2">
              <Stars rating={product.rating} />
              <span style={{ fontFamily: "'Inter', sans-serif", color: COLORS.mute, fontSize: 13 }}>{product.rating} &middot; {product.reviews} reviews</span>
            </div>
            <div style={{ fontFamily: "'Poppins', sans-serif", color: COLORS.ink }} className="text-2xl font-bold">${product.price}</div>
            <p style={{ fontFamily: "'Inter', sans-serif", color: COLORS.mute, lineHeight: 1.7 }}>{product.desc}</p>

            <div className="flex flex-col gap-2 p-4" style={{ border: `1px solid ${COLORS.line}`, borderRadius: 6, background: COLORS.cream }}>
              <div className="flex items-center gap-2" style={{ fontFamily: "'Inter', sans-serif", color: COLORS.ink, fontSize: 14 }}>
                <span>&#128666;</span><span>Delivery: <strong>{product.delivery}</strong></span>
              </div>
              <div className="flex items-center gap-2" style={{ fontFamily: "'Inter', sans-serif", color: COLORS.ink, fontSize: 14 }}>
                <span>&#8617;</span><span>Free returns within 14 days</span>
              </div>
              <div className="flex items-center gap-2" style={{ fontFamily: "'Inter', sans-serif", color: COLORS.success, fontSize: 14 }}>
                <span>&#10003;</span><span>{product.stock} in stock</span>
              </div>
            </div>

            <div className="flex items-center gap-3 mt-2">
              <div className="flex items-center gap-2" style={{ fontFamily: "'Inter', sans-serif" }}>
                <button onClick={() => setQty((q) => Math.max(1, q - 1))} className="w-9 h-9" style={{ border: `1px solid ${COLORS.line}` }}>&minus;</button>
                <span className="w-8 text-center">{qty}</span>
                <button onClick={() => setQty((q) => q + 1)} className="w-9 h-9" style={{ border: `1px solid ${COLORS.line}` }}>+</button>
              </div>
              <button onClick={handleAdd} className="btn-pop flex-1" style={{ fontFamily: "'Inter', sans-serif", background: COLORS.primary, color: "#fff" }}>
                <span className="px-6 py-3 rounded-sm block text-center">{added ? "Added \u2713" : "Add to cart"}</span>
              </button>
            </div>
          </div>
        </Reveal>
      </div>

      {related.length > 0 && (
        <div className="mt-20">
          <Reveal>
            <h2 style={{ fontFamily: "'Poppins', sans-serif", color: COLORS.ink }} className="text-xl font-bold mb-6">You may also like</h2>
          </Reveal>
          <div className="grid grid-cols-1 sm:grid-cols-3 gap-5">
            {related.map((p, idx) => (
              <Reveal key={p.id} delay={idx * 80}>
                <ProductCard p={p} onAdd={onAdd} onOpen={onOpen} />
              </Reveal>
            ))}
          </div>
        </div>
      )}
    </div>
  );
}

function CartPage({ cart, setCart, setPage }) {
  const total = cart.reduce((s, i) => s + i.price * i.qty, 0);
  const changeQty = (id, delta) => {
    setCart((prev) => prev.map((i) => (i.id === id ? { ...i, qty: Math.max(1, i.qty + delta) } : i)).filter((i) => i.qty > 0));
  };
  const remove = (id) => setCart((prev) => prev.filter((i) => i.id !== id));

  return (
    <div className="max-w-4xl mx-auto px-6 py-14 page-fade">
      <h1 style={{ fontFamily: "'Poppins', sans-serif", color: COLORS.ink }} className="text-3xl font-bold mb-8">Your cart</h1>
      {cart.length === 0 ? (
        <div className="flex flex-col items-start gap-4">
          <p style={{ fontFamily: "'Inter', sans-serif", color: COLORS.mute }}>Your cart is empty.</p>
          <button onClick={() => setPage("Home")} className="btn-pop" style={{ fontFamily: "'Inter', sans-serif", background: COLORS.primary, color: "#fff" }}>
            <span className="px-6 py-3 rounded-sm block">Browse products</span>
          </button>
        </div>
      ) : (
        <div className="flex flex-col gap-4">
          {cart.map((i) => (
            <div key={i.id} className="flex items-center gap-4 p-4" style={{ border: `1px solid ${COLORS.line}`, borderRadius: 6 }}>
              <div style={{ width: 44, height: 44, borderRadius: "50%", background: i.swatch, flexShrink: 0 }} />
              <div className="flex-1">
                <div style={{ fontFamily: "'Poppins', sans-serif", color: COLORS.ink }} className="text-base font-semibold">{i.name}</div>
                <div style={{ fontFamily: "'Inter', sans-serif", color: COLORS.mute, fontSize: 13 }}>${i.price} each</div>
              </div>
              <div className="flex items-center gap-2" style={{ fontFamily: "'Inter', sans-serif" }}>
                <button onClick={() => changeQty(i.id, -1)} className="w-7 h-7" style={{ border: `1px solid ${COLORS.line}` }}>&minus;</button>
                <span className="w-6 text-center">{i.qty}</span>
                <button onClick={() => changeQty(i.id, 1)} className="w-7 h-7" style={{ border: `1px solid ${COLORS.line}` }}>+</button>
              </div>
              <div style={{ fontFamily: "'Inter', sans-serif", color: COLORS.ink, width: 60, textAlign: "right" }} className="font-semibold">${(i.price * i.qty).toFixed(0)}</div>
              <button onClick={() => remove(i.id)} style={{ color: COLORS.mute }} aria-label={`Remove ${i.name}`}>&#10005;</button>
            </div>
          ))}
          <div className="flex justify-between items-center pt-6" style={{ borderTop: `1px solid ${COLORS.line}` }}>
            <span style={{ fontFamily: "'Poppins', sans-serif", color: COLORS.ink }} className="text-xl font-bold">Total: ${total.toFixed(0)}</span>
            <button onClick={() => setPage("Checkout")} className="btn-pop" style={{ fontFamily: "'Inter', sans-serif", background: COLORS.primary, color: "#fff" }}>
              <span className="px-8 py-3 rounded-sm block">Checkout</span>
            </button>
          </div>
        </div>
      )}
    </div>
  );
}

const STEP_LABELS = ["Shipping", "Payment", "Review"];

function StepIndicator({ step }) {
  return (
    <div className="flex items-center gap-3 mb-10">
      {STEP_LABELS.map((label, idx) => {
        const n = idx + 1;
        const active = step === n;
        const done = step > n;
        return (
          <React.Fragment key={label}>
            <div className="flex items-center gap-2">
              <div className="step-dot flex items-center justify-center rounded-full" style={{ width: 28, height: 28, fontSize: 13, background: done ? COLORS.success : active ? COLORS.primary : COLORS.line, color: done || active ? "#fff" : COLORS.mute, fontFamily: "'Inter', sans-serif", transform: active ? "scale(1.1)" : "scale(1)" }}>
                {done ? "\u2713" : n}
              </div>
              <span style={{ fontFamily: "'Inter', sans-serif", fontSize: 13, color: active ? COLORS.ink : COLORS.mute, fontWeight: active ? 600 : 400 }}>{label}</span>
            </div>
            {idx < STEP_LABELS.length - 1 && <div style={{ flex: 1, height: 1, background: done ? COLORS.success : COLORS.line, transition: "background .3s ease" }} />}
          </React.Fragment>
        );
      })}
    </div>
  );
}

function CheckoutPage({ cart, setCart, setPage }) {
  const [step, setStep] = useState(1);
  const [placing, setPlacing] = useState(false);
  const [orderNumber, setOrderNumber] = useState(null);
  const [shipping, setShipping] = useState({ name: "", address: "", city: "", phone: "", email: "" });
  const [payment, setPayment] = useState({ cardName: "", cardNumber: "", expiry: "", cvv: "" });

  const total = cart.reduce((s, i) => s + i.price * i.qty, 0);
  const shippingFee = total > 0 && total < 40 ? 5 : 0;
  const grandTotal = total + shippingFee;

  const shippingValid = shipping.name && shipping.address && shipping.city && shipping.phone && shipping.email;
  const paymentValid = payment.cardName && payment.cardNumber.replace(/\s/g, "").length >= 12 && payment.expiry && payment.cvv.length >= 3;

  const placeOrder = () => {
    setPlacing(true);
    setTimeout(() => {
      setOrderNumber(`VM-${Date.now().toString().slice(-6)}`);
      setPlacing(false);
      setCart([]);
    }, 1400);
  };

  if (cart.length === 0 && !orderNumber) {
    return (
      <div className="max-w-3xl mx-auto px-6 py-20 text-center page-fade">
        <p style={{ fontFamily: "'Inter', sans-serif", color: COLORS.mute }}>Your cart is empty, so there's nothing to check out.</p>
        <button onClick={() => setPage("Home")} className="mt-4 underline" style={{ fontFamily: "'Inter', sans-serif", color: COLORS.primary }}>Browse products</button>
      </div>
    );
  }

  if (orderNumber) {
    const eta = new Date();
    eta.setDate(eta.getDate() + 5);
    return (
      <div className="max-w-2xl mx-auto px-6 py-24 text-center page-fade">
        <Reveal>
          <div className="flex flex-col items-center gap-4">
            <div style={{ width: 64, height: 64, borderRadius: "50%", background: COLORS.success, color: "#fff", fontSize: 28 }} className="flex items-center justify-center">&#10003;</div>
            <h1 style={{ fontFamily: "'Poppins', sans-serif", color: COLORS.ink }} className="text-2xl font-bold">Order confirmed</h1>
            <p style={{ fontFamily: "'Inter', sans-serif", color: COLORS.mute }}>
              Order <strong style={{ color: COLORS.ink }}>{orderNumber}</strong> is being prepared.
              Estimated delivery <strong style={{ color: COLORS.ink }}>{eta.toDateString()}</strong>.
            </p>
            <p style={{ fontFamily: "'Inter', sans-serif", color: COLORS.mute, fontSize: 13 }}>A confirmation would normally be emailed to {shipping.email}.</p>
            <button onClick={() => { setOrderNumber(null); setStep(1); setPage("Home"); }} className="btn-pop mt-4" style={{ fontFamily: "'Inter', sans-serif", background: COLORS.primary, color: "#fff" }}>
              <span className="px-6 py-3 rounded-sm block">Continue shopping</span>
            </button>
          </div>
        </Reveal>
      </div>
    );
  }

  const inputStyle = { fontFamily: "'Inter', sans-serif", border: `1px solid ${COLORS.line}`, borderRadius: 4, padding: "10px 12px", width: "100%", outline: "none" };
  const labelStyle = { fontFamily: "'Inter', sans-serif", color: COLORS.mute, fontSize: 12, marginBottom: 4, display: "block" };

  return (
    <div className="max-w-5xl mx-auto px-6 py-14 page-fade">
      <h1 style={{ fontFamily: "'Poppins', sans-serif", color: COLORS.ink }} className="text-3xl font-bold mb-8">Checkout</h1>
      <StepIndicator step={step} />

      <div className="grid grid-cols-1 md:grid-cols-3 gap-10">
        <div className="md:col-span-2">
          {step === 1 && (
            <div className="fade-swap flex flex-col gap-4">
              <h2 style={{ fontFamily: "'Poppins', sans-serif", color: COLORS.ink }} className="text-xl font-bold mb-1">Shipping details</h2>
              <div><label style={labelStyle}>Full name</label><input style={inputStyle} value={shipping.name} onChange={(e) => setShipping({ ...shipping, name: e.target.value })} placeholder="Your name" /></div>
              <div><label style={labelStyle}>Address</label><input style={inputStyle} value={shipping.address} onChange={(e) => setShipping({ ...shipping, address: e.target.value })} placeholder="Street address" /></div>
              <div className="grid grid-cols-2 gap-4">
                <div><label style={labelStyle}>City</label><input style={inputStyle} value={shipping.city} onChange={(e) => setShipping({ ...shipping, city: e.target.value })} placeholder="City" /></div>
                <div><label style={labelStyle}>Phone</label><input style={inputStyle} value={shipping.phone} onChange={(e) => setShipping({ ...shipping, phone: e.target.value })} placeholder="Phone number" /></div>
              </div>
              <div><label style={labelStyle}>Email</label><input style={inputStyle} value={shipping.email} onChange={(e) => setShipping({ ...shipping, email: e.target.value })} placeholder="you@email.com" /></div>
              <button disabled={!shippingValid} onClick={() => setStep(2)} className="btn-pop mt-2" style={{ fontFamily: "'Inter', sans-serif", background: shippingValid ? COLORS.primary : COLORS.line, color: shippingValid ? "#fff" : COLORS.mute, cursor: shippingValid ? "pointer" : "not-allowed", alignSelf: "flex-start" }}>
                <span className="px-6 py-3 rounded-sm block">Continue to payment</span>
              </button>
            </div>
          )}

          {step === 2 && (
            <div className="fade-swap flex flex-col gap-4">
              <h2 style={{ fontFamily: "'Poppins', sans-serif", color: COLORS.ink }} className="text-xl font-bold mb-1">Payment</h2>
              <div><label style={labelStyle}>Name on card</label><input style={inputStyle} value={payment.cardName} onChange={(e) => setPayment({ ...payment, cardName: e.target.value })} placeholder="Name on card" /></div>
              <div><label style={labelStyle}>Card number</label><input style={inputStyle} value={payment.cardNumber} onChange={(e) => setPayment({ ...payment, cardNumber: e.target.value })} placeholder="1234 5678 9012 3456" /></div>
              <div className="grid grid-cols-2 gap-4">
                <div><label style={labelStyle}>Expiry</label><input style={inputStyle} value={payment.expiry} onChange={(e) => setPayment({ ...payment, expiry: e.target.value })} placeholder="MM/YY" /></div>
                <div><label style={labelStyle}>CVV</label><input style={inputStyle} value={payment.cvv} onChange={(e) => setPayment({ ...payment, cvv: e.target.value })} placeholder="123" /></div>
              </div>
              <p style={{ fontFamily: "'Inter', sans-serif", color: COLORS.mute, fontSize: 12 }}>This is a demo checkout &mdash; no real payment is processed.</p>
              <div className="flex gap-3 mt-2">
                <button onClick={() => setStep(1)} style={{ fontFamily: "'Inter', sans-serif", color: COLORS.ink, border: `1px solid ${COLORS.line}` }} className="px-6 py-3 rounded-sm">Back</button>
                <button disabled={!paymentValid} onClick={() => setStep(3)} className="btn-pop" style={{ fontFamily: "'Inter', sans-serif", background: paymentValid ? COLORS.primary : COLORS.line, color: paymentValid ? "#fff" : COLORS.mute, cursor: paymentValid ? "pointer" : "not-allowed" }}>
                  <span className="px-6 py-3 rounded-sm block">Review order</span>
                </button>
              </div>
            </div>
          )}

          {step === 3 && (
            <div className="fade-swap flex flex-col gap-5">
              <h2 style={{ fontFamily: "'Poppins', sans-serif", color: COLORS.ink }} className="text-xl font-bold mb-1">Review &amp; place order</h2>
              <div className="p-4" style={{ border: `1px solid ${COLORS.line}`, borderRadius: 6 }}>
                <div style={{ fontFamily: "'Inter', sans-serif", fontSize: 13, color: COLORS.mute }} className="mb-1">Shipping to</div>
                <div style={{ fontFamily: "'Inter', sans-serif", color: COLORS.ink }}>{shipping.name}, {shipping.address}, {shipping.city}</div>
                <div style={{ fontFamily: "'Inter', sans-serif", color: COLORS.mute, fontSize: 13 }}>{shipping.phone} &middot; {shipping.email}</div>
              </div>
              <div className="p-4" style={{ border: `1px solid ${COLORS.line}`, borderRadius: 6 }}>
                <div style={{ fontFamily: "'Inter', sans-serif", fontSize: 13, color: COLORS.mute }} className="mb-1">Payment</div>
                <div style={{ fontFamily: "'Inter', sans-serif", color: COLORS.ink }}>Card ending {payment.cardNumber.replace(/\s/g, "").slice(-4)}</div>
              </div>
              <div className="flex gap-3 mt-2">
                <button onClick={() => setStep(2)} style={{ fontFamily: "'Inter', sans-serif", color: COLORS.ink, border: `1px solid ${COLORS.line}` }} className="px-6 py-3 rounded-sm">Back</button>
                <button onClick={placeOrder} disabled={placing} className="btn-pop flex items-center gap-2" style={{ fontFamily: "'Inter', sans-serif", background: COLORS.primary, color: "#fff" }}>
                  <span className="px-6 py-3 rounded-sm flex items-center gap-2">
                    {placing && <span className="spinner" style={{ width: 14, height: 14, border: "2px solid rgba(255,255,255,0.4)", borderTopColor: "#fff", borderRadius: "50%", display: "inline-block" }} />}
                    {placing ? "Placing order..." : "Place order"}
                  </span>
                </button>
              </div>
            </div>
          )}
        </div>

        <div>
          <div className="p-5" style={{ border: `1px solid ${COLORS.line}`, borderRadius: 6, background: COLORS.cream }}>
            <h3 style={{ fontFamily: "'Poppins', sans-serif", color: COLORS.ink }} className="text-base font-bold mb-3">Order summary</h3>
            <div className="flex flex-col gap-2 mb-3">
              {cart.map((i) => (
                <div key={i.id} className="flex justify-between" style={{ fontFamily: "'Inter', sans-serif", fontSize: 13, color: COLORS.ink }}>
                  <span>{i.name} &times; {i.qty}</span><span>${(i.price * i.qty).toFixed(0)}</span>
                </div>
              ))}
            </div>
            <div className="flex justify-between pt-2" style={{ borderTop: `1px solid ${COLORS.line}`, fontFamily: "'Inter', sans-serif", fontSize: 13, color: COLORS.mute }}>
              <span>Shipping</span><span>{shippingFee === 0 ? "Free" : `$${shippingFee}`}</span>
            </div>
            <div className="flex justify-between pt-2 mt-1" style={{ borderTop: `1px solid ${COLORS.line}`, fontFamily: "'Poppins', sans-serif", color: COLORS.ink }}>
              <span className="font-bold">Total</span><span className="font-bold">${grandTotal.toFixed(0)}</span>
            </div>
          </div>
        </div>
      </div>
    </div>
  );
}

function AboutPage() {
  return (
    <div className="page-fade">
      <div style={{ background: `linear-gradient(135deg, ${COLORS.soft} 0%, ${COLORS.cream} 100%)` }}>
        <Reveal>
          <div className="max-w-4xl mx-auto px-6 py-16">
            <h1 style={{ fontFamily: "'Poppins', sans-serif", color: COLORS.ink }} className="text-3xl font-bold mb-4">Our story</h1>
            <p style={{ fontFamily: "'Inter', sans-serif", color: COLORS.mute }} className="leading-relaxed">
              Vertex Mart started with a simple idea: one trustworthy place to shop for everything from
              electronics and office gear to craft supplies and seasonal essentials, without hopping between
              a dozen different stores.
            </p>
          </div>
        </Reveal>
      </div>
      <div className="max-w-4xl mx-auto px-6 py-16 grid grid-cols-1 md:grid-cols-3 gap-8">
        {[
          { t: "Wide selection", d: "New categories added regularly, based on season and demand.", c: catColors.Electronics },
          { t: "Checked quality", d: "Every product reviewed before it's listed for sale.", c: catColors.Office },
          { t: "Fast delivery", d: "Reliable shipping windows shown on every product page.", c: catColors.Crafts },
        ].map((v, idx) => (
          <Reveal key={v.t} delay={idx * 100}>
            <div className="flex flex-col gap-2">
              <Swatch color={v.c} />
              <h3 style={{ fontFamily: "'Poppins', sans-serif", color: COLORS.ink }} className="text-lg font-bold">{v.t}</h3>
              <p style={{ fontFamily: "'Inter', sans-serif", color: COLORS.mute, fontSize: 14 }}>{v.d}</p>
            </div>
          </Reveal>
        ))}
      </div>
    </div>
  );
}

function Footer() {
  return (
    <div style={{ borderTop: `1px solid ${COLORS.line}` }} className="mt-10">
      <div className="max-w-6xl mx-auto px-6 py-10 flex flex-col md:flex-row justify-between items-start md:items-center gap-4">
        <Logo />
        <span style={{ fontFamily: "'Inter', sans-serif", color: COLORS.mute, fontSize: 13 }}>&copy; {new Date().getFullYear()} Vertex Mart. All rights reserved.</span>
      </div>
    </div>
  );
}

export default function App() {
  const [page, setPage] = useState("Home");
  const [menuOpen, setMenuOpen] = useState(false);
  const [cart, setCart] = useState([]);
  const [selectedProduct, setSelectedProduct] = useState(null);
  const [cartBump, setCartBump] = useState(false);
  const [shopCategory, setShopCategory] = useState("Electronics");
  const [searchOpen, setSearchOpen] = useState(false);
  const [searchDraft, setSearchDraft] = useState("");
  const [activeSearch, setActiveSearch] = useState("");

  const onAdd = (p) => {
    setCart((prev) => {
      const existing = prev.find((i) => i.id === p.id);
      if (existing) return prev.map((i) => (i.id === p.id ? { ...i, qty: i.qty + 1 } : i));
      return [...prev, { ...p, qty: 1 }];
    });
    setCartBump(true);
    setTimeout(() => setCartBump(false), 500);
  };

  const onOpen = (p) => {
    setSelectedProduct(p);
    setPage("Product");
    window.scrollTo({ top: 0, behavior: "smooth" });
  };

  const goToShop = (cat) => {
    setActiveSearch("");
    setShopCategory(cat);
    setPage("Shop");
  };

  const onSearchSubmit = () => {
    setActiveSearch(searchDraft);
    setPage("Shop");
    setSearchOpen(false);
  };

  const clearSearch = () => {
    setActiveSearch("");
    setSearchDraft("");
  };

  const goSetPage = (p) => {
    setActiveSearch("");
    setPage(p);
  };

  const cartCount = cart.reduce((s, i) => s + i.qty, 0);

  return (
    <div style={{ background: COLORS.bg, minHeight: "100vh" }}>
      <style>{GLOBAL_STYLES}</style>
      <NavBar
        page={page}
        setPage={goSetPage}
        cartCount={cartCount}
        cartBump={cartBump}
        onOpenMenu={() => setMenuOpen(true)}
        searchOpen={searchOpen}
        setSearchOpen={setSearchOpen}
        searchTerm={searchDraft}
        setSearchTerm={setSearchDraft}
        onSearchSubmit={onSearchSubmit}
      />
      <SlideMenu open={menuOpen} onClose={() => setMenuOpen(false)} page={page} setPage={goSetPage} cartCount={cartCount} goToShop={goToShop} />

      <div key={page}>
        {page === "Home" && <HomePage setPage={goSetPage} onAdd={onAdd} onOpen={onOpen} goToShop={goToShop} />}
        {page === "Shop" && <ShopPage onAdd={onAdd} onOpen={onOpen} category={shopCategory} setCategory={setShopCategory} searchTerm={activeSearch} clearSearch={clearSearch} />}
        {page === "Product" && <ProductDetailPage product={selectedProduct} onAdd={onAdd} setPage={goSetPage} onOpen={onOpen} />}
        {page === "Cart" && <CartPage cart={cart} setCart={setCart} setPage={goSetPage} />}
        {page === "Checkout" && <CheckoutPage cart={cart} setCart={setCart} setPage={goSetPage} />}
        {page === "About" && <AboutPage />}
      </div>
      <Footer />
    </div>
  );
}
