# Capítulo IV: Product Implementation & Validation

## 4. Product Implementation & Validation

## 4.1. Software Configuration Management

En esta sección se describe el proceso integral mediante el cual el equipo de LocalFood organiza, gestiona y controla los cambios durante el ciclo de vida del desarrollo del software. Establecer una sólida gestión de la configuración es vital para un proyecto que involucra múltiples repositorios, interfaces iterativas y algoritmos de geolocalización, asegurando la trazabilidad, la calidad del código y la entrega continua de valor.

---

### 4.1.1. Software Development Environment Configuration

Para garantizar un flujo de trabajo eficiente y estandarizado entre todos los integrantes del equipo, se ha configurado un entorno de desarrollo estructurado en cuatro pilares: Gestión, Diseño, Desarrollo y Control de Versiones.

#### A. Gestión de Requisitos y Planificación

- **Trello:** Herramienta seleccionada para gestionar el flujo de trabajo bajo el marco de metodologías ágiles (Scrum). Se utiliza para visualizar el estado real de las tareas (`To Do`, `Doing`, `Testing`, `Done`), asignar responsables y dar seguimiento a los Story Points de cada historia de usuario (como la configuración del algoritmo de rutas o el filtrado de restaurantes) durante los Sprints.
    - Ruta de referencia: https://trello.com/

#### B. Diseño UX/UI y Modelado

- **Figma:** Plataforma colaborativa basada en la nube utilizada para la elaboración de wireframes y prototipos de alta fidelidad. En el contexto de LocalFood, Figma permitió iterar rápidamente sobre las vistas del mapa interactivo, las tarjetas de recomendación de restaurantes y las versiones responsivas para Desktop y Mobile.
    - Ruta de referencia: https://www.figma.com/

- **Lucidchart:** Aplicación empleada para diagramar la arquitectura de la información y los flujos del sistema. Se utilizó extensamente en las etapas previas para diseñar los flujos de usuario (User Flows) y los diagramas C4 correspondientes a los Bounded Contexts.
    - Ruta de referencia: https://www.lucidchart.com/

#### C. Entorno de Desarrollo y Stack Tecnológico (Frontend & Landing Page)

- **Visual Studio Code (VS Code):** Seleccionado como el Entorno de Desarrollo Integrado (IDE) principal del equipo por su ligereza y alto nivel de personalización. Su soporte nativo para el ecosistema web y la capacidad de integrar extensiones (como ESLint, Prettier y Live Server) optimizan la escritura del código para las interfaces de la plataforma.
    - Ruta de referencia: https://code.visualstudio.com/

- **HTML5 & CSS3:** Tecnologías base para la estructuración y estilización. Se emplea HTML5 para garantizar un maquetado semántico y accesible. CSS3, apoyado por el framework Tailwind CSS, se utiliza para manejar el diseño responsivo, garantizando que la aplicación se adapte perfectamente tanto a comensales en dispositivos móviles como a dueños de locales en ordenadores.

- **Vue.js:** Framework progresivo de JavaScript seleccionado para el desarrollo de componentes reactivos en la Landing Page y la documentación interactiva, permitiendo una renderización rápida y una arquitectura basada en componentes reutilizables.

#### D. Control de Versiones e Integración

- **Git:** Sistema de control de versiones distribuido utilizado de manera local por cada desarrollador a través de la interfaz de línea de comandos (CLI). Permite mantener un historial detallado de los cambios en los algoritmos de cálculo y las interfaces.

- **GitHub:** Plataforma en la nube que actúa como repositorio central del proyecto. Facilita la colaboración asíncrona, las revisiones de código (Pull Requests) y la integración de las contribuciones de todo el equipo de ingeniería.
    - Ruta de referencia: https://github.com/

---

### 4.1.2. Source Code Management

