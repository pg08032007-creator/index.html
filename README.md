<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
    <title>Treino Mobile</title>
    <style>
        :root { --primary: #2ecc71; --bg: #121212; --card: #1e1e1e; --text: #ffffff; }
        
        * { box-sizing: border-box; } /* Garante que o padding não aumente o tamanho dos elementos */

        body { 
            font-family: 'Segoe UI', sans-serif; 
            background: var(--bg); 
            color: var(--text); 
            margin: 0; 
            padding: 0;
            overflow-x: hidden; /* Evita rolagem lateral */
        }
        
        /* Barra de Navegação Superior compacta */
        .navbar { 
            background: #1a1a1a; 
            padding: 10px 5px; 
            position: sticky; 
            top: 0; 
            z-index: 1000; 
            border-bottom: 2px solid var(--primary); 
            display: flex; 
            justify-content: space-between;
            gap: 4px;
        }
        
        .nav-btn { 
            background: #333; 
            color: #bbb; 
            border: none; 
            padding: 10px 2px; 
            border-radius: 6px; 
            font-size: 0.7rem; 
            font-weight: bold; 
            flex: 1; /* Divide o espaço igualmente */
            cursor: pointer;
        }
        
        .nav-btn.active { background: var(--primary); color: #000; }

        .container { padding: 15px; width: 100%; }
        
        h1 { text-align: center; color: var(--primary); font-size: 1.1rem; margin: 10px 0; }
        
        .dia-content { display: none; width: 100%; }
        .dia-content.active { display: block; animation: fadeIn 0.3s ease; }

        .card { 
            background: var(--card); 
            border-radius: 12px; 
            padding: 15px; 
            width: 100%;
            box-shadow: 0 4px 10px rgba(0,0,0,0.3); 
        }

        .img-container { 
            width: 100%; 
            height: 140px; /* Reduzi a altura para sobrar espaço pro texto */
            border-radius: 8px; 
            overflow: hidden; 
            margin-bottom: 15px; 
            background: #2a2a2a; 
        }
        
        .img-container img { width: 100%; height: 100%; object-fit: cover; }
        
        h2 { margin: 0 0 10px 0; font-size: 1rem; color: var(--primary); line-height: 1.2; }
        
        ul { list-style: none; padding: 0; margin: 0; }
        
        li { 
            padding: 12px 0; 
            border-bottom: 1px solid #2a2a2a; 
            display: flex; 
            align-items: center;
            font-size: 0.9rem; /* Tamanho de fonte melhor para mobile */
        }

        input[type="checkbox"] { 
            min-width: 20px; 
            min-height: 20px; 
            margin-right: 12px; 
            accent-color: var(--primary); 
        }
        
        .btn-reset { 
            display: block; 
            width: 100%; 
            padding: 12px; 
            background: #222; 
            color: #ff7675; 
            border: 1px solid #333; 
            border-radius: 8px; 
            font-size: 0.8rem;
            font-weight: bold; 
            margin-top: 20px; 
        }

        @keyframes fadeIn { from { opacity: 0; } to { opacity: 1; } }
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
                <div class="img-container"><img src="https://images.pexels.com/photos/1552242/pexels-photo-1552242.jpeg?auto=compress&cs=tinysrgb&w=500" alt="Pernas"></div>
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
                <div class="img-container"><img src="https://images.pexels.com/photos/3838389/pexels-photo-3838389.jpeg?auto=compress&cs=tinysrgb&w=500" alt="Peito"></div>
                <h2>Terça: Peito e Tríceps</h2>
                <ul>
                    <li><input type="checkbox"> Supino c/ Halteres</li>
                    <li><input type="checkbox"> Crucifixo Máquina</li>
                    <li><input type="checkbox"> Tríceps Corda</li>
                    <li><input type="checkbox"> Tríceps Francês Sentado</li>
                </ul>
            </div>
        </div>

        <div id="quarta" class="dia-content">
            <div class="card">
                <div class="img-container"><img src="https://images.pexels.com/photos/3760830/pexels-photo-3760830.jpeg?auto=compress&cs=tinysrgb&w=500" alt="Core"></div>
                <h2>Quarta: Core</h2>
                <ul>
                    <li><input type="checkbox"> Prancha Frontal</li>
                    <li><input type="checkbox"> Prancha Lateral</li>
                    <li><input type="checkbox"> Deadbug</li>
                    <li><input type="checkbox"> Caminhada (30 min)</li>
                </ul>
            </div>
        </div>

        <div id="quinta" class="dia-content">
            <div class="card">
                <div class="img-container"><img src="https://images.pexels.com/photos/3775164/pexels-photo-3775164.jpeg?auto=compress&cs=tinysrgb&w=500" alt="Posterior"></div>
                <h2>Quinta: Posterior</h2>
                <ul>
                    <li><input type="checkbox"> Mesa Flexora</li>
                    <li><input type="checkbox"> Elevação Pélvica</li>
                    <li><input type="checkbox"> Panturrilha Sentado</li>
                </ul>
            </div>
        </div>

        <div id="sexta" class="dia-content">
            <div class="card">
                <div class="img-container"><img src="https://images.pexels.com/photos/949126/pexels-photo-949126.jpeg?auto=compress&cs=tinysrgb&w=500" alt="Costas"></div>
                <h2>Sexta: Costas e Bíceps</h2>
                <ul>
                    <li><input type="checkbox"> Puxada Alta</li>
                    <li><input type="checkbox"> Remada Baixa</li>
                    <li><input type="checkbox"> Rosca 45°</li>
                    <li><input type="checkbox"> Rosca Martelo</li>
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
