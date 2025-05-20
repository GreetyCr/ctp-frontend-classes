# Práctica 4: Proyecto con Tailwind CSS

En esta práctica, vamos a construir una página de inicio (landing page) responsiva utilizando Tailwind CSS. Esta experiencia te permitirá aplicar los conceptos aprendidos sobre Tailwind y entender su flujo de trabajo.

## Objetivos

- Configurar un proyecto con Tailwind CSS
- Implementar una interfaz responsiva utilizando el enfoque utility-first
- Crear componentes reutilizables con Tailwind
- Adaptar el diseño para diferentes tamaños de pantalla

## Requisitos

- Editor de código (VS Code recomendado)
- Node.js y npm instalados
- Conocimientos básicos de HTML
- Conocimientos básicos de terminal/línea de comandos

## Proyecto: Landing Page de Servicio de Tecnología

Vamos a crear una página de inicio para un servicio de tecnología ficticio llamado "TechSolve". Esta página incluirá:

1. Barra de navegación
2. Sección Hero
3. Características del servicio
4. Testimonios
5. Plan de precios
6. Formulario de contacto
7. Pie de página

## Configuración inicial

### Paso 1: Crear la estructura del proyecto

```bash
# Crear directorio del proyecto
mkdir techsolve-landing
cd techsolve-landing

# Inicializar proyecto npm
npm init -y

# Instalar dependencias
npm install -D tailwindcss postcss autoprefixer
npm install -D vite

# Inicializar Tailwind CSS
npx tailwindcss init -p
```

### Paso 2: Configurar Tailwind CSS

Edita el archivo `tailwind.config.js`:

```js
/** @type {import('tailwindcss').Config} */
module.exports = {
  content: ["./src/**/*.{html,js}"],
  theme: {
    extend: {
      colors: {
        primary: {
          50: '#f0f9ff',
          100: '#e0f2fe',
          200: '#bae6fd',
          300: '#7dd3fc',
          400: '#38bdf8',
          500: '#0ea5e9',
          600: '#0284c7',
          700: '#0369a1',
          800: '#075985',
          900: '#0c4a6e',
        },
      },
    },
  },
  plugins: [],
}
```

### Paso 3: Crear archivos base

Crea la estructura de carpetas y archivos:

```
techsolve-landing/
  ├── node_modules/
  ├── src/
  │    ├── index.html
  │    └── input.css
  ├── package.json
  ├── postcss.config.js
  └── tailwind.config.js
```

Edita `src/input.css`:

```css
@tailwind base;
@tailwind components;
@tailwind utilities;

@layer components {
  .btn-primary {
    @apply py-2 px-4 bg-primary-600 text-white font-semibold rounded-lg shadow-md hover:bg-primary-700 focus:outline-none focus:ring-2 focus:ring-primary-500 focus:ring-opacity-75 transition duration-300;
  }
}
```

Actualiza `package.json` con el script de desarrollo:

```json
"scripts": {
  "dev": "vite"
}
```

## Implementación de la Página

### Paso 4: Crear la estructura HTML base

Crea un archivo `src/index.html` con la siguiente estructura:

```html
<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>TechSolve | Soluciones Tecnológicas</title>
  <link rel="stylesheet" href="./input.css">
</head>
<body class="font-sans antialiased text-gray-800 bg-gray-50">
  <!-- Navbar -->
  <header>
    <!-- Aquí irá la barra de navegación -->
  </header>

  <!-- Hero Section -->
  <section>
    <!-- Aquí irá la sección principal -->
  </section>

  <!-- Features Section -->
  <section>
    <!-- Aquí irán las características -->
  </section>

  <!-- Testimonials Section -->
  <section>
    <!-- Aquí irán los testimonios -->
  </section>

  <!-- Pricing Section -->
  <section>
    <!-- Aquí irá el plan de precios -->
  </section>

  <!-- Contact Form -->
  <section>
    <!-- Aquí irá el formulario de contacto -->
  </section>

  <!-- Footer -->
  <footer>
    <!-- Aquí irá el pie de página -->
  </footer>
</body>
</html>
```

### Paso 5: Desarrollar la Barra de Navegación

Reemplaza la sección `<!-- Navbar -->` con:

