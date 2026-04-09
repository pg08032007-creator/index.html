<!DOCTYPE html>
<html lang="pt-br">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">

<style>
:root {
    --primary: #2ecc71;
    --bg: #121212;
    --card: #1e1e1e;
    --text: #ffffff;
}

* { box-sizing: border-box; }

body {
    font-family: 'Segoe UI', sans-serif;
    background: var(--bg);
    color: var(--text);
    margin: 0;
    overflow-x: hidden;
}

/* NAVBAR */
.navbar {
    background: #1a1a1a;
    padding: 10px 5px;
    position: sticky;
    top: 0;
    display: flex;
    gap: 4px;
    border-bottom: 2px solid var(--primary);
    z-index: 1000;
}

.nav-btn {
    background: #333;
    color: #bbb;
    border: none;
    padding: 10px 2px;
    border-radius: 6px;
    font-size: 0.7rem;
    font-weight: bold;
    flex: 1;
}

.nav-btn.active {
    background: var(--primary);
    color: #000;
}

/* CONTAINER */
.container {
    padding: 15px;
}

h1 {
    text-align: center;
    color: var(--primary);
    font-size: 1.1rem;
}

/* CARD */
.card {
    background: var(--card);
    border-radius: 12px;
    padding: 15px;
    box-shadow: 0 4px 10px rgba(0,0,0,0.3);
}

.dia-content { display: none; }
.dia-content.active { display: block; }

/* EXERCICIOS */
ul {
    list-style: none;
    padding: 0;
}

li {
    display: flex;
    align-items: center;
    gap: 10px;
    padding: 10px 0;
    border-bottom: 1px solid #2a2a2a;
}

.ex-img {
    width: 55px;
    height: 55px;
    border-radius: 8px;
    object-fit: cover;
}

input[type="checkbox"] {
    min-width: 20px;
    min-height: 20px;
    accent-color: var(--primary);
}

/* BOTAO */
.btn-reset {
    width: 100%;
    padding: 12px;
    margin-top: 20px;
    background: #222;
    color: #ff7675;
    border: 1px solid #333;
    border-radius: 8px;
}

/* ANIMAÇÃO */
li input:checked {
    transform: scale(1.2);
}
</style>
</head>

<body>

<div class="navbar">
    <button class="nav-btn active" onclick="mostrarDia('segunda', this)">SEG</button>
    <button class="nav-btn" onclick="mostrarDia('terca', this)">TER</button>
    <button class="nav-btn" onclick="mostrarDia('quarta', this)">QUA</button>
    <button class="nav-btn" onclick="mostrarDia('quinta', this)">QUI</button>
    <button class="nav-btn" onclick="mostrarDia('sexta', this)">SEX</button>
</div>

<div class="container">
<h1>🏋️ Treino do Dia</h1>

<!-- SEGUNDA -->
<div id="segunda" class="dia-content active">
<div class="card">
<h2>Quadríceps e Glúteos</h2>
<ul>
<li><img class="ex-img" src="https://images.pexels.com/photos/2261477/pexels-photo-2261477.jpeg?auto=compress&w=200"><input type="checkbox"> Leg Press 45°</li>
<li><img class="ex-img" src="https://images.pexels.com/photos/3838386/pexels-photo-3838386.jpeg?auto=compress&w=200"><input type="checkbox"> Cadeira Extensora</li>
<li><img class="ex-img" src="https://images.pexels.com/photos/4162487/pexels-photo-4162487.jpeg?auto=compress&w=200"><input type="checkbox"> Afundo com Halteres</li>
<li><img class="ex-img" src="https://images.pexels.com/photos/4498606/pexels-photo-4498606.jpeg?auto=compress&w=200"><input type="checkbox"> Cadeira Abdutora</li>
</ul>
</div>
</div>

