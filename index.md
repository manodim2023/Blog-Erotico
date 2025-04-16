<script type="text/javascript">
        var gk_isXlsx = false;
        var gk_xlsxFileLookup = {};
        var gk_fileData = {};
        function loadFileData(filename) {
        if (gk_isXlsx && gk_xlsxFileLookup[filename]) {
            try {
                var workbook = XLSX.read(gk_fileData[filename], { type: 'base64' });
                var firstSheetName = workbook.SheetNames[0];
                var worksheet = workbook.Sheets[firstSheetName];

                // Convert sheet to JSON to filter blank rows
                var jsonData = XLSX.utils.sheet_to_json(worksheet, { header: 1, blankrows: false, defval: '' });
                // Filter out blank rows (rows where all cells are empty, null, or undefined)
                var filteredData = jsonData.filter(row =>
                    row.some(cell => cell !== '' && cell !== null && cell !== undefined)
                );

                // Convert filtered JSON back to CSV
                var csv = XLSX.utils.aoa_to_sheet(filteredData); // Create a new sheet from filtered array of arrays
                csv = XLSX.utils.sheet_to_csv(csv, { header: 1 });
                return csv;
            } catch (e) {
                console.error(e);
                return "";
            }
        }
        return gk_fileData[filename] || "";
        }
        </script><!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Blog de Contos Eróticos</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <style>
        body {
            font-family: 'Georgia', serif;
            background-color: #f5f5f5;
        }
        .story-card:hover {
            transform: scale(1.02);
            transition: transform 0.3s ease;
        }
    </style>
</head>
<body class="bg-gray-100 text-gray-800">
    <!-- Navbar -->
    <nav class="bg-red-900 text-white p-4 sticky top-0 shadow-md">
        <div class="container mx-auto flex justify-between items-center">
            <h1 class="text-2xl font-bold">Contos Sensuais</h1>
            <ul class="flex space-x-6">
                <li><a href="#" class="hover:text-red-300">Início</a></li>
                <li><a href="#categories" class="hover:text-red-300">Categorias</a></li>
                <li><a href="#about" class="hover:text-red-300">Sobre</a></li>
                <li><a href="#contact" class="hover:text-red-300">Contato</a></li>
            </ul>
        </div>
    </nav>

    <!-- Hero Section -->
    <section class="bg-red-800 text-white py-16 text-center">
        <div class="container mx-auto">
            <h2 class="text-4xl font-bold mb-4">Bem-vindo ao Blog de Contos Eróticos</h2>
            <p class="text-lg mb-6">Explore histórias apaixonantes e sensuais que vão despertar sua imaginação.</p>
            <a href="#stories" class="bg-white text-red-800 px-6 py-2 rounded-full hover:bg-red-100">Ver Contos</a>
        </div>
    </section>

    <!-- Stories Section -->
    <section id="stories" class="py-12">
        <div class="container mx-auto">
            <h3 class="text-3xl font-bold text-center mb-8">Últimos Contos</h3>
            <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
                <!-- Story Card Example -->
                <div class="story-card bg-white p-6 rounded-lg shadow-md">
                    <h4 class="text-xl font-semibold mb-2">No Calor da Noite</h4>
                    <p class="text-gray-600 mb-4">Uma história envolvente sobre um encontro inesperado em uma noite quente de verão...</p>
                    <a href="#story1" class="text-red-800 hover:text-red-600">Ler mais</a>
                </div>
                <div class="story-card bg-white p-6 rounded-lg shadow-md">
                    <h4 class="text-xl font-semibold mb-2">Sussurros ao Anoitecer</h4>
                    <p class="text-gray-600 mb-4">Um romance proibido que floresce sob a luz da lua...</p>
                    <a href="#story2" class="text-red-800 hover:text-red-600">Ler mais</a>
                </div>
                <div class="story-card bg-white p-6 rounded-lg shadow-md">
                    <h4 class="text-xl font-semibold mb-2">Desejo Incontrolável</h4>
                    <p class="text-gray-600 mb-4">Uma paixão avassaladora que desafia todas as regras...</p>
                    <a href="#story3" class="text-red-800 hover:text-red-600">Ler mais</a>
                </div>
            </div>
        </div>
    </section>

    <!-- Categories Section -->
    <section id="categories" class="bg-gray-200 py-12">
        <div class="container mx-auto">
            <h3 class="text-3xl font-bold text-center mb-8">Categorias</h3>
            <div class="flex flex-wrap justify-center gap-4">
                <a href="#romance" class="bg-red-800 text-white px-4 py-2 rounded-full hover:bg-red-600">Romance</a>
                <a href="#fantasia" class="bg-red-800 text-white px-4 py-2 rounded-full hover:bg-red-600">Fantasia</a>
                <a href="#drama" class="bg-red-800 text-white px-4 py-2 rounded-full hover:bg-red-600">Drama</a>
                <a href="#mistério" class="bg-red-800 text-white px-4 py-2 rounded-full hover:bg-red-600">Mistério</a>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer class="bg-red-900 text-white py-8">
        <div class="container mx-auto text-center">
            <p class="mb-4">&copy; 2025 Contos Sensuais. Todos os direitos reservados.</p>
            <div class="flex justify-center space-x-6">
                <a href="#privacy" class="hover:text-red-300">Política de Privacidade</a>
                <a href="#terms" class="hover:text-red-300">Termos de Uso</a>
                <a href="#contact" class="hover:text-red-300">Contato</a>
            </div>
        </div>
    </footer>

    <!-- JavaScript for basic interactivity -->
    <script>
        // Smooth scroll for anchor links
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function (e) {
                e.preventDefault();
                document.querySelector(this.getAttribute('href')).scrollIntoView({
                    behavior: 'smooth'
                });
            });
        });
    </script>
</body>
</html>