```html
<header class="bg-white shadow-sm sticky top-0 z-50">
  <nav class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
    <div class="flex justify-between h-16">
      <div class="flex items-center">
        <div class="flex-shrink-0 flex items-center">
          <span class="text-primary-600 font-bold text-xl">TechSolve</span>
        </div>
        <div class="hidden sm:ml-6 sm:flex sm:space-x-8">
          <a href="#" class="border-primary-500 text-gray-900 inline-flex items-center px-1 pt-1 border-b-2 text-sm font-medium">
            Inicio
          </a>
          <a href="#features" class="border-transparent text-gray-500 hover:border-gray-300 hover:text-gray-700 inline-flex items-center px-1 pt-1 border-b-2 text-sm font-medium">
            Características
          </a>
          <a href="#testimonials" class="border-transparent text-gray-500 hover:border-gray-300 hover:text-gray-700 inline-flex items-center px-1 pt-1 border-b-2 text-sm font-medium">
            Testimonios
          </a>
          <a href="#pricing" class="border-transparent text-gray-500 hover:border-gray-300 hover:text-gray-700 inline-flex items-center px-1 pt-1 border-b-2 text-sm font-medium">
            Precios
          </a>
          <a href="#contact" class="border-transparent text-gray-500 hover:border-gray-300 hover:text-gray-700 inline-flex items-center px-1 pt-1 border-b-2 text-sm font-medium">
            Contacto
          </a>
        </div>
      </div>
      
      <div class="hidden sm:ml-6 sm:flex sm:items-center">
        <button class="btn-primary">
          Iniciar sesión
        </button>
      </div>
      
      <div class="flex items-center sm:hidden">
        <button type="button" class="inline-flex items-center justify-center p-2 rounded-md text-gray-400 hover:text-gray-500 hover:bg-gray-100 focus:outline-none focus:ring-2 focus:ring-inset focus:ring-primary-500">
          <span class="sr-only">Abrir menú</span>
          <!-- Icono de menú simplificado -->
          <svg class="h-6 w-6" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke="currentColor">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16M4 18h16" />
          </svg>
        </button>
      </div>
    </div>
  </nav>
</header>
```

### Paso 6: Desarrollar la Sección Hero

Reemplaza la sección `<!-- Hero Section -->` con:

```html
<section class="relative bg-white overflow-hidden">
  <div class="max-w-7xl mx-auto">
    <div class="relative z-10 pb-8 bg-white sm:pb-16 md:pb-20 lg:max-w-2xl lg:w-full lg:pb-28 xl:pb-32">
      <svg class="hidden lg:block absolute right-0 inset-y-0 h-full w-48 text-white transform translate-x-1/2" fill="currentColor" viewBox="0 0 100 100" preserveAspectRatio="none" aria-hidden="true">
        <polygon points="50,0 100,0 50,100 0,100" />
      </svg>

      <div class="relative pt-6 px-4 sm:px-6 lg:px-8"></div>

      <main class="mt-10 mx-auto max-w-7xl px-4 sm:mt-12 sm:px-6 md:mt-16 lg:mt-20 lg:px-8 xl:mt-28">
        <div class="sm:text-center lg:text-left">
          <h1 class="text-4xl tracking-tight font-extrabold text-gray-900 sm:text-5xl md:text-6xl">
            <span class="block xl:inline">Soluciones tecnológicas</span>
            <span class="block text-primary-600 xl:inline">para tu negocio</span>
          </h1>
          <p class="mt-3 text-base text-gray-500 sm:mt-5 sm:text-lg sm:max-w-xl sm:mx-auto md:mt-5 md:text-xl lg:mx-0">
            Transformamos tu empresa con soluciones innovadoras que impulsan la eficiencia, productividad y crecimiento. Descubre cómo la tecnología puede llevar tu negocio al siguiente nivel.
          </p>
          <div class="mt-5 sm:mt-8 sm:flex sm:justify-center lg:justify-start">
            <div class="rounded-md shadow">
              <a href="#contact" class="w-full flex items-center justify-center px-8 py-3 border border-transparent text-base font-medium rounded-md text-white bg-primary-600 hover:bg-primary-700 md:py-4 md:text-lg md:px-10">
                Empezar ahora
              </a>
            </div>
            <div class="mt-3 sm:mt-0 sm:ml-3">
              <a href="#features" class="w-full flex items-center justify-center px-8 py-3 border border-transparent text-base font-medium rounded-md text-primary-700 bg-primary-100 hover:bg-primary-200 md:py-4 md:text-lg md:px-10">
                Ver características
              </a>
            </div>
          </div>
        </div>
      </main>
    </div>
  </div>
  <div class="lg:absolute lg:inset-y-0 lg:right-0 lg:w-1/2">
    <img class="h-56 w-full object-cover sm:h-72 md:h-96 lg:w-full lg:h-full" src="https://images.unsplash.com/photo-1551434678-e076c223a692?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=2850&q=80" alt="Equipo de trabajo">
  </div>
</section>
```

### Paso 7: Implementar la Sección de Características

Reemplaza la sección `<!-- Features Section -->` con:

