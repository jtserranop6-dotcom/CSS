# 🚀 Simulador de Entrenamiento - Catálogo de Productos
| Información General | Detalle del Proyecto |
| :--- | :--- |
| **Programa de Formación** | Análisis y Desarrollo de Software |
| **Centro de Formación** | Centro Industrial de Mantenimiento Integral (SENA) |
| **Número de Ficha** | 3381732 |
| **Subactividad** | Estructurar la jerarquía de estilos (Selectores, herencia, cascada y especificidad) |

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
| **Genética (Herencia)** | Declaración de `font-family` y `color` base en el selector `body`. | Los encabezados, párrafos y listas adoptan automáticamente estos estilos globales sin reescribirlos. |
| **Pintura por Zonas (Selectores Combinados)** | Reglas compuestas (`header nav ul li a`, `aside ul li a`, `footer ul li a`). | Aísla y colorea cada zona de enlaces independientemente, evitando cruces visuales. |
| **Autoridad (Cascada vs. Especificidad)** | Uso simultáneo de clase (`.btn-comprar`) e ID (`#btn-destacado`). | Demuestra cómo el peso del ID aplasta el orden lógico de la cascada. |

---

## 📊 3. Cálculo de Puntos de Especificidad
| Tipo de Selector | Puntuación | Descripción Técnica |
| :--- | :---: | :--- |
| **Etiqueta (Elemento)** | **1 pt** | Apunta directamente a las etiquetas base de HTML (`p`, `h2`, `article`). |
| **Clase (`.clase`)** | **10 pts** | Agrupa y estiliza conjuntos de elementos bajo un mismo atributo. |
| **Identificador (`#id`)** | **100 pts** | Selecciona de manera unívoca y con máxima prioridad un elemento único. |


