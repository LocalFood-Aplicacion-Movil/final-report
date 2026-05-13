# Capítulo III: Solution UI/UX Design

## 3.1. Product Design

### 3.1.1. Style Guidelines
#### 3.1.1.1. General Style Guidelines
#### Brand Overview

En muchas ciudades, coordinar un punto de encuentro para grupos de personas es un reto. La falta de información clara sobre opciones accesibles para todos provoca que elegir un restaurante o café genere demoras, frustración y a veces hasta cancelaciones de reuniones. **LocalFood** surge como una solución a este problema: una plataforma que ayuda a encontrar el punto medio justo entre colegas, amigos o familiares, mostrando opciones de restaurantes y locales accesibles para todos los miembros del grupo.

A través de geolocalización y un sistema inteligente de recomendación, LocalFood no solo facilita la elección del lugar ideal, sino que también mejora la experiencia social al reducir el tiempo de coordinación y garantizar un encuentro justo y equitativo para todos.

---

#### Brand Name

El nombre de nuestra solución, **LocalFood**, refleja la esencia del proyecto: **"Local"** representa la proximidad, accesibilidad y comunidad, mientras que **"Food"** enfatiza la experiencia compartida alrededor de la comida. La unión de ambos términos transmite de manera clara y directa el propósito central de la aplicación: facilitar reuniones en restaurantes y espacios gastronómicos cercanos al grupo de usuarios.

La elección de un nombre en inglés responde a su carácter sencillo, universal y atractivo para un público amplio, lo que permite escalar la solución más allá de un mercado local.

---

#### Logo

A continuación, se presenta el logo de LocalFood:

![Logo-LocalFood.PNG](../../assets/chapter-3/Logo-LocalFood.PNG)

#### Typography

La tipografía en **LocalFood** juega un papel crucial en la claridad y coherencia de la interfaz.  
Se han definido **dos fuentes principales** que aseguran jerarquía visual y legibilidad:

- **Nunito**  
  Utilizada para títulos, encabezados y botones. Su estilo redondeado y amigable transmite cercanía y frescura, alineándose con la identidad social del proyecto.
    - Variantes: Bold (títulos principales), SemiBold (subtítulos y botones).

- **Lato**  
  Utilizada en párrafos, descripciones, enlaces y textos de apoyo. Su diseño limpio y moderno facilita la lectura en web y móvil.
    - Variantes: Regular (texto general), Italic (notas).

**Niveles tipográficos definidos:**
- Headings (Nunito) → jerarquía clara en títulos.
- Body (Lato) → legibilidad en el texto base.
- Buttons (Nunito SemiBold) → acciones destacadas.
- Links (Lato Italic/Subrayado) → navegación secundaria.

![tipografia.png](../../assets/chapter-3/tipografia.png)

---

#### Colors

La elección de colores es una parte esencial en el diseño de **LocalFood**. Una paleta bien definida no solo determina la estética de la marca, sino que también comunica los valores principales de frescura, accesibilidad y confianza.

En nuestro sistema visual, se distinguen:
- **Color primario**: el que guía la identidad de la marca y se utiliza en los elementos clave de interacción.
- **Colores secundarios**: aquellos que complementan al primario y refuerzan la jerarquía visual.
- **Colores de estado**: usados para indicar acciones específicas (éxito, alerta, error, etc.).
- **Colores base/neutros**: blanco y negro, que aportan legibilidad y balance al diseño.

---

### 🎨 Color Primario
- **Verde Lima**  
  Representa frescura, dinamismo y accesibilidad. Se usa en la navegación activa y elementos destacados de la interfaz.

**Hex:** `#4FFF49`

![verde.PNG](../../assets/chapter-3/verde.PNG)

---

### 🎨 Colores Secundarios
- **Naranja/Beige**  
  Utilizado en el fondo de la barra lateral, transmite calidez y cercanía.  
  **Hex:** `#FFB983`

  ![naranjoso.PNG](../../assets/chapter-3/naranjoso.PNG)

- **Morado/Violeta**  
  Resalta botones y cantidades, aportando energía visual.  
  **Hex:** `#F828FF`

  ![morao.PNG](../../assets/chapter-3/morao.PNG)

