<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Portfolio de jhiaim</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Inter', 'Segoe UI', system-ui, -apple-system, sans-serif;
            background: #f8fafc;
            min-height: 100vh;
            padding: 40px 20px;
            color: #334155;
        }

        .container {
            max-width: 1100px;
            width: 100%;
            margin: 0 auto;
        }

        .header {
            background: white;
            padding: 50px;
            border-radius: 8px;
            box-shadow: 0 1px 3px rgba(0, 0, 0, 0.1);
            margin-bottom: 40px;
            border-top: 4px solid #2563eb;
        }

        h1 {
            color: #0f172a;
            font-size: 2.5em;
            margin-bottom: 30px;
            font-weight: 700;
            letter-spacing: -0.5px;
        }

        .intro-section {
            display: grid;
            grid-template-columns: 1.8fr 1fr;
            gap: 50px;
            align-items: start;
        }

        .about-me {
            color: #475569;
            line-height: 1.8;
            font-size: 1.05em;
        }

        .about-me p {
            margin-bottom: 18px;
        }

        .about-me strong {
            color: #1e293b;
            font-weight: 600;
        }

        .objectif {
            color: #1e40af;
            font-weight: 500;
            margin-top: 25px;
            padding: 20px;
            background: #eff6ff;
            border-radius: 6px;
            border-left: 4px solid #2563eb;
        }

        .contact-section {
            background: #f8fafc;
            padding: 30px;
            border-radius: 6px;
            border: 1px solid #e2e8f0;
        }

        .contact-section h3 {
            color: #0f172a;
            margin-bottom: 20px;
            font-size: 1.1em;
            font-weight: 600;
            text-transform: uppercase;
            letter-spacing: 0.5px;
            font-size: 0.9em;
            color: #64748b;
        }

        .contact-item {
            display: flex;
            align-items: center;
            margin-bottom: 16px;
            color: #475569;
            font-size: 0.95em;
        }

        .contact-item .icon {
            margin-right: 12px;
            font-size: 1.1em;
            color: #64748b;
            width: 20px;
        }

        .contact-item a {
            color: #2563eb;
            text-decoration: none;
            transition: color 0.2s;
        }

        .contact-item a:hover {
            color: #1d4ed8;
        }

        .folders {
            display: flex;
            justify-content: center;
            gap: 24px;
            margin-bottom: 30px;
            flex-wrap: wrap;
        }

        .folder {
            background: white;
            padding: 30px 40px;
            border-radius: 6px;
            text-align: center;
            cursor: pointer;
            transition: all 0.2s ease;
            box-shadow: 0 1px 3px rgba(0, 0, 0, 0.1);
            text-decoration: none;
            color: inherit;
            border: 1px solid #e2e8f0;
            min-width: 180px;
        }

        .folder:hover {
            transform: translateY(-2px);
            box-shadow: 0 4px 12px rgba(0, 0, 0, 0.15);
            border-color: #2563eb;
        }

        .folder-icon {
            font-size: 42px;
            margin-bottom: 12px;
            filter: grayscale(20%);
        }

        .folder span {
            display: block;
            font-size: 1em;
            font-weight: 600;
            color: #1e293b;
            letter-spacing: 0.3px;
        }

        .modal {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(15, 23, 42, 0.7);
            z-index: 1000;
            justify-content: center;
            align-items: center;
            padding: 20px;
            backdrop-filter: blur(4px);
        }

        .modal.active {
            display: flex;
        }

        .modal-content {
            background: white;
            border-radius: 8px;
            max-width: 800px;
            width: 100%;
            max-height: 85vh;
            overflow-y: auto;
            box-shadow: 0 20px 60px rgba(0, 0, 0, 0.3);
            animation: slideIn 0.3s ease;
        }

        @keyframes slideIn {
            from {
                transform: translateY(-30px);
                opacity: 0;
            }
            to {
                transform: translateY(0);
                opacity: 1;
            }
        }

        .modal-header {
            background: #1e293b;
            color: white;
            padding: 30px 35px;
            border-radius: 8px 8px 0 0;
            display: flex;
            justify-content: space-between;
            align-items: center;
            border-bottom: 3px solid #2563eb;
        }

        .modal-header h2 {
            font-size: 1.6em;
            font-weight: 600;
            letter-spacing: -0.3px;
        }

        .close-btn {
            background: rgba(255, 255, 255, 0.1);
            border: none;
            color: white;
            font-size: 24px;
            cursor: pointer;
            width: 36px;
            height: 36px;
            border-radius: 4px;
            display: flex;
            align-items: center;
            justify-content: center;
            transition: all 0.2s ease;
        }

        .close-btn:hover {
            background: rgba(255, 255, 255, 0.2);
        }

        .modal-body {
            padding: 40px 35px;
            color: #475569;
            line-height: 1.8;
        }

        .placeholder {
            text-align: center;
            padding: 60px 40px;
            color: #94a3b8;
            font-style: italic;
        }

        .placeholder p:first-child {
            font-size: 1.1em;
            margin-bottom: 15px;
        }

        .footer {
            text-align: center;
            color: #64748b;
            margin-top: 50px;
            font-size: 0.9em;
            padding: 20px;
        }

        @media (max-width: 768px) {
            .intro-section {
                grid-template-columns: 1fr;
                gap: 30px;
            }

            .header {
                padding: 30px;
            }

            h1 {
                font-size: 2em;
            }

            .folders {
                gap: 16px;
            }

            .folder {
                min-width: 140px;
                padding: 24px 30px;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <div class="header">
            <h1>Portfolio de jhiaim</h1>
            
            <div class="intro-section">
                <div class="about-me">
                    <p>
                        Étudiant en <strong>BTS SIO SISR</strong> (Solutions d'Infrastructure, Systèmes et Réseaux), 
                        je suis passionné par l'informatique, l'administration réseau et la cybersécurité.
                    </p>
                    <p>
                        Au cours de ma formation, j'ai développé des compétences en administration système, 
                        gestion de réseaux, sécurité informatique et virtualisation. Je cherche constamment 
                        à approfondir mes connaissances dans ces domaines en pleine évolution.
                    </p>
                    <p class="objectif">
                        <strong>Objectif professionnel :</strong> Je souhaite évoluer dans l'administration réseau 
                        et la cybersécurité, en contribuant à la sécurisation et à l'optimisation des infrastructures informatiques.
                    </p>
                </div>

                <div class="contact-section">
                    <h3>Contact</h3>
                    <div class="contact-item">
                        <span class="icon">✉</span>
                        <a href="mailto:votre.email@example.com">votre.email@example.com</a>
                    </div>
                    <div class="contact-item">
                        <span class="icon">🔗</span>
                        <a href="https://linkedin.com/in/votreprofil" target="_blank">LinkedIn</a>
                    </div>
                    <div class="contact-item">
                        <span class="icon">💻</span>
                        <a href="https://github.com/jhiaim" target="_blank">GitHub</a>
                    </div>
                    <div class="contact-item">
                        <span class="icon">📱</span>
                        <span>+33 X XX XX XX XX</span>
                    </div>
                </div>
            </div>
        </div>

        <div class="folders">
            <div class="folder" onclick="openModal('competences')">
                <div class="folder-icon">📊</div>
                <span>Compétences</span>
            </div>
            <div class="folder" onclick="openModal('projets')">
                <div class="folder-icon">💼</div>
                <span>Projets</span>
            </div>
            <div class="folder" onclick="openModal('cv')">
                <div class="folder-icon">📄</div>
                <span>CV</span>
            </div>
        </div>

        <div class="footer">
            <p>© 2025 jhiaim - BTS SIO SISR</p>
        </div>
    </div>

    <!-- Modals -->
    <div id="modal-competences" class="modal" onclick="closeModal(event, 'competences')">
        <div class="modal-content" onclick="event.stopPropagation()">
            <div class="modal-header">
                <h2>Compétences</h2>
                <button class="close-btn" onclick="closeModal(event, 'competences')">&times;</button>
            </div>
            <div class="modal-body">
                <div class="placeholder">
                    <p>À compléter prochainement...</p>
                    <p style="margin-top: 20px; font-size: 0.9em;">
                        Cette section contiendra mes compétences techniques en réseau, cybersécurité et administration système.
                    </p>
                </div>
            </div>
        </div>
    </div>

    <div id="modal-projets" class="modal" onclick="closeModal(event, 'projets')">
        <div class="modal-content" onclick="event.stopPropagation()">
            <div class="modal-header">
                <h2>Projets</h2>
                <button class="close-btn" onclick="closeModal(event, 'projets')">&times;</button>
            </div>
            <div class="modal-body">
                <div class="placeholder">
                    <p>À compléter prochainement...</p>
                    <p style="margin-top: 20px; font-size: 0.9em;">
                        Cette section présentera mes projets réalisés durant ma formation BTS SIO SISR.
                    </p>
                </div>
            </div>
        </div>
    </div>

    <div id="modal-cv" class="modal" onclick="closeModal(event, 'cv')">
        <div class="modal-content" onclick="event.stopPropagation()">
            <div class="modal-header">
                <h2>CV</h2>
                <button class="close-btn" onclick="closeModal(event, 'cv')">&times;</button>
            </div>
            <div class="modal-body">
                <div class="placeholder">
                    <p>CV disponible prochainement...</p>
                    <p style="margin-top: 20px; font-size: 0.9em;">
                        Mon CV détaillé sera disponible ici pour téléchargement.
                    </p>
                </div>
            </div>
        </div>
    </div>

    <script>
        function openModal(type) {
            const modal = document.getElementById('modal-' + type);
            modal.classList.add('active');
            document.body.style.overflow = 'hidden';
        }

        function closeModal(event, type) {
            event.stopPropagation();
            const modal = document.getElementById('modal-' + type);
            modal.classList.remove('active');
            document.body.style.overflow = 'auto';
        }

        document.addEventListener('keydown', function(e) {
            if (e.key === 'Escape') {
                const modals = document.querySelectorAll('.modal.active');
                modals.forEach(modal => {
                    modal.classList.remove('active');
                    document.body.style.overflow = 'auto';
                });
            }
        });
    </script>
</body>
</html>
