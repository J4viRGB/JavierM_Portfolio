<!DOCTYPE html>
<html lang="es">
<head> <link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Anton+SC&family=Noto+Sans+KR:wght@100..900&display=swap" rel="stylesheet">
    <!-- Especifica el tipo de documento y la versión de HTML -->
    <meta charset="UTF-8">
    <!-- Configura el viewport para que el sitio sea responsive -->
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <!-- Título de la página que aparece en la pestaña del navegador -->
    <title>THROUGH MY EYES</title>

    <!-- STYLESHEET -->
    <link rel="stylesheet" href="styles.css">
    
</head>

<body>
    <!-- Sección de encabezado del sitio -->
    <header>
        <h1 class="anton-sc-regular">THROUGH MY EYES</h1>
        <p> Day by Day photography </p>
    </header>
    <!-- Barra de navegación con enlaces -->
    <nav>
        <ul>
            <li><a href="About me.html">About me</a></li>
            <li><a href="https://www.youtube.com/@FaizalWestcott">Media</a></li>
                        <li>
                <a href="">Contact</a>
                <ul>
                    <li><a onclick="sendEmail()">Email</a></li>
                    <li><a href="https://www.instagram.com/throughjaviseyes?igsh=am82azJ1NGYxMDFo&utm_source=qr">Instagram</a></li>
                </ul>
             </li>
        </ul>
    </nav>

    <!-- Contenido principal de la página -->
        <iframe width="780" height="315" src="https://www.youtube.com/embed/Ev5IdBxDyr4?si=dCcuuT1ibiEEEpvM" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

    <!--Unsplash photo Search API-->
 <h1>Unsplash Photo Search</h1>
    <input type="text" id="query" placeholder="Enter search term">
    <button onclick="searchPhotos()">Search</button>
    <div id="photos"></div>
<main>
    <script>
        //Unsplash Photo Search API
        const API_KEY = 'kq-WQmO8mCrHSQuyri6Oz1XRMtFjxTRQLQuq0aTkXPI';

        async function searchPhotos() {
            const query = document.getElementById('query').value;
            const response = await fetch(`https://api.unsplash.com/search/photos?query=${query}&client_id=${API_KEY}`);
            const data = await response.json();
            const photosDiv = document.getElementById('photos');

            photosDiv.innerHTML = ''; // Limpiar resultados anteriores

            data.results.forEach(photo => {
                const img = document.createElement('img');
                img.src = photo.urls.small;
                img.alt = photo.alt_description;
                img.className = 'photo';
                photosDiv.appendChild(img);
            });
        }
//configuracon para el correo
        function sendEmail() {
            var recipient = "javiermarreronoriega@gmail.com"; // Cambia esto con el correo deseado
            var subject = "Asunto del correo";
            var body = "Este es el cuerpo del correo.";

            var mailto_link = "mailto:" + recipient + "?subject=" + encodeURIComponent(subject) + "&body=" + encodeURIComponent(body);

            window.location.href = mailto_link;
        }
    </script>
</main>
    <!-- Pie de página del sitio -->
      <footer>
        <p>&copy; 2024 </p>
    </footer>
</body>
</html>
