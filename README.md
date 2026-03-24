<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Treino Semanal</title>
    <style>
        :root { --primary: #2ecc71; --bg: #121212; --card: #1e1e1e; --text: #ffffff; }
        body { font-family: 'Segoe UI', sans-serif; background: var(--bg); color: var(--text); margin: 0; padding: 0; }
        
        /* Barra de Navegação Superior */
        .navbar { background: #1a1a1a; padding: 10px; position: sticky; top: 0; z-index: 1000; border-bottom: 2px solid var(--primary); display: flex; overflow-x: auto; gap: 10px; scrollbar-width: none; }
        .navbar::-webkit-scrollbar { display: none; }
        
        .nav-btn { background: #333; color: #bbb; border: none; padding: 8px 15px; border-radius: 20px; font-size: 0.85rem; font-weight: bold; cursor: pointer; white-space: nowrap; transition: 0.3s; }
        .nav-btn.active { background: var(--primary); color: #000; }

        .container { padding: 20px; }
        h1 { text-align: center; color: var(--primary); font-size: 1.2rem; margin-bottom: 20px; }
        
        .dia-content { display: none; animation: fadeIn 0.4s ease; }
        .dia-content.active { display: block; }

        .card { background: var(--card); border-radius: 15px; padding: 15px; box-shadow: 0 4px 15px rgba(0,0,0,0.5); }
        .img-container { width: 100%; height: 180px; border-radius: 10px; overflow: hidden; margin-bottom: 15px; }
        .img-container img { width: 100%; height: 100%; object-fit: cover; }
        
        ul { list-style: none; padding: 0; }
        li { padding: 15px 0; border-bottom: 1px solid #2a2a2a; display: flex; align-items: center; }
        input[type="checkbox"] { width: 22px; height: 22px; margin-right: 15px; accent-color: var(--primary); }
        
        .btn-reset { display: block; width: 100%; padding: 15px; background: #333; color: #ff7675; border: 1px solid #444; border-radius: 10px; font-weight: bold; margin-top: 20px; cursor: pointer; }

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
        <h1>🏋️ MEU TREINO DO DIA</h1>

        <div id="segunda" class="dia-content active">
            <div class="card">
                <div class="img-container"><img src="https://images.unsplash.com/photo-1574680096145-d05b474e2158?w=500"></div>
                <h2>Segunda: Quadríceps</h2>
                <ul>
                    <li><input type="checkbox"> Leg Press 45°</li>
                    <li><input type="checkbox"> Cadeira Extensora</li>
                    <li><input type="checkbox"> Afundo com Halteres</li>
                    <li><input type="checkbox"> Cadeira Abdutora</li>
                </ul>
            </div>
        </div>

        <div id="terca" class="dia-content">
            <div class="card" style="border-top: 4px solid #3498db;">
                <div class="img-container"><img src="https://images.unsplash.com/photo-1581009146145-b5ef03a7403f?w=500"></div>
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
            <div class="card" style="border-top: 4px solid #8e44ad;">
                <div class="img-container"><img src="https://images.unsplash.com/photo-1517836357463-d25dfeac3438?w=500"></div>
                <h2>Quarta: Core</h2>
                <ul>
                    <li><input type="checkbox"> Prancha Frontal (3x 60s)</li>
                    <li><input type="checkbox"> Prancha Lateral</li>
                    <li><input type="checkbox"> Deadbug</li>
                    <li><input type="checkbox"> Caminhada (30 min)</li>
                </ul>
            </div>
        </div>

        <div id="quinta" class="dia-content">
            <div class="card" style="border-top: 4px solid #f39c12;">
                <div class="img-container"><img src="https://images.unsplash.com/photo-1534438327276-14e5300c3a48?w=500"></div>
                <h2>Quinta: Posterior</h2>
                <ul>
                    <li><input type="checkbox"> Mesa Flexora</li>
                    <li><input type="checkbox"> Elevação Pélvica</li>
                    <li><input type="checkbox"> Panturrilha Sentado</li>
                </ul>
            </div>
        </div>

        <div id="sexta" class="dia-content">
            <div class="card" style="border-top: 4px solid #c0392b;">
                <div class="img-container"><img src="https://images.unsplash.com/photo-1605296867304-46d5465a13f1?w=500"></div>
                <h2>Sexta: Costas e Bíceps</h2>
                <ul>
                    <li><input type="checkbox"> Puxada Alta</li>
                    <li><input type="checkbox"> Remada Baixa Sentada</li>
                    <li><input type="checkbox"> Rosca 45°</li>
                    <li><input type="checkbox"> Rosca Martelo</li>
                </ul>
            </div>
        </div>

        <button class="btn-reset" onclick="resetar()">LIMPAR TUDO</button>
    </div>

    <script>
        function mostrarDia(diaId, btn) {
            // Esconde todos os conteúdos
            document.querySelectorAll('.dia-content').forEach(el => el.classList.remove('active'));
            // Remove classe 'active' de todos os botões
            document.querySelectorAll('.nav-btn').forEach(b => b.classList.remove('active'));
            
            // Mostra o selecionado
            document.getElementById(diaId).classList.add('active');
            btn.classList.add('active');
        }

        function resetar() {
            if(confirm("Limpar todos os exercícios marcados?")) {
                document.querySelectorAll('input[type="checkbox"]').forEach(c => c.checked = false);
            }
        }
    </script>
</body>
</html>
        .img-container { width: 100%; height: 150px; border-radius: 8px; overflow: hidden; margin-bottom: 12px; background: #2a2a2a; }
        .img-container img { width: 100%; height: 100%; object-fit: cover; opacity: 0.8; }
        
        ul { list-style: none; padding: 0; }
        li { padding: 12px 0; border-bottom: 1px solid #2a2a2a; display: flex; align-items: center; font-size: 0.95rem; }
        input[type="checkbox"] { width: 20px; height: 20px; margin-right: 15px; accent-color: var(--primary); cursor: pointer; }
        
        .btn-reset { display: block; width: 100%; padding: 15px; background: #e74c3c; color: white; border: none; border-radius: 8px; font-weight: bold; font-size: 1rem; cursor: pointer; margin-top: 10px; }
        .footer { text-align: center; font-size: 0.75rem; color: #777; margin: 30px 0; line-height: 1.4; }
    </style>
</head>
<body>

    <h1>💪 Treino Coluna Saudável</h1>

    <div class="dia">
        <h2>Segunda: Quadríceps e Glúteos</h2>
        <div class="img-container">
            <img src="https://images.unsplash.com/photo-1574680096145-d05b474e2158?auto=format&fit=crop&w=500&q=80" alt="Treino de pernas">
        </div>
        <ul>
            <li><input type="checkbox"> Leg Press 45°</li>
            <li><input type="checkbox"> Cadeira Extensora</li>
            <li><input type="checkbox"> Afundo com Halteres</li>
            <li><input type="checkbox"> Cadeira Abdutora</li>
        </ul>
    </div>

    <div class="dia" style="border-top-color: #3498db;">
        <h2>Terça: Peito e Tríceps</h2>
        <div class="img-container">
            <img src="https://images.unsplash.com/photo-1581009146145-b5ef03a7403f?auto=format&fit=crop&w=500&q=80" alt="Treino de peito">
        </div>
        <ul>
            <li><input type="checkbox"> Supino c/ Halteres</li>
            <li><input type="checkbox"> Crucifixo Máquina</li>
            <li><input type="checkbox"> Tríceps Corda</li>
            <li><input type="checkbox"> Tríceps Francês Sentado</li>
        </ul>
    </div>

    <div class="dia" style="border-top-color: #8e44ad;">
        <h2>Quarta: Core e Estabilidade</h2>
        <div class="img-container">
            <img src="https://images.unsplash.com/photo-1517836357463-d25dfeac3438?auto=format&fit=crop&w=500&q=80" alt="Treino de core">
        </div>
        <ul>
            <li><input type="checkbox"> Prancha Frontal (3x 60s)</li>
            <li><input type="checkbox"> Prancha Lateral</li>
            <li><input type="checkbox"> Deadbug</li>
            <li><input type="checkbox"> Caminhada Leve (30 min)</li>
        </ul>
    </div>

    <div class="dia" style="border-top-color: #f39c12;">
        <h2>Quinta: Posterior e Panturrilha</h2>
        <div class="img-container">
            <img src="https://images.unsplash.com/photo-1534438327276-14e5300c3a48?auto=format&fit=crop&w=500&q=80" alt="Treino posterior">
        </div>
        <ul>
            <li><input type="checkbox"> Mesa Flexora</li>
            <li><input type="checkbox"> Elevação Pélvica</li>
            <li><input type="checkbox"> Panturrilha Sentado</li>
        </ul>
    </div>

    <div class="dia" style="border-top-color: #c0392b;">
        <h2>Sexta: Costas e Bíceps</h2>
        <div class="img-container">
            <img src="https://images.unsplash.com/photo-1605296867304-46d5465a13f1?auto=format&fit=crop&w=500&q=80" alt="Treino de costas">
        </div>
        <ul>
            <li><input type="checkbox"> Puxada Alta</li>
            <li><input type="checkbox"> Remada Baixa Sentada</li>
            <li><input type="checkbox"> Rosca 45° (Banco apoiado)</li>
            <li><input type="checkbox"> Rosca Martelo</li>
        </ul>
    </div>

    <button class="btn-reset" onclick="resetar()">LIMPAR TREINO DO DIA</button>

    <div class="footer">
        Atenção: Mantenha sempre o abdômen contraído (Bracing) para proteger sua lombar.
    </div>

    <script>
        function resetar() {
            if(confirm("Deseja desmarcar todos os exercícios?")) {
                const checks = document.querySelectorAll('input[type="checkbox"]');
                checks.forEach(c => c.checked = false);
            }
        }
    </script>

</body>
</html>
