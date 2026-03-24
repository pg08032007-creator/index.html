<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Treino Semanal</title>
    <style>
        :root { --primary: #2ecc71; --bg: #121212; --card: #1e1e1e; --text: #ffffff; }
        body { font-family: 'Segoe UI', sans-serif; background: var(--bg); color: var(--text); margin: 0; padding: 0; }
        
        /* Barra de Navegação Superior Fixa */
        .navbar { 
            background: #1a1a1a; 
            padding: 15px 10px; 
            position: sticky; 
            top: 0; 
            z-index: 1000; 
            border-bottom: 2px solid var(--primary); 
            display: flex; 
            justify-content: space-around;
            gap: 5px;
        }
        
        .nav-btn { 
            background: #333; 
            color: #bbb; 
            border: none; 
            padding: 10px 12px; 
            border-radius: 8px; 
            font-size: 0.75rem; 
            font-weight: bold; 
            cursor: pointer; 
            flex: 1;
            transition: 0.3s; 
        }
        
        .nav-btn.active { background: var(--primary); color: #000; }

        .container { padding: 20px; }
        h1 { text-align: center; color: var(--primary); font-size: 1.2rem; margin-bottom: 20px; }
        
        /* Controle de Exibição dos Dias */
        .dia-content { display: none; animation: fadeIn 0.4s ease; }
        .dia-content.active { display: block; }

        .card { background: var(--card); border-radius: 15px; padding: 15px; box-shadow: 0 4px 15px rgba(0,0,0,0.5); }
        .img-container { width: 100%; height: 180px; border-radius: 10px; overflow: hidden; margin-bottom: 15px; background: #2a2a2a; }
        .img-container img { width: 100%; height: 100%; object-fit: cover; opacity: 0.9; }
        
        h2 { margin: 0 0 15px 0; font-size: 1.1rem; color: var(--primary); border-bottom: 1px solid #333; padding-bottom: 10px; }
        
        ul { list-style: none; padding: 0; }
        li { padding: 15px 0; border-bottom: 1px solid #2a2a2a; display: flex; align-items: center; }
        input[type="checkbox"] { width: 22px; height: 22px; margin-right: 15px; accent-color: var(--primary); cursor: pointer; }
        
        .btn-reset { display: block; width: 100%; padding: 15px; background: #333; color: #ff7675; border: 1px solid #444; border-radius: 10px; font-weight: bold; margin-top: 30px; cursor: pointer; }

        @keyframes fadeIn { from { opacity: 0; transform: translateY(10px); } to { opacity: 1; transform: translateY(0); } }
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

        <div id="segunda" class="dia-content active">
            <div class="card">
                <div class="img-container"><img src="https://images.unsplash.com/photo-1574680096145-d05b474e2158?w=500"></div>
                <h2>Segunda: Quadríceps e Glúteos</h2>
                <ul>
                    <li><input type="checkbox"> Leg Press 45°</li>
                    <li><input type="checkbox"> Cadeira Extensora</li>
                    <li><input type="checkbox"> Afundo com Halteres</li>
                    <li><input type="checkbox"> Cadeira Abdutora</li>
                </ul>
            </div>
        </div>

        <div id="terca" class="dia-content">
            <div class="card">
                <div class="img-container"><img src="https://images.unsplash.com/photo-1581009146145-b5ef03a7403f?w=500"></div>
                <h2>Terça: Peito e Tríceps</h2>
                <ul>
                    <li><input type="checkbox"> Supino c/ Halteres (Sentado)</li>
                    <li><input type="checkbox"> Crucifixo Máquina</li>
                    <li><input type="checkbox"> Tríceps Corda</li>
                    <li><input type="checkbox"> Tríceps Francês Sentado</li>
                </ul>
            </div>
        </div>

        <div id="quarta" class="dia-content">
            <div class="card">
                <div class="img-container"><img src="https://images.unsplash.com/photo-1517836357463-d25dfeac3438?w=500"></div>
                <h2>Quarta: Core e Estabilidade</h2>
                <ul>
                    <li><input type="checkbox"> Prancha Frontal (3x 60s)</li>
                    <li><input type="checkbox"> Prancha Lateral</li>
                    <li><input type="checkbox"> Deadbug (Lombar no chão)</li>
                    <li><input type="checkbox"> Caminhada (30 min)</li>
                </ul>
            </div>
        </div>

        <div id="quinta" class="dia-content">
            <div class="card">
                <div class="img-container"><img src="https://images.unsplash.com/photo-1534438327276-14e5300c3a48?w=500"></div>
                <h2>Quinta: Posterior e Panturrilha</h2>
                <ul>
                    <li><input type="checkbox"> Mesa Flexora</li>
                    <li><input type="checkbox"> Elevação Pélvica</li>
                    <li><input type="checkbox"> Panturrilha Sentado</li>
                </ul>
            </div>
        </div>

        <div id="sexta" class="dia-content">
            <div class="card">
                <div class="img-container"><img src="https://images.unsplash.com/photo-1605296867304-46d5465a13f1?w=500"></div>
                <h2>Sexta: Costas e Bíceps</h2>
                <ul>
                    <li><input type="checkbox"> Puxada Alta</li>
                    <li><input type="checkbox"> Remada Baixa Sentada</li>
                    <li><input type="checkbox"> Rosca 45° (Bíceps)</li>
                    <li><input type="checkbox"> Rosca Martelo</li>
                </ul>
            </div>
        </div>

        <button class="btn-reset" onclick="resetar()">DESMARCAR TUDO</button>
    </div>

    <script>
        // Função para trocar o dia exibido
        function mostrarDia(diaId, btn) {
            // Esconde todos
            document.querySelectorAll('.dia-content').forEach(el => el.classList.remove('active'));
            // Desativa botões
            document.querySelectorAll('.nav-btn').forEach(b => b.classList.remove('active'));
            
            // Ativa o dia e o botão clicado
            document.getElementById(diaId).classList.add('active');
            btn.classList.add('active');
            
            // Rola para o topo suavemente
            window.scrollTo({top: 0, behavior: 'smooth'});
        }

        // Função para limpar os checks
        function resetar() {
            if(confirm("Limpar os exercícios marcados?")) {
                document.querySelectorAll('input[type="checkbox"]').forEach(c => c.checked = false);
            }
        }
    </script>
</body>
</html>
