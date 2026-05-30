<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Michi D'Oro - Menú Digital</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link href="https://fonts.googleapis.com/css2?family=Playfair+Display:ital,wght@0,400;0,600;1,400&family=Lato:wght@300;400;700&display=swap" rel="stylesheet">
    <style>
        :root {
            --color-dorado: #D4AF37; /* Dorado clásico */
            --color-palo-rosa: #e6b8b8; /* Palo de rosa suave */
            --color-verde-manzana: #8DB600; /* Verde manzana vibrante */
            --color-fondo: #FDFBF7; /* Blanco roto cálido */
            --color-texto: #333333; /* Gris muy oscuro para legibilidad */
        }

        body {
            font-family: 'Lato', sans-serif;
            background-color: var(--color-fondo);
            color: var(--color-texto);
            line-height: 1.6;
        }

        h1, h2, h3, .font-serif {
            font-family: 'Playfair Display', serif;
        }

        /* Utilidades de color personalizadas de Tailwind */
        .text-dorado { color: var(--color-dorado); }
        .bg-dorado { background-color: var(--color-dorado); }
        .border-dorado { border-color: var(--color-dorado); }
        
        .text-palo-rosa { color: var(--color-palo-rosa); }
        .bg-palo-rosa { background-color: var(--color-palo-rosa); }
        
        .text-verde-manzana { color: var(--color-verde-manzana); }
        .bg-verde-manzana { background-color: var(--color-verde-manzana); }

        /* Estilos para el acordeón del menú */
        .category-content {
            max-height: 0;
            overflow: hidden;
            transition: max-height 0.3s ease-out;
        }
        
        .category-header.active {
            color: var(--color-dorado);
        }
        
        .category-header.active .icon-chevron {
            transform: rotate(180deg);
        }

        .icon-chevron {
            transition: transform 0.3s ease;
        }
        
        /* Decoración de fondo */
        .bg-pattern {
            background-image: radial-gradient(var(--color-palo-rosa) 1px, transparent 1px);
            background-size: 20px 20px;
            opacity: 0.1;
            position: fixed;
            top: 0; left: 0; right: 0; bottom: 0;
            z-index: -1;
        }
    </style>