Dada la naturaleza colaborativa del proyecto y la necesidad de integrar funcionalidades complejas (como el motor de búsqueda del punto medio y la gestión de grupos), el equipo ha adoptado el flujo de trabajo **GitFlow**. Este enfoque proporciona una estructura robusta para la gestión de versiones, aislando el desarrollo de nuevas características y protegiendo el código en producción.

#### Estructura de Ramas del Proyecto LocalFood

**Ramas Principales:**

- **`main` (Principal):** Es la rama de producción. Contiene el código completamente estable, probado y funcional. Cada fusión (merge) hacia esta rama representa una nueva versión oficial del producto y se marca con etiquetas semánticas (ej. `v1.0.0`) para facilitar el rastreo de los releases.

- **`develop` (Desarrollo):** Actúa como la rama de pre-producción. Es el punto de integración donde convergen todas las nuevas funcionalidades una vez terminadas. El código aquí debe ser compilable y funcional para pasar por pruebas de integración antes de ser enviado a `main`.

**Ramas de Soporte (Derivadas):**

- **`feature/*` (Características):** Ramas independientes derivadas de `develop`. Se utilizan para desarrollar historias de usuario específicas (ej. `feature/distance-calculator`, `feature/restaurant-filters`). Garantizan que el trabajo paralelo de los ingenieros no interfiera con la base de código estable. Una vez aprobadas mediante un Pull Request, se fusionan de vuelta a `develop`.

- **`chapter/*` (Documentación):** Ramas específicas para la redacción y control de versiones de los informes y capítulos del proyecto académico. Al finalizar un documento, se integra para su revisión y consolidación.

- **`release/*` (Lanzamientos):** Ramas creadas a partir de `develop` cuando el software está maduro para un despliegue. Permiten congelar el desarrollo de nuevas funciones mientras se realizan pruebas finales de control de calidad (QA) y correcciones menores antes de fusionarse con `main`.

- **`hotfix/*` (Urgencias):** Ramas de emergencia que se derivan directamente de `main`. Su propósito es resolver errores críticos (bugs) detectados en el entorno de producción. Una vez solucionado el problema, se fusionan tanto en `main` (para arreglar el entorno en vivo) como en `develop` (para que las futuras versiones contengan el parche).

![gitflow.png](../../assets/gitflow.png)


---

### 4.1.3. Source Code Style Guide & Conventions

Para garantizar que el código fuente de LocalFood sea mantenible, escalable y legible por cualquier miembro del equipo (actual o futuro), se ha establecido una guía de estilos estricta. La estandarización reduce la carga cognitiva durante las revisiones de código y previene errores de sintaxis.

#### 1. Convenciones para HTML5

- **Semántica y Accesibilidad:** Todos los documentos deben iniciar con la declaración `<!DOCTYPE html>` y el atributo de idioma correspondiente (ej. `<html lang="es">`).

- **Cierre de Etiquetas:** Todos los elementos HTML deben estar correctamente cerrados. Los elementos vacíos deben incluir la barra de cierre de forma explícita para evitar comportamientos inesperados en el DOM (ej. `<img src="..." alt="..." />`, `<br />`).

- **Atributos:** Es obligatorio el uso de comillas dobles (`" "`) para todos los atributos (ej. `class="card-container"`). Asimismo, todas las imágenes deben contener el atributo `alt` para fines de accesibilidad y SEO, describiendo brevemente su contenido.

#### 2. Convenciones para CSS3 y Tailwind

- **Indentación y Formato:** Se utilizará una sangría estricta de **2 espacios** (sin uso de tabulaciones) para mantener la consistencia en el espaciado.

- **Nomenclatura:** Todas las propiedades, valores y selectores personalizados deben estar escritos en minúsculas. En caso de usar clases CSS propias, se utilizará la convención `kebab-case` (ej. `.btn-primary-green`).

- **Limpieza de Código:** Se prohíben los espacios en blanco innecesarios al final de las líneas y las líneas vacías redundantes dentro de los bloques de estilo.

