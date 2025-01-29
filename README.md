# EU-LIFE-WEEELoop
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>LIFE WEEELoop</title>
    <link href="https://fonts.googleapis.com/css2?family=Montserrat:wght@400;700&display=swap" rel="stylesheet">
    <style>
        body {
            font-family: 'Montserrat', sans-serif;
            line-height: 1.6;
            margin: 0;
            padding: 0;
            background-color: #F5F5F5;
        }
        header {
            background-color: rgb(66, 207, 217);
            color: white;
            text-align: center;
            padding: 1rem;
            position: relative;
        }
        nav {
            background-color: rgb(13, 130, 147);
            color: white;
            padding: 0.5rem;
            text-align: center;
        }
        nav ul {
            list-style-type: none;
            padding: 0;
            display: inline-block;
        }
        nav ul li {
            display: inline;
            margin-right: 10px;
        }
        nav ul li a {
            color: white;
            text-decoration: none;
            cursor: pointer;
        }
        main {
            padding: 20px;
            text-align: center;
        }
        section {
            border: 2px solid rgb(31, 199, 58);
            margin-bottom: 20px;
            padding: 15px;
            border-radius: 8px;
            background-color: white;
        }
        footer {
            background-color: rgb(13, 130, 147);
            color: white;
            text-align: center;
            padding: 1rem;
            position: relative;
        }
        .language-selector {
            position: absolute;
            top: 10px;
            right: 10px;
        }
        .language-selector select {
            font-family: 'Montserrat', sans-serif;
            padding: 5px;
            border: none;
            border-radius: 4px;
            background-color: rgb(13, 130, 147);
            color: white;
            cursor: pointer;
        }
        .language-selector select:focus {
            outline: none;
            box-shadow: 0 0 0 2px rgb(31, 199, 58);
        }
        form {
            text-align: left;
            max-width: 300px;
            margin: 0 auto;
        }
        input[type="text"], input[type="email"] {
            width: 100%;
            padding: 5px;
            margin-bottom: 10px;
        }
        input[type="submit"] {
            background-color: rgb(31, 199, 58);
            color: white;
            border: none;
            padding: 10px 20px;
            cursor: pointer;
            border-radius: 4px;
        }
        .news-item {
            background-color: #f0f0f0;
            border-radius: 8px;
            padding: 15px;
            margin-bottom: 20px;
            text-align: left;
        }
        .news-item h3 {
            color: rgb(13, 130, 147);
        }
        .news-item a {
            display: inline-block;
            background-color: rgb(31, 199, 58);
            color: white;
            text-decoration: none;
            padding: 8px 15px;
            border-radius: 4px;
            margin-top: 10px;
        }
        .news-item a:hover {
            background-color: rgb(25, 160, 46);
        }
    </style>