<!-- TERÇA -->
<div id="terca" class="dia-content">
<div class="card">
<h2>Peito e Tríceps</h2>
<ul>
<li><img class="ex-img" src="https://images.pexels.com/photos/3838937/pexels-photo-3838937.jpeg?auto=compress&w=200"><input type="checkbox"> Supino Halteres</li>
<li><img class="ex-img" src="https://images.pexels.com/photos/4164761/pexels-photo-4164761.jpeg?auto=compress&w=200"><input type="checkbox"> Crucifixo</li>
<li><img class="ex-img" src="https://images.pexels.com/photos/4164517/pexels-photo-4164517.jpeg?auto=compress&w=200"><input type="checkbox"> Tríceps Corda</li>
<li><img class="ex-img" src="https://images.pexels.com/photos/4498573/pexels-photo-4498573.jpeg?auto=compress&w=200"><input type="checkbox"> Tríceps Francês</li>
</ul>
</div>
</div>

<!-- QUARTA -->
<div id="quarta" class="dia-content">
<div class="card">
<h2>Core</h2>
<ul>
<li><img class="ex-img" src="https://images.pexels.com/photos/4324022/pexels-photo-4324022.jpeg?auto=compress&w=200"><input type="checkbox"> Prancha Frontal</li>
<li><img class="ex-img" src="https://images.pexels.com/photos/4324025/pexels-photo-4324025.jpeg?auto=compress&w=200"><input type="checkbox"> Prancha Lateral</li>
<li><img class="ex-img" src="https://images.pexels.com/photos/4162583/pexels-photo-4162583.jpeg?auto=compress&w=200"><input type="checkbox"> Deadbug</li>
<li><img class="ex-img" src="https://images.pexels.com/photos/1552249/pexels-photo-1552249.jpeg?auto=compress&w=200"><input type="checkbox"> Caminhada</li>
</ul>
</div>
</div>

<!-- QUINTA -->
<div id="quinta" class="dia-content">
<div class="card">
<h2>Posterior</h2>
<ul>
<li><img class="ex-img" src="https://images.pexels.com/photos/4162451/pexels-photo-4162451.jpeg?auto=compress&w=200"><input type="checkbox"> Mesa Flexora</li>
<li><img class="ex-img" src="https://images.pexels.com/photos/4498604/pexels-photo-4498604.jpeg?auto=compress&w=200"><input type="checkbox"> Elevação Pélvica</li>
<li><img class="ex-img" src="https://images.pexels.com/photos/3837780/pexels-photo-3837780.jpeg?auto=compress&w=200"><input type="checkbox"> Panturrilha</li>
</ul>
</div>
</div>

<!-- SEXTA -->
<div id="sexta" class="dia-content">
<div class="card">
<h2>Costas e Bíceps</h2>
<ul>
<li><img class="ex-img" src="https://images.pexels.com/photos/4162579/pexels-photo-4162579.jpeg?auto=compress&w=200"><input type="checkbox"> Puxada Alta</li>
<li><img class="ex-img" src="https://images.pexels.com/photos/4162581/pexels-photo-4162581.jpeg?auto=compress&w=200"><input type="checkbox"> Remada Baixa</li>
<li><img class="ex-img" src="https://images.pexels.com/photos/4498571/pexels-photo-4498571.jpeg?auto=compress&w=200"><input type="checkbox"> Rosca 45°</li>
<li><img class="ex-img" src="https://images.pexels.com/photos/4164516/pexels-photo-4164516.jpeg?auto=compress&w=200"><input type="checkbox"> Rosca Martelo</li>
</ul>
</div>
</div>

<button class="btn-reset" onclick="resetar()">DESMARCAR TUDO</button>
</div>

<script>
function mostrarDia(diaId, btn) {
    document.querySelectorAll('.dia-content').forEach(el => el.classList.remove('active'));
    document.querySelectorAll('.nav-btn').forEach(b => b.classList.remove('active'));
    document.getElementById(diaId).classList.add('active');
    btn.classList.add('active');
    window.scrollTo({top: 0, behavior: 'smooth'});
}

function resetar() {
    if(confirm("Limpar os exercícios marcados?")) {
        document.querySelectorAll('input[type="checkbox"]').forEach(c => c.checked = false);
    }
}
</script>

</body>
</html>
