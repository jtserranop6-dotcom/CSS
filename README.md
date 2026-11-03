# 🚀 Simulador de Entrenamiento - Catálogo de Productos
| Información General | Detalle del Proyecto |
| :--- | :--- |
| **Programa de Formación** | Análisis y Desarrollo de Software[cite: 4, 6] |
| **Centro de Formación** | Centro Industrial de Mantenimiento Integral (SENA)[cite: 4] |
| **Número de Ficha** | 3381732[cite: 6] |
| **Subactividad** | Estructurar la jerarquía de estilos (Selectores, herencia, cascada y especificidad)[cite: 4, 6] |

---

## 🏗️ 1. Arquitectura Semántica del Maquetado (`index.html`)
| Bloque Semántico | Elementos HTML Utilizados | Propósito en el Catálogo |
| :--- | :--- | :--- |
| **`<header>`** | `<nav>`, `<ul>`, `<li>`, `<a>` | Aloja la barra de navegación principal con enlaces de acceso rápido[cite: 5, 6]. |
| **`<main>`** | `<section>`, 4 x `<article>`, `<h2>`, `<p>`, `<a>` | Zona central que agrupa el catálogo de productos con su respectiva anatomía[cite: 5, 6]. |
| **`<aside>`** | `<h2>`, `<ul>`, `<li>`, `<a>` | Barra lateral dedicada al menú secundario de filtros por categorías[cite: 5, 6]. |
| **`<footer>`** | `<p>`, `<ul>`, `<li>`, `<a>` | Contiene los derechos de autor y los enlaces de redes sociales[cite: 5, 6]. |

---

## 🎨 2. Leyes Físicas de CSS Aplicadas (`style.css`)
| Ley CSS | Implementación Técnica | Comportamiento en el Navegador |
| :--- | :--- | :--- |
| **Genética (Herencia)** | Declaración de `font-family` y `color` base en el selector `body`[cite: 5, 6]. | Los encabezados, párrafos y listas adoptan automáticamente estos estilos globales sin reescribirlos[cite: 5, 6]. |
| **Pintura por Zonas (Selectores Combinados)** | Reglas compuestas (`header nav ul li a`, `aside ul li a`, `footer ul li a`)[cite: 5, 6]. | Aísla y colorea cada zona de enlaces independientemente, evitando cruces visuales[cite: 5, 6]. |
| **Autoridad (Cascada vs. Especificidad)** | Uso simultáneo de clase (`.btn-comprar`) e ID (`#btn-destacado`)[cite: 5, 6]. | Demuestra cómo el peso del ID aplasta el orden lógico de la cascada[cite: 5, 6]. |

---

## 📊 3. Cálculo de Puntos de Especificidad
| Tipo de Selector | Puntuación | Descripción Técnica |
| :--- | :---: | :--- |
| **Etiqueta (Elemento)** | **1 pt** | Apunta directamente a las etiquetas base de HTML (`p`, `h2`, `article`)[cite: 5, 6]. |
| **Clase (`.clase`)** | **10 pts** | Agrupa y estiliza conjuntos de elementos bajo un mismo atributo[cite: 5, 6]. |
| **Identificador (`#id`)** | **100 pts** | Selecciona de manera unívoca y con máxima prioridad un elemento único[cite: 5, 6]. |


## Hallazgos: El Modelo de Caja

Durante la auditoría del modelo de caja utilizando las herramientas de desarrollo del navegador (DevTools > Computed), pudimos comprobar que los valores espaciales programados en el código coinciden perfectamente con la representación visual:

1. **La diferencia práctica entre Margin y Padding:** 
   El `padding` (relleno interno) corresponde al espacio que hay entre el contenido de la tarjeta de producto y sus bordes, expandiendo el área interna del elemento. Por su parte, el `margin` (margen externo) controla la separación y el espacio libre que existe por fuera del borde entre una tarjeta y los demás elementos de la página.

2. **Por qué es fundamental para el diseño:** 
   Comprender y auditar el modelo de caja es vital porque nos permite controlar con precisión las dimensiones exactas de los componentes, evitar desbordamientos visuales y asegurar una estructura limpia, ordenada y adaptable en todo el catálogo de productos.