#### 3. Convenciones para Vue.js

El equipo se adhiere a las reglas de la guía de estilo oficial de Vue (Essential & Strongly Recommended):

- **Nombres de Componentes:** Deben seguir la convención `PascalCase` tanto en la definición del archivo como en su importación (ej. `RestaurantCard.vue`, `GroupCalculator.vue`). Esto los diferencia claramente de los elementos HTML nativos.

- **Definición de Props:** Los componentes que reciban props deben definir obligatoriamente su tipo de dato (`String`, `Number`, `Array`, etc.) y proporcionar un valor por defecto (`default`) para prevenir caídas de la interfaz por datos no resueltos durante las llamadas a la API de restaurantes.

---

### 4.1.4. Software Deployment Configuration

El despliegue inicial de la presentación del proyecto (Landing Page y Reportes Académicos) se ha configurado utilizando **GitHub Pages**, lo que permite alojar y servir archivos estáticos de forma rápida, segura e integrada directamente con nuestro flujo de control de versiones.

El proceso completo de configuración y despliegue continuo se estructuró de la siguiente manera:

#### 1. Creación y Estructura del Repositorio

Se estableció un repositorio público centralizado en GitHub bajo la organización del equipo. Este repositorio alberga el código fuente de la página de aterrizaje y la documentación iterativa.

Comando de clonación local:

```bash
git clone https://github.com/LocalFood-Aplicaciones-Web/Project-report.git
```

#### 2. Desarrollo del Sitio Estático

La Landing Page, diseñada para captar a los comensales y dueños de locales interesados en la aplicación, fue desarrollada utilizando el stack definido (HTML, CSS, Tailwind.css y Vue.js). Los archivos compilados y listos para producción se alojan en la raíz del repositorio o dentro del directorio `/docs`, asegurando que la ruta sea compatible con el motor de despliegue de GitHub.

#### 3. Configuración del Pipeline en GitHub Pages

Dentro de la plataforma de GitHub, se accedió al panel de configuración del repositorio (**Settings > Pages**). En la sección de fuente (**Source**), se configuró el despliegue automático desde la rama destinada a producción (generalmente `main` o una rama específica como `gh-pages`), apuntando al directorio raíz (`/root`).

Esta configuración asegura que cada nuevo commit fusionado a la rama de despliegue desencadene automáticamente una actualización del sitio en vivo (Continuous Deployment básico).

#### 4. Verificación y Acceso al Entorno de Producción

Tras la correcta ejecución de los procesos internos de GitHub, el entorno es validado asegurando la carga de assets (imágenes, hojas de estilo) y el correcto funcionamiento de los botones de "Call to Action".

- **Enlace de despliegue oficial:** https://localfood-aplicaciones-web.github.io/Project-report/
#### 4.1.2. Source Code Management

- Trello: Herramienta utilizada para gestionar el flujo de trabajo de proyectos principalmente marcos en red de trabajos ágiles. El segmento para visualizar y actualizar el estado real de las tareas e historias de usuario pertenecientes al sprint a desarrollado.

  Ruta de referencia: https://trello.com/es

### 4.2. Landing Page & Mobile Application Implementation

#### 4.2.1. Sprint n
##### 4.2.1.1. Sprint Planning n
##### 4.2.1.2. Sprint Backlog n
##### 4.2.1.3. Development Evidence for Sprint Review
##### 4.2.1.4. Testing Suite Evidence for Sprint Review
##### 4.2.1.5. Execution Evidence for Sprint Review
##### 4.2.1.6. Services Documentation Evidence for Sprint Review
##### 4.2.1.7. Software Deployment Evidence for Sprint Review
##### 4.2.1.8. Team Collaboration Insights during Sprint

### 4.3. Validation Interviews
#### 4.3.1. Diseño de Entrevistas
#### 4.3.2. Registro de Entrevistas
#### 4.3.3. Evaluaciones según heurísticas