- **Azul**  
  Usado en fondos de QR y botones secundarios, transmite confianza.  
  **Hex:** `#5B58FE  
- 
  ![azul.PNG](../../assets/chapter-3/azul.PNG)

---

### 🎨 Colores Base / Neutros
- **Blanco**  
  Fondo principal, aporta claridad y legibilidad.  
  **Hex:** `#FFFFFF`

  ![blanco.PNG](../../assets/chapter-3/blanco.PNG)


- **Negro**  
  Utilizado en tipografía y detalles para alto contraste.  
  **Hex:** `#000000`

  ![negro.PNG](../../assets/chapter-3/negro.PNG)
---

### 3.1.2. Information Architecture

En esta sección se detallan las decisiones y fundamentos que guían la organización del contenido en las experiencias web y móvil de **LocalFood**, incluyendo tanto la Landing Page como la Aplicación Web. Estas propuestas buscan asegurar que los usuarios se adapten fácilmente a la funcionalidad de la plataforma y encuentren lo que necesitan sin esfuerzo. Las decisiones abarcan los sistemas de organización, etiquetado, SEO, búsqueda y navegación.

---
#### 3.1.2.1. Organization Systems

Para estructurar la arquitectura de información de **LocalFood**, se ha adoptado un sistema **jerárquico** en la Landing Page y en la Aplicación Web. Esto permite a los usuarios identificar rápidamente las secciones principales y acceder a las funcionalidades clave.

### Landing Page

La Landing Page de **LocalFood** incluye las siguientes secciones:

- **Inicio (Home):** Presenta la propuesta de valor central de la aplicación, con un mensaje introductorio y botones de llamada a la acción (CTA) como *Iniciar Sesión* o *Registrarse*.
- **Acerca de Nosotros:** Explica la misión, visión y valores de la startup, transmitiendo confianza y transparencia.
- **Marcas Registradas:** Sección destinada a mostrar las alianzas o registros de propiedad intelectual vinculados a la aplicación.
- **Países Hábiles:** Lista de los países en los que la plataforma puede operar o proyecta expandirse.
- **Contáctanos:** Ofrece medios de comunicación, formulario de contacto y enlaces a redes sociales.

### Aplicación Móvil

La aplicación móvil está organizada en secciones diseñadas para guiar al usuario en la planificación de encuentros:

- **Inicio:** Vista general de las opciones y accesos directos a las principales funciones.
- **Colegas:** Permite agregar, buscar y gestionar la lista de amigos/compañeros de reunión. Incluye opciones de búsqueda por usuario, código único o QR.
- **Restaurantes:** Muestra la lista de locales sugeridos como puntos de encuentro, organizados por cercanía y accesibilidad para todos los participantes.
- **Calculadora:** Herramienta que utiliza geolocalización para determinar el punto medio óptimo para los usuarios, minimizando tiempos de traslado.

Cada sección está claramente diferenciada y jerarquizada, con encabezados visibles y botones de acción estratégicamente ubicados.

---

#### 3.1.2.2. Labelling Systems

El sistema de etiquetado en **LocalFood** está diseñado para ser **claro, inclusivo y coherente**.

- **Etiquetas textuales:**
  - *Inicio*, *Colegas*, *Restaurantes*, *Calculadora*, *Cerrar Sesión*.
  - Frases simples y directas, evitando ambigüedad.

- **Etiquetas icónicas:**
  - Ícono de **lupa** para búsqueda.
  - Ícono de **usuario** para la sección de colegas.
  - Ícono de **mapa/ubicación** en la calculadora.
  - Ícono de **QR** para compartir o agregar usuarios rápidamente.

Este etiquetado facilita la comprensión inmediata de las funciones, incluso para usuarios primerizos.

---

#### 3.1.2.3. SEO Tags and Meta Tags

Se definen etiquetas SEO y meta tags para optimizar la visibilidad de la Landing Page y garantizar su correcta indexación en motores de búsqueda.

- **Title:**

  ```html
     <title>LocalFood - Encuentra tu punto medio en Lima</title>
- **Description:**

  ```html
    <meta name="description" content="LocalFood es una aplicación que recomienda restaurantes y cafés equitativos para grupos de amigos y colegas en Lima, utilizando geolocalización inteligente."/>
