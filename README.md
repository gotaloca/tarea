<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Proceso de Contratación - Recursos Humanos</title>
    <style>
        body {
            font-family: 'Arial', sans-serif;
            background: linear-gradient(135deg, #f5f7fa 0%, #c3cfe2 100%);
            margin: 0;
            padding: 40px;
            color: #333;
        }

        h1 {
            text-align: center;
            font-size: 3rem;
            margin-bottom: 50px;
            color: #333;
            text-transform: uppercase;
            letter-spacing: 2px;
        }

        .container {
            display: flex;
            justify-content: space-between;
            align-items: center;
            flex-wrap: wrap;
            max-width: 1200px;
            margin: 0 auto;
        }

        .phase {
            background: linear-gradient(145deg, #ffffff, #e6e6e6);
            border-radius: 15px;
            box-shadow: 10px 10px 20px rgba(0, 0, 0, 0.1), -10px -10px 20px rgba(255, 255, 255, 0.6);
            margin: 20px;
            padding: 40px;
            width: 280px;
            text-align: center;
            position: relative;
            overflow: hidden;
            transition: all 0.4s ease-in-out;
            opacity: 0;
            transform: translateY(30px);
        }

        .phase:hover {
            transform: translateY(-10px) scale(1.05);
            box-shadow: 0 15px 30px rgba(0, 0, 0, 0.2);
        }

        .icon {
            font-size: 60px;
            margin-bottom: 20px;
            transition: transform 0.3s ease;
        }

        .phase:hover .icon {
            transform: scale(1.3);
        }

        .phase h2 {
            color: #333;
            margin-bottom: 20px;
            font-size: 1.5rem;
            text-transform: uppercase;
            letter-spacing: 1.5px;
        }

        .phase p {
            font-size: 1rem;
            color: #666;
            line-height: 1.8;
        }

        .phase button {
            margin-top: 15px;
            padding: 10px 20px;
            border: none;
            border-radius: 5px;
            background-color: #007BFF;
            color: white;
            cursor: pointer;
            transition: background-color 0.3s;
        }

        .phase button:hover {
            background-color: #0056b3;
        }

        .modal {
            display: none;
            position: fixed;
            z-index: 1;
            left: 0;
            top: 0;
            width: 100%;
            height: 100%;
            overflow: auto;
            background-color: rgb(0,0,0);
            background-color: rgba(0,0,0,0.4);
            padding-top: 60px;
        }

        .modal-content {
            background-color: #fefefe;
            margin: 5% auto;
            padding: 20px;
            border: 1px solid #888;
            width: 80%;
            border-radius: 10px;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
        }

        .close {
            color: #aaa;
            float: right;
            font-size: 28px;
            font-weight: bold;
        }

        .close:hover,
        .close:focus {
            color: black;
            text-decoration: none;
            cursor: pointer;
        }

        .recruitment { border-top: 8px solid #4CAF50; }
        .selection { border-top: 8px solid #2196F3; }
        .hiring { border-top: 8px solid #FFC107; }
        .induction { border-top: 8px solid #FF5722; }

        .icon-recruitment { color: #4CAF50; }
        .icon-selection { color: #2196F3; }
        .icon-hiring { color: #FFC107; }
        .icon-induction { color: #FF5722; }

        @media (max-width: 768px) {
            .container {
                flex-direction: column;
                align-items: center;
            }

            .phase {
                width: 90%;
                margin-bottom: 30px;
            }
        }

        .fade-in {
            animation: fadeIn 1s ease-in-out forwards;
        }

        @keyframes fadeIn {
            from {
                opacity: 0;
                transform: translateY(30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }
    </style>

    <link href="https://fonts.googleapis.com/icon?family=Material+Icons" rel="stylesheet">

    <script>
        window.onload = function() {
            const phases = document.querySelectorAll('.phase');
            phases.forEach((phase, index) => {
                setTimeout(() => {
                    phase.classList.add('fade-in');
                }, index * 300);
            });

            // Modal functionality
            const modals = document.querySelectorAll('.modal');
            const buttons = document.querySelectorAll('.phase button');
            const closeButtons = document.querySelectorAll('.close');

            buttons.forEach((button, index) => {
                button.onclick = function() {
                    modals[index].style.display = "block";
                };
            });

            closeButtons.forEach((closeButton, index) => {
                closeButton.onclick = function() {
                    modals[index].style.display = "none";
                };
            });

            window.onclick = function(event) {
                modals.forEach((modal) => {
                    if (event.target === modal) {
                        modal.style.display = "none";
                    }
                });
            };
        }
    </script>
</head>
<body>
    <h1>Proceso de Contratación de Auxiliar de Recursos Humanos</h1>

    <div class="container">
        <!-- Reclutamiento -->
        <div class="phase recruitment">
            <span class="material-icons icon icon-recruitment">search</span>
            <h2>Reclutamiento</h2>
            <p>Definir perfil del puesto, publicar vacante y revisar currículums recibidos. Identificar los mejores candidatos potenciales.</p>
            <button>Más información</button>
            <div class="modal">
                <div class="modal-content">
                    <span class="close">&times;</span>
                    <h2>Más sobre Reclutamiento</h2>
                    <p>Este proceso incluye una revisión detallada de los currículums, la preparación de una lista corta de candidatos y la planificación de entrevistas iniciales.</p>
                </div>
            </div>
        </div>

        <!-- Selección -->
        <div class="phase selection">
            <span class="material-icons icon icon-selection">people</span>
            <h2>Selección</h2>
            <p>Realizar entrevistas, aplicar pruebas psicométricas y verificar referencias laborales. Evaluar quién cumple mejor con los requisitos del puesto.</p>
            <button>Más información</button>
            <div class="modal">
                <div class="modal-content">
                    <span class="close">&times;</span>
                    <h2>Más sobre Selección</h2>
                    <p>Se llevan a cabo varias entrevistas y pruebas para evaluar habilidades técnicas y blandas, además de la verificación de antecedentes laborales.</p>
                </div>
            </div>
        </div>

        <!-- Contratación -->
        <div class="phase hiring">
            <span class="material-icons icon icon-hiring">assignment</span>
            <h2>Contratación</h2>
            <p>Presentar oferta de empleo, negociar términos si es necesario, firmar contrato y realizar los trámites administrativos correspondientes.</p>
            <button>Más información</button>
            <div class="modal">
                <div class="modal-content">
                    <span class="close">&times;</span>
                    <h2>Más sobre Contratación</h2>
                    <p>Este proceso incluye la redacción del contrato de trabajo y la entrega de documentación relevante, así como la explicación de beneficios y políticas de la empresa.</p>
                </div>
            </div>
        </div>

        <!-- Inducción -->
        <div class="phase induction">
            <span class="material-icons icon icon-induction">school</span>
            <h2>Inducción</h2>
            <p>Integrar al nuevo empleado al equipo, explicar políticas de la empresa y capacitarlo en herramientas y procedimientos.</p>
            <button>Más información</button>
            <div class="modal">
                <div class="modal-content">
                    <span class="close">&times;</span>
                    <h2>Más sobre Inducción</h2>
                    <p>La inducción incluye formación sobre la cultura de la empresa, normas de trabajo y una presentación de los equipos y proyectos en curso.</p>
                </div>
            </div>
        </div>
    </div>
</body>
</html>
