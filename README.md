# 🚀 Simulador de Entrenamiento - Catálogo de Productos
| Información General | Detalle del Proyecto |
| :--- | :--- |
| **Programa de Formación** | Análisis y Desarrollo de Software |
| **Centro de Formación** | Centro Industrial de Mantenimiento Integral (SENA) |
| **Número de Ficha** | 3381732 |
| **Subactividad** | Construir la macro-arquitectura bidimensional (Grid CSS) |

---

## 🏗️ 1. Arquitectura Semántica del Maquetado (`index.html`)
| Bloque Semántico | Elementos HTML Utilizados | Propósito en el Catálogo |
| :--- | :--- | :--- |
| **`<header>`** | `<nav>`, `<ul>`, `<li>`, `<a>` | Aloja la barra de navegación principal con enlaces de acceso rápido. |
| **`<main>`** | `<section>`, `<article>`, `<h2>`, `<h3>`, `<p>`, `<button>` | Zona central que agrupa el catálogo de productos y el formulario de contacto. |
| **`<aside>`** | `<h3>`, `<ul>`, `<li>`, `<a>` | Barra lateral dedicada al menú secundario de filtros por categorías. |
| **`<footer>`** | `<p>`, `<div>`, `<a>` | Contiene los derechos de autor y los enlaces de políticas y términos. |

---

## 🎨 2. Leyes Físicas de CSS Aplicadas (`style.css`)
| Ley CSS | Implementación Técnica | Comportamiento en el Navegador |
| :--- | :--- | :--- |
| **Genética (Herencia)** | Declaración de `font-family` y `color` base en el selector `body`. | Los encabezados, párrafos y listas adoptan automáticamente estos estilos globales sin reescribirlos. |
| **Pintura por Zonas (Selectores Combinados)** | Reglas compuestas y clases BEM aisladas por componente. | Aísla y colorea cada zona de enlaces independientemente, evitando cruces visuales. |
| **Autoridad (Cascada vs. Especificidad)** | Uso equilibrado de selectores planos con metodología BEM. | Mantiene la jerarquía limpia y predecible sin guerras de especificidad. |

---

## 📊 3. Cálculo de Puntos de Especificidad
| Tipo de Selector | Puntuación | Descripción Técnica |
| :--- | :---: | :--- |
| **Etiqueta (Elemento)** | **1 pt** | Apunta directamente a las etiquetas base de HTML (`p`, `h2`, `article`). |
| **Clase (`.clase`)** | **10 pts** | Agrupa y estiliza conjuntos de elementos bajo un mismo atributo. |
| **Identificador (`#id`)** | **100 pts** | Selecciona de manera unívoca y con máxima prioridad un elemento único. |

---

## Hallazgos: El Modelo de Caja

Durante la auditoría del modelo de caja utilizando las herramientas de desarrollo del navegador (DevTools > Computed), pudimos comprobar que los valores espaciales programados en el código coinciden perfectamente con la representación visual:

1. **La diferencia práctica entre Margin y Padding:** 
   El `padding` (relleno interno) corresponde al espacio que hay entre el contenido de la tarjeta de producto y sus bordes, expandiendo el área interna del elemento. Por su parte, el `margin` (margen externo) controla la separación y el espacio libre que existe por fuera del borde entre una tarjeta y los demás elementos de la página.

2. **Por qué es fundamental para el diseño:** 
   Comprender y auditar el modelo de caja es vital porque nos permite controlar con precisión las dimensiones exactas de los componentes, evitar desbordamientos visuales y asegurar una estructura limpia, ordenada y adaptable en todo el catálogo de productos.

---

## Hallazgos: Centralización de Identidad Visual y Espaciado

1. **Lista completa de variables declaradas:**
   - **Colores:**
     - `--color-primario`: `#1e293b` (Color principal para títulos y estructura).
     - `--color-secundario`: `#7c3aed` (Color de acento para botones, bordes y destacados).
     - `--color-fondo`: `#f8fafc` (Color de fondo de la interfaz).
     - `--color-tarjeta`: `#f3f4f6` (Color de fondo de los contenedores).
     - `--color-texto`: `#334155` (Color general del texto).
     - `--color-borde`: `#d1d5db` (Color de bordes suaves).
   - **Tipografía:**
     - `--fuente-principal`: `'Inter', sans-serif` (Tipografía importada desde Google Fonts).
   - **Espaciados (Box Model):**
     - `--espaciado-pequeno`: `8px`
     - `--espaciado-medio`: `16px`
     - `--espaciado-grande`: `24px`
     - `--espaciado-xl`: `32px`

2. **Ventaja de reutilizar medidas de margen y relleno:**
   La reutilización de tokens de espaciado elimina la duplicación de valores arbitrarios, garantizando una escala armónica y permitiendo realizar modificaciones globales de manera instantánea desde `:root`.

3. **De qué manera la centralización en `:root` previene colisiones visuales a medida que la hoja de estilos crece:**
   Al unificar los valores clave en un solo lugar, se reduce la deuda técnica y se evita la sobreescritura caótica de selectores, asegurando que cualquier componente nuevo mantenga la coherencia visual del sistema de diseño.

---

## Hallazgos: Pseudoclases y Pseudoelementos

