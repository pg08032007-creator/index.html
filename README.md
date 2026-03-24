<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Meu Treino Seguro</title>
    <style>
        :root { --primary: #2ecc71; --bg: #121212; --card: #1e1e1e; --text: #ffffff; }
        body { font-family: 'Segoe UI', sans-serif; background: var(--bg); color: var(--text); margin: 0; padding: 15px; }
        h1 { text-align: center; color: var(--primary); font-size: 1.4rem; margin-bottom: 20px; }
        
        .dia { background: var(--card); border-radius: 12px; padding: 15px; margin-bottom: 25px; border-top: 4px solid var(--primary); shadow: 0 4px 10px rgba(0,0,0,0.3); }
        h2 { margin: 0 0 10px 0; color: var(--primary); font-size: 1.1rem; text-transform: uppercase; }
        
        /* Estilo das Imagens */
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