- **Keywords:**

  ```html
    <meta name="keywords" content="LocalFood, punto medio, app reuniones, restaurantes accesibles, Lima"/>
- **Author:**

  ```html
  <meta name="author" content="© 2024 LocalFood. Todos los derechos reservados."/>
- **Viewport:**

  ```html
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  
#### 3.1.2.4. Searching Systems

La aplicación ofrece distintos métodos de búsqueda para facilitar el acceso a la información:

- **Búsqueda por nombre de usuario:**  
  Permite encontrar y agregar colegas escribiendo directamente su nombre de usuario.

- **Búsqueda por código único:**  
  Opción para ingresar un código corto que identifica a cada usuario.

- **Búsqueda por QR:**  
  Escaneo de un código QR compartido para agregar colegas de forma rápida.

- **Búsqueda de restaurantes:**  
  Filtrado de locales por nombre, categoría o ubicación.
---

#### 3.1.2.5. Navigation Systems

El sistema de navegación en **LocalFood** está diseñado para ser **intuitivo y consistente** en web y móvil:

- **Menú superior (Landing Page – Desktop):**  
  Incluye Inicio, Acerca de Nosotros, Marcas Registradas, Países Hábiles y Contacto.

- **Menú lateral (Aplicación Web – Desktop):**  
  Accesos directos a Inicio, Colegas, Restaurantes, Calculadora y Cerrar Sesión.

- **Navegación inferior (Mobile):**  
  Barra con íconos para Inicio, Colegas, Restaurantes y Perfil.

- **CTA fijo:**  
  Botón destacado *“Encuentra tu punto medio”* disponible en la sección de calculadora.

- **Footer (Landing Page):**  
  Enlaces a políticas de privacidad, términos de servicio y redes sociales.
---

### 3.1.3. Landing Page UI Design

**Introducción:**  
La landing page de LocalFood refleja los valores de equidad, frescura y eficiencia. La estructura guía al usuario de manera clara hacia los beneficios y el uso inmediato de la app.

---

#### 3.1.3.1. Landing Page Wireframe

**Versión Desktop**

Los wireframes muestran la jerarquía de secciones, menús y CTA sin detalles visuales, priorizando la organización de contenido y navegación.

![Wirelading1.png](../../assets/chapter-3/Wirelading1.png)

![Wirelading2.png](../../assets/chapter-3/Wirelading2.png)

![Wirelading3.png](../../assets/chapter-3/Wirelading3.png)

![Wirelading4.png](../../assets/chapter-3/Wirelading4.png)

#### 3.1.3.2. Landing Page Mock-up

**Versión Desktop**

![Wirelading1.png](../../assets/chapter-3/Wirelading1.png)

![Wirelading2.png](../../assets/chapter-3/Wirelading2.png)

![Wirelading3.png](../../assets/chapter-3/Wirelading3.png)

![Wirelading4.png](../../assets/chapter-3/Wirelading4.png)

### 3.1.4. Mobile Applications UX/UI Design
#### 3.1.4.1. Mobile Applications Wireframes
#### 3.1.4.2. Mobile Applications Wireflow Diagrams
#### 3.1.4.3. Mobile Applications Mock-ups
#### 3.1.4.4. Mobile Applications User Flow Diagrams
#### 3.1.4.5. Mobile Applications Prototyping

En esta sección se presentan los prototipos de interfaz de usuario desarrollados para la versión web en navegadores de escritorio, tanto para turistas como para agencias. Estos prototipos simulan la navegación e interacción con las principales funcionalidades, en base a los flujos definidos previamente en los Wireflow Diagrams.

Las decisiones de interacción se tomaron considerando principios de usabilidad, claridad visual, diseño inclusivo y una arquitectura de información coherente. Se priorizó una navegación intuitiva, adaptada al perfil y objetivos de cada usuario. El sistema de navegación, las jerarquías visuales y los tipos de interacción fueron diseñados para facilitar la experiencia del usuario, busqueda del punto de encuentro mas óptimo, entre otras actividades.

Los prototipos permiten visualizar el comportamiento del sistema ante las principales tareas definidas, asegurando una experiencia consistente y funcional. Se incluye una captura de pantalla y un enlace al video en Microsoft Stream donde se muestra la simulación de interacción correspondiente.