```html
<section id="features" class="py-12 bg-white">
  <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
    <div class="lg:text-center">
      <h2 class="text-base text-primary-600 font-semibold tracking-wide uppercase">Características</h2>
      <p class="mt-2 text-3xl leading-8 font-extrabold tracking-tight text-gray-900 sm:text-4xl">
        Una mejor manera de trabajar
      </p>
      <p class="mt-4 max-w-2xl text-xl text-gray-500 lg:mx-auto">
        Nuestras soluciones están diseñadas para aumentar la productividad y reducir la complejidad.
      </p>
    </div>

    <div class="mt-10">
      <dl class="space-y-10 md:space-y-0 md:grid md:grid-cols-2 md:gap-x-8 md:gap-y-10">
        <div class="relative">
          <dt>
            <div class="absolute flex items-center justify-center h-12 w-12 rounded-md bg-primary-500 text-white">
              <!-- Heroicon: outline/globe-alt -->
              <svg class="h-6 w-6" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M21 12a9 9 0 01-9 9m9-9a9 9 0 00-9-9m9 9H3m9 9a9 9 0 01-9-9m9 9c1.657 0 3-4.03 3-9s-1.343-9-3-9m0 18c-1.657 0-3-4.03-3-9s1.343-9 3-9m-9 9a9 9 0 019-9" />
              </svg>
            </div>
            <p class="ml-16 text-lg leading-6 font-medium text-gray-900">Soluciones globales</p>
          </dt>
          <dd class="mt-2 ml-16 text-base text-gray-500">
            Nuestras soluciones funcionan en cualquier lugar del mundo, con soporte para múltiples idiomas y regulaciones locales.
          </dd>
        </div>

        <div class="relative">
          <dt>
            <div class="absolute flex items-center justify-center h-12 w-12 rounded-md bg-primary-500 text-white">
              <!-- Heroicon: outline/scale -->
              <svg class="h-6 w-6" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M3 6l3 1m0 0l-3 9a5.002 5.002 0 006.001 0M6 7l3 9M6 7l6-2m6 2l3-1m-3 1l-3 9a5.002 5.002 0 006.001 0M18 7l3 9m-3-9l-6-2m0-2v2m0 16V5m0 16H9m3 0h3" />
              </svg>
            </div>
            <p class="ml-16 text-lg leading-6 font-medium text-gray-900">Seguridad avanzada</p>
          </dt>
          <dd class="mt-2 ml-16 text-base text-gray-500">
            Protección de datos de nivel empresarial con encriptación de extremo a extremo y cumplimiento de normativas.
          </dd>
        </div>

        <div class="relative">
          <dt>
            <div class="absolute flex items-center justify-center h-12 w-12 rounded-md bg-primary-500 text-white">
              <!-- Heroicon: outline/lightning-bolt -->
              <svg class="h-6 w-6" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M13 10V3L4 14h7v7l9-11h-7z" />
              </svg>
            </div>
            <p class="ml-16 text-lg leading-6 font-medium text-gray-900">Rendimiento optimizado</p>
          </dt>
          <dd class="mt-2 ml-16 text-base text-gray-500">
            Velocidad y eficiencia sin compromisos, con tiempos de carga rápidos y consumo de recursos mínimo.
          </dd>
        </div>

        <div class="relative">
          <dt>
            <div class="absolute flex items-center justify-center h-12 w-12 rounded-md bg-primary-500 text-white">
              <!-- Heroicon: outline/annotation -->
              <svg class="h-6 w-6" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M7 8h10M7 12h4m1 8l-4-4H5a2 2 0 01-2-2V6a2 2 0 012-2h14a2 2 0 012 2v8a2 2 0 01-2 2h-3l-4 4z" />
              </svg>
            </div>
            <p class="ml-16 text-lg leading-6 font-medium text-gray-900">Soporte 24/7</p>
          </dt>
          <dd class="mt-2 ml-16 text-base text-gray-500">
            Asistencia técnica disponible todo el día, todos los días, con tiempos de respuesta rápidos y soluciones eficaces.
          </dd>
        </div>
      </dl>
    </div>
  </div>
</section>
```

### Paso 8: Ejecutar el servidor de desarrollo

```bash
npm run dev
```

### Paso 9: Continúa con las secciones restantes

Para completar la práctica, deberás implementar:

1. La sección de testimonios
2. La sección de precios
3. El formulario de contacto
4. El pie de página

## Entregable

Cuando termines, deberás entregar:

1. El código fuente completo del proyecto
2. Capturas de pantalla que muestren cómo se ve el sitio en diferentes tamaños de pantalla (móvil, tablet, escritorio)
3. Un breve informe explicando:
   - Los desafíos que enfrentaste
   - Cómo aplicaste los conceptos de Tailwind CSS
   - Qué aprendiste durante el proceso

## Recursos adicionales

- [Documentación oficial de Tailwind CSS](https://tailwindcss.com/docs)
- [Tailwind UI Components](https://tailwindui.com/components) (algunos son premium)
- [Tailwind Components](https://tailwindcomponents.com/) (componentes gratuitos)
- [Heroicons](https://heroicons.com/) (iconos SVG gratuitos) 