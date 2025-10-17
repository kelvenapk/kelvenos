<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Kelvena - Dev Fullstack</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            background: linear-gradient(135deg, #0f0c29, #302b63, #24243e);
            color: #e0e0e0;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            line-height: 1.6;
            overflow-x: hidden;
        }

        /* Animação de fundo */
        @keyframes gradientShift {
            0%, 100% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
        }

        body {
            background: linear-gradient(-45deg, #0f0c29, #302b63, #24243e, #9D4EDD);
            background-size: 400% 400%;
            animation: gradientShift 15s ease infinite;
        }

        /* Partículas flutuantes */
        @keyframes float {
            0%, 100% { transform: translateY(0px) translateX(0px); opacity: 0.1; }
            50% { transform: translateY(-20px) translateX(10px); opacity: 0.3; }
        }

        .particle {
            position: fixed;
            width: 2px;
            height: 2px;
            background: #9D4EDD;
            border-radius: 50%;
            pointer-events: none;
            animation: float 20s infinite;
            z-index: 0;
        }

        /* Container principal */
        .container {
            max-width: 1000px;
            margin: 0 auto;
            padding: 20px;
            position: relative;
            z-index: 1;
        }

        /* Header */
        header {
            text-align: center;
            padding: 60px 20px;
            animation: slideDown 0.8s ease-out;
        }

        @keyframes slideDown {
            from {
                opacity: 0;
                transform: translateY(-30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        .greeting {
            font-size: 3em;
            font-weight: bold;
            margin-bottom: 20px;
            background: linear-gradient(135deg, #9D4EDD, #FF006E, #9D4EDD);
            background-size: 200% 200%;
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            animation: gradientFlow 3s ease infinite;
        }

        @keyframes gradientFlow {
            0%, 100% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
        }

        .tagline {
            font-size: 1.3em;
            color: #b0b0ff;
            margin-bottom: 30px;
            animation: fadeInUp 1s ease-out 0.3s both;
        }

        /* Badges */
        .badges {
            display: flex;
            gap: 15px;
            justify-content: center;
            flex-wrap: wrap;
            margin-top: 20px;
            animation: fadeInUp 1s ease-out 0.5s both;
        }

        .badge {
            display: inline-block;
            padding: 8px 16px;
            background: rgba(157, 78, 221, 0.2);
            border: 2px solid #9D4EDD;
            border-radius: 20px;
            color: #9D4EDD;
            font-size: 0.9em;
            transition: all 0.3s ease;
            cursor: pointer;
        }

        .badge:hover {
            background: rgba(157, 78, 221, 0.5);
            transform: translateY(-5px);
            box-shadow: 0 10px 30px rgba(157, 78, 221, 0.4);
        }

        @keyframes fadeInUp {
            from {
                opacity: 0;
                transform: translateY(20px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        /* Seções */
        section {
            margin: 50px 0;
            animation: fadeInUp 1s ease-out forwards;
            opacity: 0;
        }

        section:nth-child(1) { animation-delay: 0.6s; }
        section:nth-child(2) { animation-delay: 0.8s; }
        section:nth-child(3) { animation-delay: 1s; }
        section:nth-child(4) { animation-delay: 1.2s; }

        h2 {
            font-size: 2em;
            color: #9D4EDD;
            margin-bottom: 25px;
            display: flex;
            align-items: center;
            gap: 10px;
            border-bottom: 2px solid rgba(157, 78, 221, 0.3);
            padding-bottom: 10px;
        }

        /* Cartões de projeto */
        .projects-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 25px;
            margin-top: 30px;
        }

        .project-card {
            background: rgba(48, 43, 99, 0.5);
            border: 2px solid rgba(157, 78, 221, 0.3);
            border-radius: 15px;
            padding: 25px;
            transition: all 0.3s ease;
            cursor: pointer;
            position: relative;
            overflow: hidden;
        }

        .project-card::before {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: linear-gradient(45deg, transparent, rgba(157, 78, 221, 0.2), transparent);
            transform: rotate(45deg);
            animation: shine 3s infinite;
        }

        @keyframes shine {
            0% {
                transform: translateX(-100%) translateY(-100%) rotate(45deg);
            }
            100% {
                transform: translateX(100%) translateY(100%) rotate(45deg);
            }
        }

        .project-card:hover {
            border-color: #9D4EDD;
            background: rgba(157, 78, 221, 0.15);
            transform: translateY(-10px);
            box-shadow: 0 20px 40px rgba(157, 78, 221, 0.3);
        }

        .project-card h3 {
            color: #9D4EDD;
            margin-bottom: 10px;
            font-size: 1.3em;
            position: relative;
            z-index: 1;
        }

        .project-card p {
            color: #b0b0ff;
            margin-bottom: 15px;
            position: relative;
            z-index: 1;
        }

        .project-link {
            display: inline-block;
            color: #9D4EDD;
            text-decoration: none;
            padding: 8px 15px;
            border: 1px solid #9D4EDD;
            border-radius: 5px;
            transition: all 0.3s ease;
            position: relative;
            z-index: 1;
        }

        .project-link:hover {
            background: #9D4EDD;
            color: #0f0c29;
            transform: translateX(5px);
        }

        /* Tabelas */
        table {
            width: 100%;
            border-collapse: collapse;
            margin-top: 20px;
            border-radius: 10px;
            overflow: hidden;
        }

        th, td {
            padding: 15px;
            text-align: left;
            border-bottom: 1px solid rgba(157, 78, 221, 0.2);
        }

        th {
            background: rgba(157, 78, 221, 0.2);
            color: #9D4EDD;
            font-weight: bold;
        }

        tr:hover {
            background: rgba(157, 78, 221, 0.1);
            transition: all 0.3s ease;
        }

        /* Progress bar */
        .progress-bar {
            width: 100%;
            height: 8px;
            background: rgba(157, 78, 221, 0.2);
            border-radius: 10px;
            overflow: hidden;
            margin-top: 8px;
        }

        .progress-fill {
            height: 100%;
            background: linear-gradient(90deg, #9D4EDD, #FF006E);
            border-radius: 10px;
            animation: progressFill 2s ease-out forwards;
        }

        @keyframes progressFill {
            from { width: 0; }
        }

        /* Tecnologias */
        .tech-list {
            display: flex;
            flex-wrap: wrap;
            gap: 15px;
            margin-top: 20px;
        }

        .tech-item {
            background: rgba(157, 78, 221, 0.2);
            border: 1px solid #9D4EDD;
            padding: 10px 15px;
            border-radius: 20px;
            color: #9D4EDD;
            transition: all 0.3s ease;
            animation: popIn 0.5s ease-out forwards;
            opacity: 0;
        }

        .tech-item:hover {
            background: rgba(157, 78, 221, 0.4);
            transform: scale(1.1) rotate(5deg);
            box-shadow: 0 5px 15px rgba(157, 78, 221, 0.3);
        }

        @keyframes popIn {
            from {
                opacity: 0;
                transform: scale(0.8);
            }
            to {
                opacity: 1;
                transform: scale(1);
            }
        }

        .tech-item:nth-child(1) { animation-delay: 0.1s; }
        .tech-item:nth-child(2) { animation-delay: 0.2s; }
        .tech-item:nth-child(3) { animation-delay: 0.3s; }
        .tech-item:nth-child(4) { animation-delay: 0.4s; }
        .tech-item:nth-child(5) { animation-delay: 0.5s; }
        .tech-item:nth-child(6) { animation-delay: 0.6s; }

        /* Quote */
        .quote {
            background: linear-gradient(135deg, rgba(157, 78, 221, 0.2), rgba(255, 0, 110, 0.1));
            border-left: 4px solid #9D4EDD;
            padding: 20px;
            margin: 30px 0;
            border-radius: 10px;
            font-style: italic;
            color: #b0b0ff;
            animation: slideInLeft 0.8s ease-out;
        }

        @keyframes slideInLeft {
            from {
                opacity: 0;
                transform: translateX(-30px);
            }
            to {
                opacity: 1;
                transform: translateX(0);
            }
        }

        /* Footer */
        footer {
            text-align: center;
            padding: 40px 20px;
            color: #b0b0ff;
            border-top: 1px solid rgba(157, 78, 221, 0.2);
            margin-top: 60px;
            animation: fadeIn 1s ease-out 1.5s both;
        }

        @keyframes fadeIn {
            from { opacity: 0; }
            to { opacity: 1; }
        }

        .footer-links {
            display: flex;
            gap: 20px;
            justify-content: center;
            margin-top: 20px;
            flex-wrap: wrap;
        }

        .footer-links a {
            color: #9D4EDD;
            text-decoration: none;
            transition: all 0.3s ease;
            padding: 10px 15px;
            border-radius: 5px;
        }

        .footer-links a:hover {
            background: rgba(157, 78, 221, 0.2);
            transform: translateY(-3px);
        }

        /* Responsivo */
        @media (max-width: 768px) {
            .greeting {
                font-size: 2em;
            }
            
            .projects-grid {
                grid-template-columns: 1fr;
            }
            
            h2 {
                font-size: 1.5em;
            }
        }
    </style>
</head>
<body>
    <!-- Partículas flutuantes -->
    <script>
        const createParticles = () => {
            for (let i = 0; i < 20; i++) {
                const particle = document.createElement('div');
                particle.className = 'particle';
                particle.style.left = Math.random() * window.innerWidth + 'px';
                particle.style.top = Math.random() * window.innerHeight + 'px';
                particle.style.animationDelay = Math.random() * 5 + 's';
                document.body.appendChild(particle);
            }
        };
        createParticles();
    </script>

    <div class="container">
        <header>
            <h1 class="greeting">👋 Olá, sou Kelvena!</h1>
            <p class="tagline">Dev Fullstack • Open Source • Inovador</p>
            <div class="badges">
                <div class="badge">💻 JavaScript/TypeScript</div>
                <div class="badge">⚛️ React & Next.js</div>
                <div class="badge">🖥️ Node.js</div>
                <div class="badge">🎮 Gaming & Música</div>
            </div>
        </header>

        <section>
            <h2>🚀 Sobre Mim</h2>
            <p>Sou um desenvolvedor apaixonado por <strong>open source</strong>, otimização de sistemas e criar soluções inovadoras. Atualmente contribuindo em projetos que fazem diferença na comunidade dev.</p>
            <ul style="margin-top: 15px; margin-left: 20px;">
                <li>🔭 Trabalhando em projetos open source impactantes</li>
                <li>🌱 Aprofundando conhecimento em TypeScript e Next.js</li>
                <li>💼 Buscando posição Dev Pleno</li>
                <li>⚡ Café é meu debugger favorito ☕</li>
            </ul>
        </section>

        <section>
            <h2>🤝 Onde Eu Contribuo</h2>
            <div class="projects-grid">
                <div class="project-card">
                    <h3>🖥️ Atlas OS</h3>
                    <p>Modificação leve e transparente do Windows para otimizar performance, privacidade e usabilidade.</p>
                    <a href="https://github.com/Atlas-OS/Atlas" class="project-link" target="_blank">Ver Projeto →</a>
                </div>
                <div class="project-card">
                    <h3>📋 Revision Playbook</h3>
                    <p>Ferramenta de automação para customizar e otimizar Windows de forma segura e eficiente.</p>
                    <a href="https://github.com/meetrevision/playbook" class="project-link" target="_blank">Ver Projeto →</a>
                </div>
            </div>
        </section>

        <section>
            <h2>🎨 Meus Projetos</h2>
            <div class="projects-grid">
                <div class="project-card">
                    <h3>🖥️ ChlorideOS</h3>
                    <p>Sistema Operacional customizado e otimizado para máxima performance.</p>
                    <a href="https://github.com/kelvenapk/ChlorideOS" class="project-link" target="_blank">Ver Projeto →</a>
                </div>
                <div class="project-card">
                    <h3>🌐 Kelvenos</h3>
                    <p>Meu perfil e portfólio de desenvolvimento pessoal.</p>
                    <a href="https://github.com/kelvenapk/kelvenos" class="project-link" target="_blank">Ver Projeto →</a>
                </div>
            </div>
        </section>

        <section>
            <h2>🛠️ Tech Stack</h2>
            <div class="tech-list">
                <span class="tech-item">JavaScript</span>
                <span class="tech-item">TypeScript</span>
                <span class="tech-item">React</span>
                <span class="tech-item">Next.js</span>
                <span class="tech-item">Node.js</span>
                <span class="tech-item">Tailwind CSS</span>
            </div>
        </section>

        <section>
            <h2>📊 Metas 2025</h2>
            <table>
                <thead>
                    <tr>
                        <th>Meta</th>
                        <th>Status</th>
                        <th>Progresso</th>
                    </tr>
                </thead>
                <tbody>
                    <tr>
                        <td>🚀 Contribuir em 5+ projetos open source</td>
                        <td>🟡 Em andamento</td>
                        <td>
                            <div class="progress-bar">
                                <div class="progress-fill" style="width: 80%;"></div>
                            </div>
                        </td>
                    </tr>
                    <tr>
                        <td>📚 Dominar TypeScript e Next.js</td>
                        <td>🟢 Concluído</td>
                        <td>
                            <div class="progress-bar">
                                <div class="progress-fill" style="width: 100%;"></div>
                            </div>
                        </td>
                    </tr>
                    <tr>
                        <td>🌐 Lançar 3 projetos pessoais</td>
                        <td>🟡 Em andamento</td>
                        <td>
                            <div class="progress-bar">
                                <div class="progress-fill" style="width: 60%;"></div>
                            </div>
                        </td>
                    </tr>
                    <tr>
                        <td>💼 Conseguir posição Dev Pleno</td>
                        <td>🔴 Planejado</td>
                        <td>
                            <div class="progress-bar">
                                <div class="progress-fill" style="width: 20%;"></div>
                            </div>
                        </td>
                    </tr>
                    <tr>
                        <td>🗣️ Inglês técnico avançado</td>
                        <td>🟡 Em andamento</td>
                        <td>
                            <div class="progress-bar">
                                <div class="progress-fill" style="width: 70%;"></div>
                            </div>
                        </td>
                    </tr>
                </tbody>
            </table>
        </section>

        <section>
            <div class="quote">
                "O código é poesia. Cada linha conta uma história."
                <br><br>
                ⚡ <strong>Fun Fact:</strong> Sempre aberto a novos desafios e aprendizados!
            </div>
        </section>

        <footer>
            <h3 style="color: #9D4EDD; margin-bottom: 15px;">💬 Vamos Conversar?</h3>
            <p>Estou sempre aberto para colaborar, compartilhar conhecimento e explorar novas oportunidades!</p>
            <div class="footer-links">
                <a href="mailto:seu-email@gmail.com" target="_blank">📧 Email</a>
                <a href="https://linkedin.com/in/seu-perfil" target="_blank">💼 LinkedIn</a>
                <a href="https://github.com/kelvenapk" target="_blank">🐙 GitHub</a>
                <a href="https://discord.com" target="_blank">🎮 Discord</a>
            </div>
            <p style="margin-top: 20px; font-size: 0.9em;">Desenvolvido com 💜 por Kelvena</p>
        </footer>
    </div>
</body>
</html>
