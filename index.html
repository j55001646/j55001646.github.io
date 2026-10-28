<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="utf-8">
<meta name="viewport" content="width=device-width, initial-scale=1">
<title>Kanto Pokédex Tiles</title>
<style>
:root{--bg:#14161c;--card:#1f232d;--text:#eef0f5;--muted:#9aa3b5;--accent:#e63946}
*{box-sizing:border-box}
body{margin:0;font-family:system-ui,-apple-system,Segoe UI,Roboto,sans-serif;background:var(--bg);color:var(--text)}
header{position:sticky;top:0;z-index:5;background:rgba(20,22,28,.95);backdrop-filter:blur(6px);padding:12px 16px;border-bottom:1px solid #2c3140;display:flex;flex-wrap:wrap;gap:10px;align-items:center}
h1{font-size:1.2rem;margin:0 auto 0 0}
select,button{font:inherit;padding:8px 14px;border-radius:8px;border:1px solid #3a4154;background:var(--card);color:var(--text);cursor:pointer}
button#reset{background:var(--accent);border-color:var(--accent);font-weight:600}
#count{color:var(--muted);font-size:.9rem}
#grid{display:grid;grid-template-columns:repeat(auto-fill,minmax(150px,1fr));gap:14px;padding:16px;max-width:1400px;margin:0 auto}
.tile{position:relative;background:var(--card);border:2px solid #2c3140;border-radius:14px;padding:10px;text-align:center;color:inherit;display:flex;flex-direction:column;align-items:center;gap:6px;transition:transform .12s,border-color .12s}
.tile:hover{transform:translateY(-2px);border-color:#4a5270}
.tile.gone{display:none}
.num{position:absolute;top:8px;left:10px;font-size:.75rem;color:var(--muted)}
.wild{position:absolute;top:5px;right:8px;font-size:1.1rem}
.wrap{position:relative;width:100px;height:100px;margin-top:10px}
.wrap img{width:100%;height:100%;object-fit:contain;transition:filter .15s}
.tile.crossed .wrap img{filter:brightness(0)}
.tile.crossed .wrap::after{content:"✕";position:absolute;inset:0;display:flex;align-items:center;justify-content:center;font-size:5rem;font-weight:700;color:var(--accent);line-height:1}
.tile.crossed{border-color:var(--accent)}
.name{font-weight:600;font-size:.95rem}
.types{display:flex;gap:4px;flex-wrap:wrap;justify-content:center}
.t{font-size:.7rem;padding:2px 8px;border-radius:99px;color:#fff;font-weight:600;text-shadow:0 1px 1px rgba(0,0,0,.4)}
.empty{grid-column:1/-1;text-align:center;color:var(--muted);padding:40px}
footer{text-align:center;color:var(--muted);font-size:.8rem;padding:16px}
</style>
</head>
<body>
<header>
  <h1>Kanto Pokédex</h1>
  <label>Element:
    <select id="filter"><option value="">All</option></select>
  </label>
  <button id="reset">Reset</button>
  <span id="count"></span>
</header>
<main id="grid"></main>
<footer>🌿 = can be caught in the wild in Kanto (Red/Blue/FireRed/LeafGreen). Gifts, fossils, trades, prizes and evolution-only Pokémon are not marked.</footer>

<script>
const TYPES = {Normal:"#a8a77a",Fire:"#ee8130",Water:"#6390f0",Electric:"#d4a90a",Grass:"#5aa83c",Ice:"#4fb8b8",Fighting:"#c22e28",Poison:"#a33ea1",Ground:"#b8975a",Flying:"#8f7bd6",Psychic:"#f95587",Bug:"#a6b91a",Rock:"#b6a136",Ghost:"#735797",Dragon:"#6f35fc",Steel:"#8a8aa8",Fairy:"#d685ad"};
const A = {No:"Normal",Fi:"Fire",Wa:"Water",El:"Electric",Gr:"Grass",Ic:"Ice",Fg:"Fighting",Po:"Poison",Gd:"Ground",Fl:"Flying",Ps:"Psychic",Bu:"Bug",Ro:"Rock",Gh:"Ghost",Dr:"Dragon",St:"Steel",Fa:"Fairy"};
// Name:Type1,Type2 — in Pokédex order (1–151)
const RAW = `Bulbasaur:Gr,Po|Ivysaur:Gr,Po|Venusaur:Gr,Po|Charmander:Fi|Charmeleon:Fi|Charizard:Fi,Fl|Squirtle:Wa|Wartortle:Wa|Blastoise:Wa|Caterpie:Bu|Metapod:Bu|Butterfree:Bu,Fl|Weedle:Bu,Po|Kakuna:Bu,Po|Beedrill:Bu,Po|Pidgey:No,Fl|Pidgeotto:No,Fl|Pidgeot:No,Fl|Rattata:No|Raticate:No|Spearow:No,Fl|Fearow:No,Fl|Ekans:Po|Arbok:Po|Pikachu:El|Raichu:El|Sandshrew:Gd|Sandslash:Gd|Nidoran♀:Po|Nidorina:Po|Nidoqueen:Po,Gd|Nidoran♂:Po|Nidorino:Po|Nidoking:Po,Gd|Clefairy:Fa|Clefable:Fa|Vulpix:Fi|Ninetales:Fi|Jigglypuff:No,Fa|Wigglytuff:No,Fa|Zubat:Po,Fl|Golbat:Po,Fl|Oddish:Gr,Po|Gloom:Gr,Po|Vileplume:Gr,Po|Paras:Bu,Gr|Parasect:Bu,Gr|Venonat:Bu,Po|Venomoth:Bu,Po|Diglett:Gd|Dugtrio:Gd|Meowth:No|Persian:No|Psyduck:Wa|Golduck:Wa|Mankey:Fg|Primeape:Fg|Growlithe:Fi|Arcanine:Fi|Poliwag:Wa|Poliwhirl:Wa|Poliwrath:Wa,Fg|Abra:Ps|Kadabra:Ps|Alakazam:Ps|Machop:Fg|Machoke:Fg|Machamp:Fg|Bellsprout:Gr,Po|Weepinbell:Gr,Po|Victreebel:Gr,Po|Tentacool:Wa,Po|Tentacruel:Wa,Po|Geodude:Ro,Gd|Graveler:Ro,Gd|Golem:Ro,Gd|Ponyta:Fi|Rapidash:Fi|Slowpoke:Wa,Ps|Slowbro:Wa,Ps|Magnemite:El,St|Magneton:El,St|Farfetch'd:No,Fl|Doduo:No,Fl|Dodrio:No,Fl|Seel:Wa|Dewgong:Wa,Ic|Grimer:Po|Muk:Po|Shellder:Wa|Cloyster:Wa,Ic|Gastly:Gh,Po|Haunter:Gh,Po|Gengar:Gh,Po|Onix:Ro,Gd|Drowzee:Ps|Hypno:Ps|Krabby:Wa|Kingler:Wa|Voltorb:El|Electrode:El|Exeggcute:Gr,Ps|Exeggutor:Gr,Ps|Cubone:Gd|Marowak:Gd|Hitmonlee:Fg|Hitmonchan:Fg|Lickitung:No|Koffing:Po|Weezing:Po|Rhyhorn:Gd,Ro|Rhydon:Gd,Ro|Chansey:No|Tangela:Gr|Kangaskhan:No|Horsea:Wa|Seadra:Wa|Goldeen:Wa|Seaking:Wa|Staryu:Wa|Starmie:Wa,Ps|Mr. Mime:Ps,Fa|Scyther:Bu,Fl|Jynx:Ic,Ps|Electabuzz:El|Magmar:Fi|Pinsir:Bu|Tauros:No|Magikarp:Wa|Gyarados:Wa,Fl|Lapras:Wa,Ic|Ditto:No|Eevee:No|Vaporeon:Wa|Jolteon:El|Flareon:Fi|Porygon:No|Omanyte:Ro,Wa|Omastar:Ro,Wa|Kabuto:Ro,Wa|Kabutops:Ro,Wa|Aerodactyl:Ro,Fl|Snorlax:No|Articuno:Ic,Fl|Zapdos:El,Fl|Moltres:Fi,Fl|Dratini:Dr|Dragonair:Dr|Dragonite:Dr,Fl|Mewtwo:Ps|Mew:Ps`;
// Not catchable in the wild: starters & evolutions, gifts, fossils, trades, prizes, evolution-only
const NOT_WILD = new Set([1,2,3,4,5,6,7,8,9,12,15,18,26,31,34,36,38,59,62,65,68,71,76,78,83,91,94,103,106,107,121,122,124,131,133,134,135,136,137,138,139,140,141,142,149,151]);

const IMG = id => `https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/other/official-artwork/${id}.png`;
const grid = document.getElementById('grid'), filter = document.getElementById('filter'), count = document.getElementById('count');

const mons = RAW.split('|').map((s,i) => {
  const [name, t] = s.split(':');
  return {id:i+1, name, types:t.split(',').map(c => A[c])};
});

Object.keys(TYPES).forEach(t => filter.add(new Option(t, t)));

mons.forEach(m => {
  const b = document.createElement('button');
  b.className = 'tile';
  b.dataset.types = m.types.join(',');
  b.setAttribute('aria-pressed','false');
  b.title = 'Click to black out / reveal';
  b.innerHTML = `
    <span class="num">#${String(m.id).padStart(3,'0')}</span>
    ${NOT_WILD.has(m.id) ? '' : '<span class="wild" title="Found in the wild">🌿</span>'}
    <div class="wrap"><img src="${IMG(m.id)}" alt="${m.name}" loading="lazy"></div>
    <span class="name">${m.name}</span>
    <span class="types">${m.types.map(t => `<span class="t" style="background:${TYPES[t]}">${t}</span>`).join('')}</span>`;
  b.onclick = () => {
    const on = b.classList.toggle('crossed');
    b.setAttribute('aria-pressed', on);
    update();
  };
  grid.appendChild(b);
});

function update(){
  const f = filter.value;
  let shown = 0, crossed = 0;
  grid.querySelectorAll('.tile').forEach(t => {
    const ok = !f || t.dataset.types.split(',').includes(f);
    t.classList.toggle('gone', !ok);
    if (ok) { shown++; if (t.classList.contains('crossed')) crossed++; }
  });
  count.textContent = `Showing ${shown} • ${crossed} blacked out`;
}
filter.onchange = update;
document.getElementById('reset').onclick = () => {
  filter.value = '';
  grid.querySelectorAll('.tile').forEach(t => { t.classList.remove('crossed'); t.setAttribute('aria-pressed','false'); });
  update();
  scrollTo({top:0, behavior:'smooth'});
};
update();
</script>
</body>
</html>