</head>
<body>
    <header>
        <h1>LIFE WEEELoop</h1>
        <div class="language-selector">
            <select id="idiomas" onchange="cambiarIdioma(this.value)">
                <option value="castellano">Castellano</option>
                <option value="ingles">English</option>
                <option value="euskera">Euskara</option>
            </select>
        </div>
    </header>

    <nav>
        <ul>
            <li><a onclick="cambiarSeccion('inicio')">Inicio</a></li>
            <li><a onclick="cambiarSeccion('objetivos')">Objetivos</a></li>
            <li><a onclick="cambiarSeccion('socios')">Socios</a></li>
            <li><a onclick="cambiarSeccion('noticias')">Noticias</a></li>
            <li><a onclick="cambiarSeccion('contacto')">Contacto</a></li>
        </ul>
    </nav>

    <main id="contenido-principal">
        <!-- El contenido se cargará dinámicamente aquí -->
    </main>

    <footer>
        <p>&copy; 2025 LIFE WEEELoop. Todos los derechos reservados.</p>
    </footer>

    <script>
        const contenidos = {
            inicio: {
                titulo: "Inicio",
                contenido: "Bienvenido al proyecto LIFE WEEELoop, un nuevo modelo de gestión circular y sostenible de placas de cocina."
            },
            objetivos: {
                titulo: "Objetivos",
                contenido: "Aquí puedes listar los objetivos del proyecto."
            },
            socios: {
                titulo: "Socios",
                contenido: "Información sobre los socios del proyecto."
            },
            noticias: {
                titulo: "Noticias",
                contenido: `
                    <div class="news-item">
                        <h3>El futuro de la economía circular</h3>
                        <p>Descubre cómo ECOLEC está liderando el camino hacia un futuro más sostenible en la gestión de residuos electrónicos.</p>
                        <a href="https://www.deia.eus/economia/2024/11/26/futuro-economia-circular-ecolec-8975474.html" target="_blank">Leer más</a>
                    </div>
                `
            },
            contacto: {
                titulo: "Contacto",
                contenido: `
                    <p>Información de contacto del proyecto:</p>
                    <ul>
                        <li>Email: info@lifeweeloop.eu</li>
                        <li>Teléfono: +34 123 456 789</li>
                    </ul>
                    <h3>Posibles Comunicaciones</h3>
                    <p>Si desea recibir actualizaciones sobre el proyecto LIFE WEEELoop, por favor déjenos su información de contacto:</p>
                    <form>
                        <label for="nombre">Nombre:</label>
                        <input type="text" id="nombre" name="nombre"><br><br>
                        <label for="email">Email:</label>
                        <input type="email" id="email" name="email"><br><br>
                        <input type="submit" value="Suscribirse">
                    </form>
                `
            }
        };

        function cambiarSeccion(seccion) {
            const contenidoPrincipal = document.getElementById('contenido-principal');
            const contenidoSeccion = contenidos[seccion];
            contenidoPrincipal.innerHTML = `
                <section>
                    <h2>${contenidoSeccion.titulo}</h2>
                    ${contenidoSeccion.contenido}
                </section>
            `;
        }

        function cambiarIdioma(idioma) {
            const textos = {
                castellano: {
                    inicio: "Inicio",
                    objetivos: "Objetivos",
                    socios: "Socios",
                    noticias: "Noticias",
                    contacto: "Contacto",
                    bienvenida: "Bienvenido al proyecto LIFE WEEELoop, un nuevo modelo de gestión circular y sostenible de placas de cocina.",
                    contactoInfo: "Información de contacto del proyecto:",
                    posiblesComunicaciones: "Posibles Comunicaciones",
                    recibirActualizaciones: "Si desea recibir actualizaciones sobre el proyecto LIFE WEEELoop, por favor déjenos su información de contacto:",
                    nombre: "Nombre:",
                    suscribirse: "Suscribirse",
                    noticiasTitulo: "El futuro de la economía circular",
                    noticiasContenido: "Descubre cómo ECOLEC está liderando el camino hacia un futuro más sostenible en la gestión de residuos electrónicos.",
                    leerMas: "Leer más"
                },
                ingles: {
                    inicio: "Home",
                    objetivos: "Objectives",
                    socios: "Partners",
                    noticias: "News",
                    contacto: "Contact",
                    bienvenida: "Welcome to the LIFE WEEELoop project, a new circular and sustainable management model for kitchen plates.",
                    contactoInfo: "Project contact information:",
                    posiblesComunicaciones: "Possible Communications",
                    recibirActualizaciones: "If you would like to receive updates about the LIFE WEEELoop project, please leave us your contact information:",
                    nombre: "Name:",
                    suscribirse: "Subscribe",
                    noticiasTitulo: "The future of circular economy",
                    noticiasContenido: "Discover how ECOLEC is leading the way towards a more sustainable future in electronic waste management.",
                    leerMas: "Read more"
                },
                euskera: {
                    inicio: "Hasiera",
                    objetivos: "Helburuak",
                    socios: "Bazkideak",
                    noticias: "Berriak",
                    contacto: "Harremana",
                    bienvenida: "Ongi etorri LIFE WEEELoop proiektura, sukaldeko plakak kudeatzeko eredu zirkular eta iraunkor berri bat.",
                    contactoInfo: "Proiektuaren kontaktu-informazioa:",
                    posiblesComunicaciones: "Balizko Komunikazioak",
                    recibirActualizaciones: "LIFE WEEELoop proiektuari buruzko eguneraketak jaso nahi badituzu, utzi zure kontaktu-informazioa:",
                    nombre: "Izena:",
                    suscribirse: "Harpidetu",
                    noticiasTitulo: "Ekonomia zirkularraren etorkizuna",
                    noticiasContenido: "Ezagutu nola ECOLEC hondakin elektronikoen kudeaketan etorkizun jasangarriago baterantz bidea gidatzen ari den.",
                    leerMas: "Gehiago irakurri"
                },
            };

            const idiomaSeleccionado = textos[idioma];
            document.querySelectorAll('nav ul li a').forEach((enlace, index) => {
                enlace.textContent = Object.values(idiomaSeleccionado)[index];
            });

            contenidos.inicio.contenido = idiomaSeleccionado.bienvenida;
            contenidos.contacto.contenido = `
                <p>${idiomaSeleccionado.contactoInfo}</p>
                <ul>
                    <li>Email: info@lifeweeloop.eu</li>
                    <li>Teléfono: +34 123 456 789</li>
                </ul>
                <h3>${idiomaSeleccionado.posiblesComunicaciones}</h3>
                <p>${idiomaSeleccionado.recibirActualizaciones}</p>
                <form>
                    <label for="nombre">${idiomaSeleccionado.nombre}</label>
                    <input type="text" id="nombre" name="nombre"><br><br>
                    <label for="email">Email:</label>
                    <input type="email" id="email" name="email"><br><br>
                    <input type="submit" value="${idiomaSeleccionado.suscribirse}">
                </form>
            `;
            contenidos.noticias.contenido = `
                <div class="news-item">
                    <h3>${idiomaSeleccionado.noticiasTitulo}</h3>
                    <p>${idiomaSeleccionado.noticiasContenido}</p>
                    <a href="https://www.deia.eus/economia/2024/11/26/futuro-economia-circular-ecolec-8975474.html" target="_blank">${idiomaSeleccionado.leerMas}</a>
                </div>
            `;
            cambiarSeccion('inicio');
        }

        // Cargar la sección de inicio por defecto
        cambiarSeccion('inicio');
    </script>
</body>
</html>