</head>
<body class="antialiased min-h-screen relative">
    <div class="bg-pattern"></div>

    <div class="max-w-md mx-auto bg-white min-h-screen shadow-xl relative overflow-hidden">
        
        <header class="pt-10 pb-6 px-6 text-center relative">
            <div class="absolute top-0 left-0 w-full h-2 bg-gradient-to-r from-dorado via-palo-rosa to-verde-manzana" style="background-image: linear-gradient(to right, var(--color-dorado), var(--color-palo-rosa), var(--color-verde-manzana));"></div>
            
            <img src="Recurso 35.png" alt="Michi D'Oro Logo" class="w-48 mx-auto mb-4" onerror="this.src='https://placehold.co/200x100/ffffff/333333?text=Michi+D%27Oro'">
            
            <p class="font-serif italic text-sm text-gray-500 mt-2">"Lo Lindo de la Vida"</p>
            <div class="w-16 h-0.5 bg-dorado mx-auto mt-4 rounded"></div>
        </header>

        <main class="px-6 pb-12">
            <h1 class="text-3xl font-serif text-center mb-8 tracking-wider">Menú</h1>

            <div id="menu-container" class="space-y-4">
                <!-- Las categorías se insertarán aquí con JavaScript -->
            </div>
        </main>

        <footer class="bg-gray-50 py-8 px-6 text-center border-t border-gray-100">
            <p class="font-serif text-dorado text-lg mb-2">Michi D'Oro</p>
            <p class="text-sm text-gray-500 mb-4">Gelato Clásico Italiano</p>
            <div class="flex justify-center space-x-4 mb-6">
                <!-- Iconos de redes sociales simulados -->
                <a href="#" class="text-gray-400 hover:text-palo-rosa transition"><svg class="w-6 h-6" fill="currentColor" viewBox="0 0 24 24" aria-hidden="true"><path fill-rule="evenodd" d="M12.315 2c2.43 0 2.784.013 3.808.06 1.064.049 1.791.218 2.427.465a4.902 4.902 0 011.772 1.153 4.902 4.902 0 011.153 1.772c.247.636.416 1.363.465 2.427.048 1.067.06 1.407.06 4.123v.08c0 2.643-.012 2.987-.06 4.043-.049 1.064-.218 1.791-.465 2.427a4.902 4.902 0 01-1.153 1.772 4.902 4.902 0 01-1.772 1.153c-.636.247-1.363.416-2.427.465-1.067.048-1.407.06-4.123.06h-.08c-2.643 0-2.987-.012-4.043-.06-1.064-.049-1.791-.218-2.427-.465a4.902 4.902 0 01-1.772-1.153 4.902 4.902 0 01-1.153-1.772c-.247-.636-.416-1.363-.465-2.427-.047-1.024-.06-1.379-.06-3.808v-.63c0-2.43.013-2.784.06-3.808.049-1.064.218-1.791.465-2.427a4.902 4.902 0 011.153-1.772A4.902 4.902 0 015.45 2.525c.636-.247 1.363-.416 2.427-.465C8.901 2.013 9.256 2 11.685 2h.63zm-.081 1.802h-.468c-2.456 0-2.784.011-3.807.058-.975.045-1.504.207-1.857.344-.467.182-.8.398-1.15.748-.35.35-.566.683-.748 1.15-.137.353-.3.882-.344 1.857-.047 1.023-.058 1.351-.058 3.807v.468c0 2.456.011 2.784.058 3.807.045.975.207 1.504.344 1.857.182.466.399.8.748 1.15.35.35.683.566 1.15.748.353.137.882.3 1.857.344 1.054.048 1.37.058 4.041.058h.08c2.597 0 2.917-.01 3.96-.058.976-.045 1.505-.207 1.858-.344.466-.182.8-.398 1.15-.748.35-.35.566-.683.748-1.15.137-.353.3-.882.344-1.857.048-1.055.058-1.37.058-4.041v-.08c0-2.597-.01-2.917-.058-3.96-.045-.976-.207-1.505-.344-1.858a3.097 3.097 0 00-.748-1.15 3.098 3.098 0 00-1.15-.748c-.353-.137-.882-.3-1.857-.344-1.023-.047-1.351-.058-3.807-.058zM12 6.865a5.135 5.135 0 110 10.27 5.135 5.135 0 010-10.27zm0 1.802a3.333 3.333 0 100 6.666 3.333 3.333 0 000-6.666zm5.338-3.205a1.2 1.2 0 110 2.4 1.2 1.2 0 010-2.4z" clip-rule="evenodd" /></svg></a>
                <a href="#" class="text-gray-400 hover:text-dorado transition"><svg class="w-6 h-6" fill="currentColor" viewBox="0 0 24 24" aria-hidden="true"><path d="M8.29 20.251c7.547 0 11.675-6.253 11.675-11.675 0-.178 0-.355-.012-.53A8.348 8.348 0 0022 5.92a8.19 8.19 0 01-2.357.646 4.118 4.118 0 001.804-2.27 8.224 8.224 0 01-2.605.996 4.107 4.107 0 00-6.993 3.743 11.65 11.65 0 01-8.457-4.287 4.106 4.106 0 001.27 5.477A4.072 4.072 0 012.8 9.713v.052a4.105 4.105 0 003.292 4.022 4.095 4.095 0 01-1.853.07 4.108 4.108 0 003.834 2.85A8.233 8.233 0 012 18.407a11.616 11.616 0 006.29 1.84" /></svg></a>
            </div>
            <p class="text-xs text-gray-400">© 2026 Michi D'Oro. Todos los derechos reservados.</p>
        </footer>
    </div>

    <script>
        const menuData = [
            {
                category: "Gelato Clásico Italiano",
                description: "Nuestra especialidad en vasos y conos.",
                icon: "🍦",
                items: [
                    { name: "Vaso pequeño (1 sabor)", description: "", price: "$9.900", badges: [] },
                    { name: "Vaso mediano (2 sabores)", description: "", price: "$15.900", badges: [] },
                    { name: "Vaso grande (3 sabores)", description: "", price: "$19.500", badges: [] },
                    { name: "Cono sencillo", description: "", price: "$10.900", badges: [] },
                    { name: "Cono doble", description: "", price: "$15.900", badges: [] }
                ],
                subsections: [
                    {
                        title: "Sabores de Gelato",
                        list: [
                            "Stracciatella", "Pie de limón", "Amarena", "Chocolate", 
                            "Chocomenta", "Queso", "Chocorochelle", "Pistacho", 
                            "Cheesecake de arándanos", "Vainilla", "Ron con pasas", 
                            "Caramelo salado", "Yogurt de maracuyá", "Yogurt de frambuesa", "Almendra"
                        ]
                    },
                    {
                        title: "Sorbetes",
                        list: [
                            "Maracumango", "Sandía", "Piña, lulo y canela", "Guayaba", "Limón"
                        ]
                    }
                ]
            },
            {
                category: "Gelato Soft",
                description: "Helado suave a base de yogurt griego, bajo en azúcar.",
                icon: "🍨",
                items: [
                    { name: "Soft sencillo", description: "", price: "$9.000", badges: [] },
                    { name: "Soft con salsa y topping favorito", description: "", price: "$12.000", badges: ["Recomendado"] },
                    { name: "Soft de frutos rojos", description: "", price: "$15.000", badges: [] },
                    { name: "Soft de cacao pistacho", description: "", price: "$19.900", badges: [] }
                ],
                subsections: [
                    {
                        title: "Salsas",
                        list: ["Maracuyá", "Frutos rojos", "Arequipe", "Caramelo", "Pistacho"]
                    },
                    {
                        title: "Toppings",
                        list: ["Granola de albaricoque", "Maní", "M&M", "Fruta fresca", "Arándanos", "Fresa", "Mango"]
                    }
                ]
            },
            {
                category: "Copas de Gelato",
                description: "Combinaciones perfectas listas para disfrutar.",
                icon: "🍧",
                items: [
                    { name: "Florencia", description: "Gelato de vainilla, yogurt de maracuyá, coulis de maracuyá y trozos de mango.", price: "$18.900", badges: [] },
                    { name: "Tiramisú", description: "Bizcochuelo, gelato de Chocorochelle, vainilla y salsa de café.", price: "$19.900", badges: ["Especialidad"] },
                    { name: "Piccolo", description: "Copa infantil con yogurt de frambuesa y vainilla.", price: "$14.900", badges: ["Infantil"] }
                ]
            },
            {
                category: "Waffles con Gelato",
                description: "Crujientes, calientitos y con tu gelato favorito.",
                icon: "🧇",
                items: [
                    { name: "Waffle de frutos rojos y gelato", description: "", price: "$16.900", badges: [] },
                    { name: "Waffle de Nutella, banano y gelato", description: "", price: "$17.900", badges: ["Top Ventas"] },
                    { name: "Waffle de jalea de guayaba y gelato", description: "", price: "$22.000", badges: [] }
                ]
            },
            {
                category: "Especiales",
                description: "Para darte un gusto extra.",
                icon: "🍪",
                items: [
                    { name: "Galleta artesanal", description: "", price: "$12.000", badges: [] },
                    { name: "Galleta con gelato", description: "", price: "$21.500", badges: [] },
                    { name: "Affogato", description: "", price: "$13.900", badges: [] },
                    { name: "Affogato de almendra", description: "", price: "$17.200", badges: [] },
                    { name: "Malteada", description: "", price: "$17.000", badges: [] },
                    { name: "Gelato con brownie", description: "", price: "$16.900", badges: [] },
                    { name: "Rollo de canela con gelato", description: "", price: "$14.900", badges: [] },
                    { name: "Crepe de pistacho", description: "", price: "$19.900", badges: [] }
                ]
            },
            {
                category: "Smoothies y Jugos",
                description: "Opciones funcionales y refrescantes.",
                icon: "🥤",
                items: [
                    { name: "Proteína Smoothie Recovery", description: "Proteína vegana, leche vegetal y mantequilla de almendras natural.", price: "$15.500", badges: ["Vegano", "Proteína"] },
                    { name: "Green Recovery Juice", description: "Espinaca, apio, limón, pepino, menta, aguacate y piña.", price: "$13.500", badges: ["Saludable"] },
                    { name: "Amarillo Juice", description: "Piña, banano, mango, maracuyá, cúrcuma, jengibre e hielo.", price: "$13.500", badges: ["Refrescante"] },
                    { name: "Berry Smoothie", description: "Fresa, banano, arándanos y mantequilla pura de almendras.", price: "$13.500", badges: [] }
                ]
            }
        ];

        const menuContainer = document.getElementById('menu-container');

        function createBadge(text) {
            let bgColorClass = "bg-dorado"; // Por defecto dorado
            let textColorClass = "text-white";
            
            const lowerText = text.toLowerCase();
            if (lowerText === 'vegano' || lowerText === 'saludable') {
                bgColorClass = "bg-verde-manzana";
                textColorClass = "text-white";
            } else if (lowerText === 'especialidad' || lowerText === 'recomendado' || lowerText === 'top ventas') {
                bgColorClass = "bg-palo-rosa";
                textColorClass = "text-white";
            }

            return `<span class="inline-block px-2 py-0.5 mt-1 mr-1 text-[10px] font-bold uppercase rounded-full ${bgColorClass} ${textColorClass} shadow-sm">${text}</span>`;
        }

        function renderMenu() {
            menuData.forEach((section, index) => {
                let subsectionsHTML = '';
                
                // Procesar subsecciones (como listas de sabores, salsas, etc.) si existen
                if (section.subsections && section.subsections.length > 0) {
                    subsectionsHTML = `<div class="mt-4 border-t border-gray-200 pt-4 space-y-4">`;
                    section.subsections.forEach(sub => {
                        subsectionsHTML += `
                            <div>
                                <h4 class="font-serif font-semibold text-dorado mb-2">${sub.title}</h4>
                                <ul class="grid grid-cols-2 gap-x-4 gap-y-1 text-sm text-gray-600">
                                    ${sub.list.map(item => `<li class="flex items-start"><span class="text-palo-rosa mr-2">•</span> <span>${item}</span></li>`).join('')}
                                </ul>
                            </div>
                        `;
                    });
                    subsectionsHTML += `</div>`;
                }

                const sectionHTML = `
                    <div class="border border-gray-100 rounded-xl bg-white shadow-sm overflow-hidden mb-4">
                        <button class="category-header w-full flex items-center justify-between p-4 text-left focus:outline-none focus:ring-2 focus:ring-palo-rosa focus:ring-opacity-50 transition-colors hover:bg-gray-50" onclick="toggleCategory(${index})">
                            <div class="flex items-center space-x-3">
                                <span class="text-2xl">${section.icon}</span>
                                <div>
                                    <h2 class="font-serif text-xl font-semibold tracking-wide">${section.category}</h2>
                                    <p class="text-xs text-gray-500 mt-0.5">${section.description}</p>
                                </div>
                            </div>
                            <svg class="icon-chevron w-5 h-5 text-gray-400" id="chevron-${index}" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 9l-7 7-7-7"></path></svg>
                        </button>
                        
                        <div id="content-${index}" class="category-content bg-gray-50">
                            <div class="p-4 pt-2">
                                <div class="space-y-4">
                                    ${section.items.map(item => `
                                        <div class="flex justify-between items-start border-b border-gray-200 pb-3 last:border-0 last:pb-0">
                                            <div class="pr-4 flex-1">
                                                <h3 class="font-semibold text-gray-800 text-base">${item.name}</h3>
                                                ${item.description ? `<p class="text-sm text-gray-500 mt-0.5 leading-snug">${item.description}</p>` : ''}
                                                <div class="mt-1">
                                                    ${item.badges.map(badge => createBadge(badge)).join('')}
                                                </div>
                                            </div>
                                            <div class="font-serif font-bold text-dorado text-lg whitespace-nowrap mt-0.5">
                                                ${item.price}
                                            </div>
                                        </div>
                                    `).join('')}
                                </div>
                                ${subsectionsHTML}
                            </div>
                        </div>
                    </div>
                `;
                menuContainer.innerHTML += sectionHTML;
            });
        }

        function toggleCategory(index) {
            const content = document.getElementById(`content-${index}`);
            const header = content.previousElementSibling;
            
            header.classList.toggle('active');
            
            if (content.style.maxHeight) {
                content.style.maxHeight = null;
            } else {
                content.style.maxHeight = content.scrollHeight + "px";
            }
        }

        // Inicializar el menú
        document.addEventListener('DOMContentLoaded', () => {
            renderMenu();
            // Abrir la primera categoría por defecto
            setTimeout(() => toggleCategory(0), 100); 
        });

    </script>
</body>
</html>