1. **La diferencia funcional entre una pseudoclase y un pseudoelemento:**
   Una **pseudoclase** (como `:hover`, `:active` o `:focus`) reacciona a los estados o acciones del usuario sobre un elemento existente. Un **pseudoelemento** (como `::before` o `::after`) permite insertar y estilizar contenido virtual de forma dinámica sin alterar la estructura HTML.

2. **La importancia técnica de la pseudoclase `:focus` para cumplir con buenas prácticas de accesibilidad web:**
   Permite que los usuarios que navegan con el teclado (tecla Tab) identifiquen visualmente el elemento activo mediante un contorno personalizado, facilitando la accesibilidad web.

3. **Por qué es una buena práctica inyectar elementos decorativos desde CSS con `::before`/`::after`:**
   Mantiene el marcado HTML limpio y estrictamente semántico, separando la presentación visual y los detalles puramente decorativos hacia la capa de estilos.

---

## Hallazgos: Arquitectura BEM y Modularidad

1. **¿Qué significa la sigla BEM y cómo se escribe visualmente?**
   - **BEM** significa **Block, Element, Modifier** (*Bloque, Elemento, Modificador*).
   - Visualmente se escribe combinando el nombre del bloque independiente, seguido de un doble guion bajo (`__`) para sus elementos internos, y un doble guion medio (`--`) para sus variaciones o estados:
     - **Bloque:** `.card`
     - **Elemento:** `.card__title`, `.card__price`, `.card__button`
     - **Modificador:** `.card--destacada`, `.card__button--secundario`

2. **¿Por qué dividir el CSS en varios archivos facilita el trabajo colaborativo?**
   Al desacoplar una hoja de estilos gigante en módulos pequeños e independientes (`tarjetas.css`, `botones.css`, `menu-lateral.css`, `estilos.css`) conectados mediante `@import`, varios desarrolladores pueden trabajar en distintos componentes al mismo tiempo sin pisar el código del otro ni provocar conflictos de fusión (*merge conflicts*) en Git. Además, facilita ubicar y corregir errores rápidamente.

3. **¿Cómo esta metodología evita la guerra de especificidad (Cascada)?**
   En CSS tradicional, usar selectores anidados (como `#productos .producto-card h3`) aumenta el peso de especificidad y obliga a usar reglas más largas o `!important` para sobrescribir estilos. Con BEM, todos los selectores se mantienen planos utilizando **una única clase por regla** (peso de especificidad `10`), lo que elimina colisiones accidentales y hace que el comportamiento de la cascada sea completamente predecible y escalable.

---

## Hallazgos: Arquitectura Total con Flexbox

1. **Importancia de `min-height: 100vh` y `flex-direction: column` en el contenedor global (`.app-layout`):**
   Permitió que la estructura general ocupe siempre el 100% del alto de la pantalla del navegador y apile el encabezado, el área central y el pie de página de forma vertical. Al combinarlo con `flex: 1` en `.main-wrapper`, el contenido central absorbe todo el espacio sobrante y empuja el `.footer` hacia el borde inferior sin que quede flotando.

2. **Reemplazo de márgenes laterales por `gap` en la navegación:**
   Aplicar `display: flex` y `gap: var(--espaciado-medio)` directamente en `.nav__list` eliminó la necesidad de usar `float` o márgenes individuales entre enlaces, logrando una separación limpia, uniforme y gobernada desde las Custom Properties.

3. **Sinergia de BEM, Custom Properties y Flexbox en las tarjetas (`.card`):**
   La nomenclatura BEM mantuvo aislados los bloques y modificadores sin colisiones, las variables centralizaron espaciados y colores, y Flexbox (con `flex-direction: column` en `.card` y `flex-grow: 1` en `.card__description`) funcionó como un resorte que absorbe textos de distinta longitud para mantener todos los botones perfectamente alineados en la base.

---

## Hallazgos: Grid CSS Avanzado

1. **¿Por qué usar `grid-template-areas` hace que el código sea más legible para un humano?**
   Porque permite "dibujar" visualmente la arquitectura de la página dentro del propio código CSS utilizando nombres semánticos claros (`"header header"`, `"sidebar contenido"`, `"footer footer"`). Esto facilita comprender de un vistazo cómo se distribuyen las filas y columnas de toda la interfaz sin tener que calcular números de líneas o coordenadas de cuadrícula mentalmente.

2. **¿Qué magia matemática ocurre cuando combinas `auto-fit` con `minmax()` en una galería?**
   Al aplicar `grid-template-columns: repeat(auto-fit, minmax(280px, 1fr))` en `.products__grid`, el navegador calcula automáticamente cuántas columnas de al menos `280px` caben en el ancho disponible de la pantalla. Si el ancho aumenta, agrega nuevas columnas; si el ancho se reduce, reacomoda las tarjetas hacia abajo; y con `auto-fit` colapsa las pistas vacías repartiendo el espacio sobrante en partes iguales (`1fr`), logrando un diseño fluido sin depender de múltiples Media Queries.

3. **¿Cuál es la regla de oro moderna para decidir cuándo usar Grid y cuándo usar Flexbox?**
   Se utiliza **CSS Grid** cuando necesitamos controlar **dos dimensiones simultáneas** (filas y columnas a la vez, como el esqueleto general `.app-layout` y la vitrina `.products__grid`) y **Flexbox** cuando organizamos o alineamos elementos en **una sola dimensión** (una fila o una columna, como la barra de navegación `.nav__list` o los botones dentro de cada tarjeta `.card`).