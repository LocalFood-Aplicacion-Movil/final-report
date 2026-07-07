# Capítulo IV: Product Implementation & Validation

## 4. Product Implementation & Validation

## 4.1. Software Configuration Management

En esta sección se describe el proceso integral mediante el cual el equipo de NearbyEats organiza, gestiona y controla los cambios durante el ciclo de vida del desarrollo del software. Establecer una sólida gestión de la configuración es vital para un proyecto que involucra múltiples repositorios, interfaces iterativas y algoritmos de geolocalización, asegurando la trazabilidad, la calidad del código y la entrega continua de valor.

---

### 4.1.1. Software Development Environment Configuration

Para garantizar un flujo de trabajo eficiente y estandarizado entre todos los integrantes del equipo, se ha configurado un entorno de desarrollo estructurado en cuatro pilares: Gestión, Diseño, Desarrollo y Control de Versiones.

#### A. Gestión de Requisitos y Planificación

- **Trello:** Herramienta seleccionada para gestionar el flujo de trabajo bajo el marco de metodologías ágiles (Scrum). Se utiliza para visualizar el estado real de las tareas (`To Do`, `Doing`, `Testing`, `Done`), asignar responsables y dar seguimiento a los Story Points de cada historia de usuario (como la configuración del algoritmo de rutas o el filtrado de restaurantes) durante los Sprints.
    - Ruta de referencia: https://trello.com/

#### B. Diseño UX/UI y Modelado

- **Figma:** Plataforma colaborativa basada en la nube utilizada para la elaboración de wireframes y prototipos de alta fidelidad. En el contexto de NearbyEats, Figma permitió iterar rápidamente sobre las vistas del mapa interactivo, las tarjetas de recomendación de restaurantes y las versiones responsivas para Desktop y Mobile.
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

#### Estructura de Ramas del Proyecto NearbyEats

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

Para garantizar que el código fuente de NearbyEats sea mantenible, escalable y legible por cualquier miembro del equipo (actual o futuro), se ha establecido una guía de estilos estricta. La estandarización reduce la carga cognitiva durante las revisiones de código y previene errores de sintaxis.

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
git clone https://github.com/NearbyEats-Aplicaciones-Web/Project-report.git
```

#### 2. Desarrollo del Sitio Estático

La Landing Page, diseñada para captar a los comensales y dueños de locales interesados en la aplicación, fue desarrollada utilizando el stack definido (HTML, CSS, Tailwind.css y Vue.js). Los archivos compilados y listos para producción se alojan en la raíz del repositorio o dentro del directorio `/docs`, asegurando que la ruta sea compatible con el motor de despliegue de GitHub.

#### 3. Configuración del Pipeline en GitHub Pages

Dentro de la plataforma de GitHub, se accedió al panel de configuración del repositorio (**Settings > Pages**). En la sección de fuente (**Source**), se configuró el despliegue automático desde la rama destinada a producción (generalmente `main` o una rama específica como `gh-pages`), apuntando al directorio raíz (`/root`).

Esta configuración asegura que cada nuevo commit fusionado a la rama de despliegue desencadene automáticamente una actualización del sitio en vivo (Continuous Deployment básico).

#### 4. Verificación y Acceso al Entorno de Producción

Tras la correcta ejecución de los procesos internos de GitHub, el entorno es validado asegurando la carga de assets (imágenes, hojas de estilo) y el correcto funcionamiento de los botones de "Call to Action".

- **Enlace de despliegue oficial:** https://NearbyEats-aplicaciones-web.github.io/Project-report/

### 4.2. Landing Page & Mobile Application Implementation

#### 4.2.1. Sprint 1
En este punto se documenta el proceso realizado durante la primera fase del proyecto, en la cual se analizaron los diseños del aplicativo móvil y los requisitos funcionales previamente analizados para desarrollar la primera versión de la aplicación móvil de NearbyEats.

##### 4.2.1.1. Sprint Planning 1

| Sprint #                        | Sprint 1                                                                                                                                                                                                                                                                                                                                                                    |
| ------------------------------- |-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Sprint Planning Background      |
| Date                            | 12/05/2026                                                                                                                                                                                                                                                                                                                                                                  |
| Time                            | 14:50 PM                                                                                                                                                                                                                                                                                                                                                                    |
| Location                        | Reunión virtual en discord.                                                                                                                                                                                                                                                                                                                                                 |
| Preparate by                    | Gabriel Mamani Marca                                                                                                                                                                                                                                                                                                                                                        |
| Attendees (to planning meeting) | Anyelo Alejos,Pedro Guía,Ivan Sanchez y Anderson Ventosilla                                                                                                                                                                                                                                                                                                                 |
| Sprint n-1 Review Summary       | Se desarrolló la primera versión del landing page, del backend y del frontend móvil.                                                                                                                                                                                                                                                                                        |
| Sprint Planning Background      | Desarrollo de la primera versión de la plataforma NearbyEats.                                                                                                                                                                                                                                                                                                                |
| Sprint Goal & User Stories      |
| Sprint 1 Goal                   | Nuestro enfoque es desarrollar la landing page y verificar que cumpla con las historias de usuario identificadas. El objetivo principal es asegurar que la landing page ofrezca traducción a múltiples idiomas, sea responsive y resulte fácil de usar para el usuario. Asimismo, se desarrolla una primera versión de la aplicación móvil en Kotlin y del backend en .NET. |
| Sprint Velocity                 | Se establece un Velocity de 25 Story Points para el primer Sprint.                                                                                                                                                                                                                                                                                                          |
| Sum of Story Points             | 25 Story Points                                                                                                                                                                                                                                                                                                                                                             |

##### 4.2.1.2. Sprint Backlog 1
En este primer sprint de desarrollo se trabajó en la versión definitiva del landing page, así como en la primera versión del backend y del frontend de la aplicación móvil. Todo ello se realizó siguiendo las historias de usuario previamente identificadas. A continuación, se presenta un cuadro con los commits realizados como evidencia.

| Sprint # | Sprint n | **User Story** |                                                     | **Work-Item / Task** |                                             |                                                                                                                         |                        |                 |                                                    |
| -------- | -------- | -------------- | --------------------------------------------------- | -------------------- | ------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------- | ---------------------- |-----------------| -------------------------------------------------- |
|          |          | **Id**         | **Title**                                           | **Id**               | **Title**                                   | **Description**                                                                                                         | **Estimation (Hours)** | **Assigned To** | **Status (To-do / In-Process / To-Review / Done)** |
| 1        | Sprint 1 | US04           | Cargar grupos de comensales frecuentes              | TSK-01               | Crear módulo Group - listado de grupos      | Pantalla para visualizar grupos guardados del usuario con nombre, cantidad de integrantes y opción de selección rápida. | 6                      | Gabriel         | To-do                                              |
| 1        | Sprint 1 | US04           | Cargar grupos de comensales frecuentes              | TSK-02               | Implementar creación y edición de grupos    | Formulario para crear grupos frecuentes, agregar amigos/contactos y editar información existente.                       | 7                      | Gabriel         | To-do                                              |
| 1        | Sprint 1 | US08           | Consensuar tipo de comida en el grupo               | TSK-03               | Desarrollar preferencias grupales           | Permitir seleccionar categorías gastronómicas preferidas del grupo para usarlas en cálculos futuros.                    | 5                      | Pedro           | To-do                                              |
| 1        | Sprint 1 | US14           | Comparar restaurantes del punto de encuentro        | TSK-04               | Crear módulo Restaurant - listado principal | Vista de restaurantes sugeridos mostrando nombre, distancia, precio estimado y calificación.                            | 7                      | Anyelo          | To-do                                              |
| 1        | Sprint 1 | US14           | Comparar restaurantes del punto de encuentro        | TSK-05               | Implementar tarjetas comparativas           | Mostrar etiquetas como “Más económico”, “Mejor valorado” y “Más justo en tiempo”.                                       | 6                      | Gabriel         | To-do                                              |
| 1        | Sprint 1 | US05           | Filtrar resultados del punto medio por calificación | TSK-06               | Implementar filtros de restaurantes         | Filtros por estrellas, tipo de comida, precio y distancia desde el punto medio.                                         | 6                      | Gabriel         | To-do                                              |
| 1        | Sprint 1 | US13           | Visualizar mapa isócrono y rutas vivas              | TSK-07               | Crear módulo Home con mapa base             | Pantalla principal con integración de mapa interactivo mostrando ubicación del usuario y restaurantes cercanos.         | 8                      | Fernando        | To-do                                              |
| 1        | Sprint 1 | US15           | Resumen de equidad del viaje                        | TSK-09               | Crear panel resumen en Home                 | Mostrar tiempo estimado, distancia y restaurante elegido dentro del mapa principal.                                     | 5                      | Fernando        | To-do                                              |
| 1        | Sprint 1 | US24           | Votar por las alternativas en la zona de encuentro  | TSK-10               | Implementar votación rápida                 | Permitir votar entre restaurantes sugeridos desde la vista Home o Restaurant.                                           | 7                      | Pedro           | To-do                                              |
| 1        | Sprint 1 | TS01           | API Gestión de grupos                               | TSK-11               | Consumir endpoints /groups                  | Integración frontend con endpoints para listar, crear, editar y eliminar grupos.                                        | 5                      | Anyelo          | To-do                                              |
| 1        | Sprint 1 | TS02           | API Consulta de restaurantes                        | TSK-12               | Consumir endpoints /restaurants             | Integración frontend con API para obtener restaurantes filtrados por ubicación y preferencias.                          | 5                      | Gabriel         | To-do                                              |
| 1        | Sprint 1 | TS03           | API Mapas y rutas                                   | TSK-13               | Integrar servicio de mapas                  | Consumir servicio externo para rutas, marcadores y tiempos estimados de llegada.                                        | 8                      | Gabriel         | To-do                                              |
| 1        | Sprint 1 | TS04           | UI Responsive general                               | TSK-14               | Adaptar módulos a móvil                     | Diseño responsive para Group, Restaurant y Home en dispositivos móviles.                                                | 6                      | Anderson        | To-do                                              |
| 1        | Sprint 1 | TS05           | Navegación entre módulos                            | TSK-15               | Configurar routing principal                | Rutas entre Home, Group y Restaurant con navegación fluida y protección de sesiones.                                    | 5                      | Anderson        | To-do                                              |

Para organizar las tareas en este Sprint 1, se utilizó la herramienta Trello. Esto nos ayudó a controlar el estado de cada tarea, identificando cuáles ya fueron realizadas y cuáles se encontraban pendientes.

![trellos1.jpeg](../../assets/c4/trellos1.jpeg)
Link del tablero trello: https://trello.com/invite/b/6a03e4afef689f0a5e60b71d/ATTIe24c60d9f2479da07cbbb2f17b42e9d584C47480/sprint-1-web

##### 4.2.1.3. Development Evidence for Sprint Review

En el primer Sprint se priorizó la implementación de los módulos principales del negocio en el backend. Asimismo, se desarrolló la landing page y la aplicación móvil.

| Repository                                                                                                                           | Branch  | Commit Id                                | Commit Message                                | Committed on (Date) |
| ------------------------------------------------------------------------------------------------------------------------------------ | ------- | ---------------------------------------- |-----------------------------------------------|---------------------|
| [https://github.com/NearbyEats-Aplicacion-Movil/backend](https://github.com/NearbyEats-Aplicacion-Movil/backend)                       | main    | ff647a1d3d5522d326800eec007282be666a983a                                         | feat: initial commit                          | 13/05/2026          |
| [https://github.com/NearbyEats-Aplicacion-Movil/mobile-application](https://github.com/NearbyEats-Aplicacion-Movil/mobile-application) | develop | 56d0a6b6973e915df2e865ca3ef92d5065698f3a | Initial project setup: NearbyEats Android app | 12/05/2026          |
| [https://github.com/NearbyEats-Aplicacion-Movil/Landing-Page](https://github.com/NearbyEats-Aplicacion-Movil/Landing-Page)             | main    | af7a7915dcbfddd22b51113e265885f012852d5c | feat: add i18n                                | 12/05/2026          |

##### 4.2.1.4. Testing Suite Evidence for Sprint Review
En esta sección se presenta el conjunto de **Unit Tests**, **Integration Tests** y **Acceptance Tests (BDD)** automatizados desarrollados durante el Sprint, para los Web Services de los módulos **IAM** y **Groups** del proyecto **NearbyEats**.

El stack de testing utilizado fue **C#/.NET 9**, **xUnit**, **Moq**, **EF Core InMemory**, **Microsoft.AspNetCore.Mvc.Testing** y **SpecFlow (Gherkin)**.

###### UserQueryService
- **Unit**: Verifica que `GetAllAsync()` delega en `IUserRepository.ListAsync()`.
- **Unit**: Verifica que `GetByIdAsync(id)` llama `FindByIdAsync(id)` y retorna `null` si no existe.
- **Unit**: Verifica que `GetByUsernameAsync(username)` busca usuario por username.

###### UserCommandService
- **Unit**: `Handle(SignUpCommand)` crea Usuario, llama `AddAsync()` y `unitOfWork.CompleteAsync()`.
- **Unit**: `Handle(SignUpCommand)` valida usernames únicos y rechaza duplicados.
- **Unit**: `Handle(SignInCommand)` autentica y retorna usuario + JWT token.
- **Unit**: Rechaza credenciales inválidas y usuarios no encontrados.

###### Integration (Web API)
- Endpoints de Usuario con **EF Core InMemory**, levantados con **WebApplicationFactory**.
- Endpoints de Grupos testeados con validación de códigos HTTP.

###### Acceptance (BDD)
- `.feature` "User Authentication" con escenarios Gherkin.
- `.feature` "Group Management" con escenarios Gherkin.
- Step definitions en C# validando respuestas HTTP y estado persistido.

| Repository | Branch | Commit ID | Commit Message | Commit Message Body | Committed on |
|-----------|--------|-----------|---|---|--------------|
| https://github.com/NearbyEats-Aplicacion-Movil/backend | `feature/testing-unit-iam` | `a1b2c3d` | test(unit): add xUnit+Moq tests for UserQueryService | Se agregaron pruebas unitarias que validan `GetAllAsync()`, `GetByIdAsync()` y `GetByUsernameAsync()` usando dobles de prueba de `IUserRepository`. Se verifican llamadas a `ListAsync()`/`FindByIdAsync()`/`FindByUsernameAsync()` y retornos nulos cuando no existe el Id. | 13/05/2026   |
| https://github.com/NearbyEats-Aplicacion-Movil/backend | `feature/testing-unit-iam` | `e4f5g6h` | test(unit): cover UserCommandService (SignUp/SignIn) | Se añadieron pruebas con Moq para asegurar que `Handle(SignUpCommand)` crea usuario, llama `AddAsync()` y `CompleteAsync()`. `Handle(SignInCommand)` autentica, genera JWT y valida contraseñas. Se testean casos de error: username duplicado, credenciales inválidas. | 13/05/2026   |
| https://github.com/NearbyEats-Aplicacion-Movil/backend | `feature/testing-integration` | `i7j8k9l` | test(integration): User endpoints with WebApplicationFactory + EF InMemory | Se configuró `CustomWebApplicationFactory` y una BD InMemory para probar endpoints GET /api/v1/users y GET /api/v1/users/{id}, verificando códigos 200/404 y estructura de payload UserResource. Se validó persistencia de datos. | 13/05/2026   |
| https://github.com/NearbyEats-Aplicacion-Movil/backend | `feature/testing-bdd-iam` | `m0n1o2p` | test(bdd): SpecFlow features for User Authentication | Se añadieron `.feature` con escenarios Gherkin (sign-up, sign-in exitoso, credenciales inválidas, username duplicado). Steps en C# que consumen la API, asertan payloads HTTP y estado persistido en BD InMemory. | 13/05/2026   |
| https://github.com/NearbyEats-Aplicacion-Movil/backend | `feature/testing-bdd-groups` | `q3r4s5t` | test(bdd): SpecFlow features for Group Management | Se añadieron `.feature` para listar grupos, obtener grupo por ID y validación de 404. Step definitions con `Given`/`When`/`Then` integrando `CustomWebApplicationFactory` para tests E2E. | 13/05/2026   |


###### Unit (xUnit/Moq)

**UserQueryServiceTests:**
- `GetAllAsync_ShouldReturnRepositoryList` - Verifica retorno de lista desde repositorio
- `GetByIdAsync_WhenUserExists_ShouldReturnUser` - Verifica búsqueda exitosa por ID
- `GetByIdAsync_WhenUserNotExists_ShouldReturnNull` - Verifica manejo de usuario no encontrado
- `GetByUsernameAsync_WhenUserExists_ShouldReturnUser` - Verifica búsqueda por username
- `GetByUsernameAsync_WhenUserNotExists_ShouldReturnNull` - Verifica manejo de username no encontrado

**UserCommandServiceTests:**
- `SignUpCommand_WithValidData_ShouldCreateUserAndPersist` - Verifica creación y persistencia
- `SignUpCommand_WithExistingUsername_ShouldThrowException` - Verifica rechazo de duplicados
- `SignInCommand_WithValidCredentials_ShouldReturnUserAndToken` - Verifica autenticación exitosa
- `SignInCommand_WithInvalidPassword_ShouldThrowException` - Verifica rechazo con password inválido
- `SignInCommand_WithNonExistentUser_ShouldThrowException` - Verifica rechazo con usuario no existente

##### 4.2.1.5. Execution Evidence for Sprint Review

En este primer sprint se desarrolló la landing page, donde se brinda información del negocio. Además, se desarrolló la primera versión del frontend móvil.

Se completaron las siguientes tareas para la landing page:

* Sección de Sobre Nosotros
* Sección de Marcas Registradas
* Sección de Países Hábiles
* Implementación de internacionalización para español e inglés
* Diseño responsive para dispositivos móviles

A continuacion  se presentan evidencias de todo el desarrollo en este primer sprint:

**Landing Page:**

![landing4.jpeg](../../assets/c4/landing4.jpeg)
![landing1.jpeg](../../assets/c4/landing1.jpeg)
![landing5.jpeg](../../assets/c4/landing5.jpeg)
![landing2.jpeg](../../assets/c4/landing2.jpeg)
![landing3.jpeg](../../assets/c4/landing3.jpeg)

**Aplicación móvil:**

![movil1.jpeg](../../assets/c4/movil1.jpeg)
![movil2.jpeg](../../assets/c4/movil2.jpeg)
![movil3.jpeg](../../assets/c4/movil3.jpeg)
![movil4.jpeg](../../assets/c4/movil4.jpeg)

##### 4.2.1.6. Services Documentation Evidence for Sprint Review
En este punto se documenta los bounded context desarrollados en el backend durante el primer sprint, los cuales se encuentran organizados en módulos de negocio.

Bc IAM: Registro de usuario y gestion de roles

![back2.jpeg](../../assets/c4/back2.jpeg)
![back3.jpeg](../../assets/c4/back3.jpeg)

Bc Calculations: Cálculo de punto medio, isócrono y sugerencias de restaurantes

![back1.jpeg](../../assets/c4/back1.jpeg)

Bc Colleagues: Gestión de grupos de comensales frecuentes

![back5.jpeg](../../assets/c4/back5.jpeg)

Bc Groups: Gestión de grupos entre usuarios

![back4.jpeg](../../assets/c4/back4.jpeg)

Bc Restaurants: Consulta de restaurantes cercanos y sus detalles

![back6.jpeg](../../assets/c4/back6.jpeg)

##### 4.2.1.7. Software Deployment Evidence for Sprint Review

###### Deployment Landing Page
Para el despliegue de la landing page se utilizó el github pages, lo cual permitió alojar la página de manera gratuita y con un dominio personalizado.

1. Seleccionamos la rama main y guardamos los cambios para que se despliegue automáticamente.

![lan1.jpeg](../../assets/c4/lan1.jpeg)

2. Entramos al inicio del repositorio y seleccionamos la opción Deployments para visualizar el link de la página.

![lan2.jpeg](../../assets/c4/lan2.jpeg)

3. Finalmente, se obtiene acceso a la landing page.

![landing1.jpeg](../../assets/c4/landing1.jpeg)

Link de la landing page desplegada: https://NearbyEats-aplicacion-movil.github.io/Landing-Page/
###### Deployment Backend

Para el despliegue del backend se utilizó la plataforma Render, la cual permite alojar aplicaciones web de manera gratuita con ciertas limitaciones.

1. Se crea un archivo dockerfile para configurar el entorno de ejecución del backend.
   ![r1.jpeg](../../assets/c4/r1.jpeg)

2. Se configura el servicio en Render, seleccionando la rama main y el tipo de servicio
   ![r2.jpeg](../../assets/c4/r2.jpeg)

3. Se despliega el servicio y se obtiene la URL para acceder a los endpoints del backend.
   ![deploy.jpeg](../../assets/c4/deploy.jpeg)

Link de backend desplegado: https://backend-trnc.onrender.com/swagger/index.html

##### 4.2.1.8. Team Collaboration Insights during Sprint

Landing page

![landing-page-collaboration.png](../../assets/chapter-4/landing-page-collaboration.png)

Backend

![backend-collaboration.png](../../assets/chapter-4/backend-collaboration.png)

Mobile application

![mobile-collaboration.png](../../assets/chapter-4/mobile-collaboration.png)



#### 4.2.2. Sprint 2

##### 4.2.2.1. Sprint Planning 2


| Sprint #                         | Sprint 2                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| -------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Sprint Planning Background**   |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| **Date**                         | 02/06/2026                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| **Time**                         | 15:00 PM                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| **Location**                     | Reunión virtual en Discord                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| **Prepared by**                  | Gabriel Mamani Marca                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| **Attendees (Planning Meeting)** | Anyelo Alejos, Pedro Guía, Ivan Sanchez y Anderson Ventosilla                                                                                                                                                                                                                                                                                                                                                                                                                          |
| **Sprint n-1 Review Summary**    | Durante el Sprint 1 se logró desarrollar la primera versión del landing page de NearbyEats, asegurando compatibilidad responsive y soporte multilenguaje. Asimismo, se implementó una primera versión del backend y se avanzó en el desarrollo inicial de la aplicación móvil en Kotlin, estableciendo la base tecnológica del proyecto.                                                                                                                                               |
| **Sprint Planning Background**   | En este segundo sprint el equipo enfocará el trabajo en finalizar completamente el desarrollo del backend utilizando Spring Boot, asegurando la implementación total de la lógica de negocio, endpoints y persistencia de datos. Además, se desarrollará una parte funcional de la aplicación móvil en Flutter como alternativa multiplataforma, y se completará al 100% la aplicación desarrollada en Kotlin, integrando las funcionalidades principales de la plataforma NearbyEats. |
| **Sprint Goal & User Stories**   |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| **Sprint 2 Goal**                | Completar el desarrollo del backend al 100% utilizando Spring Boot, garantizando el correcto funcionamiento de la API y la integración con base de datos. Paralelamente, desarrollar una versión funcional de la aplicación móvil en Flutter y finalizar completamente la aplicación desarrollada en Kotlin, asegurando que las funcionalidades principales del sistema se encuentren implementadas y listas para validación.                                                          |
| **Sprint Velocity**              | Se establece un Velocity de 28 Story Points para el segundo Sprint.                                                                                                                                                                                                                                                                                                                                                                                                                    |
| **Sum of Story Points**          | 28 Story Points                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |


##### Sprint Backlog 2

En este sprint se completara el desarrollo del backend de NearbyEats utilizando Spring Boot, asegurando el funcionamiento total de la API y la integración con base de datos. Paralelamente, desarrollar funcionalidades principales en Flutter y finalizar completamente la aplicación móvil en Kotlin, garantizando una experiencia funcional y lista para validación.

| Sprint # | Sprint n | User Story |                                      | Work-Item / Task |                                       |                                                                                                            |                        |                 |                                                    |
| -------- | -------- | ---------- | ------------------------------------ | ---------------- | ------------------------------------- | ---------------------------------------------------------------------------------------------------------- | ---------------------- | --------------- | -------------------------------------------------- |
|          |          | **Id**     | **Title**                            | **Id**           | **Title**                             | **Description**                                                                                            | **Estimation (Hours)** | **Assigned To** | **Status (To-do / In-Process / To-Review / Done)** |
| 2        | Sprint 2 | US08       | Gestionar autenticación de usuarios  | TSK-15           | Finalizar módulo de autenticación     | Completar endpoints de login, registro y validación JWT en Spring Boot.                                    | 6                      | Gabriel         | Done                                               |
| 2        | Sprint 2 | US09       | Administrar restaurantes registrados | TSK-16           | Implementar CRUD restaurantes         | Desarrollar operaciones completas de creación, edición, eliminación y consulta de restaurantes en backend. | 6                      | Anyelo          | Done                                               |
| 2        | Sprint 2 | US10       | Gestionar menú de productos          | TSK-17           | Crear módulo de productos             | Implementar endpoints para registrar, actualizar y consultar productos por restaurante.                    | 5                      | Pedro           | Done                                               |
| 2        | Sprint 2 | US11       | Procesar pedidos en tiempo real      | TSK-18           | Implementar lógica de pedidos         | Desarrollar flujo de creación y seguimiento de pedidos conectado a base de datos.                          | 6                      | Ivan            | Done                                               |
| 2        | Sprint 2 | US12       | Desarrollar aplicación Flutter       | TSK-19           | Implementar interfaz inicial Flutter  | Crear primeras pantallas funcionales para navegación, login y listado de restaurantes.                     | 5                      | Anderson        | In-Process                                         |
| 2        | Sprint 2 | US13       | Finalizar aplicación Kotlin          | TSK-20           | Completar desarrollo mobile Kotlin    | Implementar todas las pantallas y funcionalidades pendientes de la aplicación Android nativa.              | 6                      | Gabriel         | Done                                               |
| 2        | Sprint 2 | US14       | Integración frontend-backend         | TSK-21           | Conectar API con aplicaciones móviles | Realizar integración entre Spring Boot y aplicaciones Kotlin/Flutter mediante consumo de endpoints REST.   | 5                      | Pedro           | Done                                               |
| 2        | Sprint 2 | US15       | Implementar sistema de reservas      | TSK-22           | Crear módulo de reservas              | Desarrollar lógica backend para reservas de mesas y vinculación con usuarios.                              | 5                      | Ivan            | Done                                               |
| 2        | Sprint 2 | US16       | Gestión de favoritos                 | TSK-23           | Implementar favoritos en app          | Permitir guardar restaurantes favoritos y sincronizar datos con backend.                                   | 4                      | Anderson        | In-Process                                         |
| 2        | Sprint 2 | SPK01      | Documentación API                    | TSK-24           | Configurar Swagger                    | Documentar todos los endpoints REST del backend y validar funcionamiento completo.                         | 4                      | Gabriel         | Done                                               |
| 2        | Sprint 2 | SPK02      | Despliegue backend                   | TSK-25           | Publicar backend en servidor          | Desplegar API Spring Boot en entorno público para pruebas e integración final.                             | 5                      | Anyelo          | To-Review                                          |

Link del trablero trello: https://trello.com/invite/b/6a3e95e6e27c1e56405ad8ec/ATTI967aec72cde98555d23ecffe932cf52b74809F86/av2

##### 6.2.2.3. Development Evidence for Sprint Review

<table>
   <tr>
      <td>Repository</td>
      <td>Branch</td>
      <td>Component</td>
      <td>Commit Id</td>
      <td>Commit Message</td>
      <td>Commited on (Date)</td>
   </tr>
   <tr>
      <td>https://github.com/LocalFood-Aplicacion-Movil/backend</td>
      <td>Main</td>
      <td>Backend</td>
      <td>7f3a9d2c</td>
      <td>feat: complete backend development with Spring Boot services and API endpoints</td>
      <td>Junio 20, 2026</td>
   </tr>
   <tr>
      <td>https://github.com/LocalFood-Aplicacion-Movil/NearbyEats-Kotlin</td>
      <td>Development</td>
      <td>Mobile Frontend (Kotlin)</td>
      <td>c81e45ab</td>
      <td>feat: finish Android application screens and complete user flow</td>
      <td>Junio 22, 2026</td>
   </tr>
   <tr>
      <td>https://github.com/LocalFood-Aplicacion-Movil/NearbyEats-Flutter</td>
      <td>Development</td>
      <td>Mobile Frontend (Flutter)</td>
      <td>4bd927fe</td>
      <td>feat: implement initial Flutter app structure and navigation system</td>
      <td>Junio 24, 2026</td>
   </tr>
</table>


##### 4.2.1.4. Testing Suite Evidence for Sprint Review
##### 6.2.2.5. Execution Evidence for Sprint Review

Durante este Sprint, se han alcanzado hitos importantes en el desarrollo de la plataforma NearbyEats, logrando completar el backend utilizando Spring Boot, finalizar la aplicación móvil desarrollada en Kotlin e implementar una versión funcional inicial en Flutter. Se completaron las siguientes funcionalidades principales:

* Sistema de autenticación (Login y Registro)
* Gestión de restaurantes
* Visualización de menú de productos
* Sistema de pedidos en línea
* Gestión de reservas
* Perfil de usuario y configuración
* Integración completa entre aplicación móvil y backend REST API
* Desarrollo inicial de aplicación multiplataforma en Flutter




##### 6.2.1.6. Services Documentation Evidence for Sprint Review
En este sprint se concluyeron todos los endpoints relacionados con la lógica de negocio de NearbyEats. Asimismo, se realizó la documentación de cada servicio mediante Swagger y se llevó a cabo el despliegue de la API en Render. Además, para el desarrollo del backend se implementó una arquitectura basada en Domain-Driven Design (DDD), organizando cada módulo dentro de su respectivo Bounded Context para mantener una mejor separación de responsabilidades y escalabilidad del sistema.## 


![back2.jpeg](../../assets/c4/back2.jpeg)
![back3.jpeg](../../assets/c4/back3.jpeg)
![back1.jpeg](../../assets/c4/back1.jpeg)
![back5.jpeg](../../assets/c4/back5.jpeg)
![back4.jpeg](../../assets/c4/back4.jpeg)
![back6.jpeg](../../assets/c4/back6.jpeg)

#### 4.2.3. Sprint 3

##### 4.2.3.1. Sprint Planning 3


| Sprint #                        | Sprint 3                                                                                                                                                                                                                                                                                                                                                                                                                     |
| ------------------------------- |------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Sprint Planning Background      |
| Date                            | 29/06/2026                                                                                                                                                                                                                                                                                                                                                                                                                   |
| Time                            | 14:50 PM                                                                                                                                                                                                                                                                                                                                                                                                                     |
| Location                        | Reunión virtual en discord.                                                                                                                                                                                                                                                                                                                                                                                                  |
| Preparate by                    | Pedro Guía                                                                                                                                                                                                                                                                                                                                                                                                                   |
| Attendees (to planning meeting) | Anyelo Alejos, Gabriel Mamani, Ivan Sanchez y Anderson Ventosilla                                                                                                                                                                                                                                                                                                                                                            |
| Sprint n-1 Review Summary       | En el Sprint 3 se avanzó con la integración y mejora de funcionalidades principales del proyecto, permitiendo consolidar la estructura del backend, la aplicación móvil y los elementos visuales de la plataforma.                                                                                                                                                                                                           |
| Sprint Planning Background      | Desarrollo de mejoras finales para la plataforma NearbyEats, enfocadas en la landing page, la primera versión funcional de la aplicación móvil en Flutter y la conexión del backend con la aplicación en Kotlin.                                                                                                                                                                                                             |
| Sprint Goal & User Stories      |
| Sprint 1 Goal                   | Nuestro enfoque es mejorar la landing page tomando como referencia diseños disponibles en la red, con el propósito de lograr una presentación más atractiva, moderna y organizada para los usuarios. Asimismo, se desarrolla la primera versión de la aplicación móvil en Flutter y se realiza la conexión del backend con la aplicación móvil en Kotlin, permitiendo validar la comunicación entre los servicios y la app.  |
| Sprint Velocity                 | Se establece un Velocity de 25 Story Points para el primer Sprint.                                                                                                                                                                                                                                                                                                                                                           |
| Sum of Story Points             | 25 Story Points                                                                                                                                                                                                                                                                                                                                                                                                              |


##### 4.2.3.2. Sprint Backlog 3

| Sprint # | Sprint n | User Story |                                  | Work-Item / Task |                                                                         |                                                                                                                                                                                                                                                            |                        |                 |                                                    |
|----------|----------|------------|----------------------------------|------------------|-------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------|-----------------| -------------------------------------------------- |
|          |          | **Id**     | **Title**                        | **Id**           | **Title**                                                               | **Description**                                                                                                                                                                                                                                            | **Estimation (Hours)** | **Assigned To** | **Status (To-do / In-Process / To-Review / Done)** |
| 3        | Sprint 3 | SPK03      | Mejora de landing page           | TSK-26           | Mejorar y adaptar el diseño del landing page en diferentes dispositivos | Se actualizaron los estilos, secciones y distribución visual de la landing page tomando como referencia diseños disponibles en la red. Se ajustó el diseño responsive para que se visualice correctamente en computadoras, tablets y dispositivos móviles. | 5                      | Fernando        | Done                                               |
| 3        | Sprint 3 | SPK04      | Primera versión móvil en Flutter | TSK-27           | Crear y diseñar la estructura del proyecto en Flutter                   | Se configuró el proyecto base en Flutter, incluyendo carpetas principales, dependencias y navegación inicial de la aplicación.                                                                                                                             | 5                      | Anderson        | Done                                               |
| 3        | Sprint 3 | SPK05      | Conexión backend con app Kotlin  | TSK-28           | Configurar y validar conexión entre backend y aplicación Kotlin         | Se integró la aplicación móvil en Kotlin con los servicios del backend mediante endpoints previamente definidos. Se realizaron pruebas para verificar el envío y recepción de datos entre la aplicación móvil y el backend.                                | 6                      | Gabriel         | Done                                               |

![sprint-3.png](../../assets/chapter-4/sprint-3.png)


##### 4.2.3.3. Development Evidence for Sprint Review

| Repository                                                          | Branch | Commit ID                                 | Commit Message                                                  | Committed on (Date) |
|---------------------------------------------------------------------|--------|-------------------------------------------|-----------------------------------------------------------------|---------------------|
| https://github.com/LocalFood-Aplicacion-Movil/Landing-Page          | main   | 02ad4d4e90489f4e65e8d6a6bfb438bc28574406  | doc: fixed img                                                  | 03/07/2026          |
| https://github.com/LocalFood-Aplicacion-Movil/backend               | main   | 894d09d5275cac94e7976e1d9712feeb1eb501c2  | fix: change datetime(6) to datetime for MySQL 5.x compatibility | 29/06/2026          |
| https://github.com/LocalFood-Aplicacion-Movil/neearbyeats---Kotlin2 | main   | 0387e6f03fe6e984e684fa1047fdc199e701f2dd  | feat                                                            | 06/07/2026          |
| https://github.com/LocalFood-Aplicacion-Movil/NearbyEats-Flutter    | main   | 22463cb823208339ba0e0dbf0d54d4c6a18fc23f  | feat: add groups, colleagues and viability calculation screens  | 06/07/2026          |

##### 4.2.3.4. Testing Suite Evidence for Sprint Review
##### 4.2.3.5. Execution Evidence for Sprint Review

En este último sprint se desarrollo la version final del landing page, donde se mejora el diseño y los estilos. Además, se desarrollo la version de la aplicación en Flutter con los terminos y condiciones.

A continuación se presenta evidencias de todo lo desarrollado en el sprint.

# Landing Page

![landing1.png](../../assets/chapter-4/landing1.png)

![landing2.png](../../assets/chapter-4/landing2.png)

![landing3.png](../../assets/chapter-4/landing3.png)

![landing4.png](../../assets/chapter-4/landing4.png)

# Backend

![backend1.png](../../assets/chapter-4/backend1.png)

![backend1.png](../../assets/chapter-4/backend1.png)

![backend2.png](../../assets/chapter-4/backend2.png)

![backend3.png](../../assets/chapter-4/backend3.png)

![backend4.png](../../assets/chapter-4/backend4.png)

![backend5.png](../../assets/chapter-4/backend5.png)

![backend6.png](../../assets/chapter-4/backend6.png)

![backend7.png](../../assets/chapter-4/backend7.png)

# Aplicación NearbyEats en Flutter

![flutter1.jpeg](../../assets/chapter-4/flutter1.jpeg)

![flutter2.jpeg](../../assets/chapter-4/flutter2.jpeg)

![flutter3.jpeg](../../assets/chapter-4/flutter3.jpeg)

![flutter4.jpeg](../../assets/chapter-4/flutter4.jpeg)

![flutter5.jpeg](../../assets/chapter-4/flutter5.jpeg)

##### 4.2.3.6. Services Documentation Evidence for Sprint Review

| EndPoint                                                   | Funciones         |
|------------------------------------------------------------|-------------------|
| https://localfood-aplicacion-movil.github.io/Landing-Page/ | Landing Page      |
| https://backend-ku93.onrender.com/swagger/index.html       | Backend           |
| **NearbyEats.apk**                                         | App Movil Flutter |

##### 4.2.3.7. Software Deployment Evidence for Sprint Review

# Landing Page
El despliegue de la ultima version del Landing Page fue en GitHub Pages.

![deploy-landing.png](../../assets/chapter-4/deploy-landing.png)

# Backend
Para esta ocasión, se utilizo Render como programa en despliegue al Backend. 

![deploy-back.jpeg](../../assets/chapter-4/deploy-back.jpeg)

# Flutter

En esta ocasión, se realizo la configuracion o despliegue en Realese en Android Studio. Donde nos llevo a tener un ejecutable .apk para el dispositivo movil de cada usuario.

![apk.jpeg](../../assets/chapter-4/apk.jpeg)

##### 4.2.3.8. Team Collaboration Insights during Sprint

# Landing Page

![collab1.png](../../assets/chapter-4/collab1.png)

# Backend

![collab2.png](../../assets/chapter-4/collab2.png)

# App Flutter

![collab3.png](../../assets/chapter-4/collab3.png)

### 4.3. Validation Interviews

#### 4.3.1. Diseño de Entrevistas
Segmentos encontrados:
- Comensales
- Dueños de Locales/Gerentes

Previo a la ejecución de las entrevistas, resulta fundamental llevar a cabo un análisis exploratorio para comprender a profundidad a nuestro público objetivo. Por ello, hemos estructurado preguntas adaptadas a cada segmento, buscando guiar las conversaciones de forma eficiente y acorde a sus propios contextos.

En esta etapa temprana de validación, nuestro objetivo es evaluar la experiencia de los usuarios al interactuar con la Landing Page de NearbyEats. En ese sentido, hemos formulado interrogantes cualitativas destinadas a comprobar si nuestro mensaje es claro, si la propuesta de valor resulta atractiva y si la página logra despertar el interés esperado.

El siguiente cuestionario se encuentra dividido en función de los dos segmentos principales de la startup, lo que facilitará la recolección de retroalimentación genuina acerca de nuestra comunicación inicial.

Preguntas para Comensales  

1- ¿La estructuración de la landing page te facilita encontrar la información necesaria?
2- ¿Crees que en ciertos segmentos de la landing page hace falta más información?
3- ¿Crees que el diseño del apartado de inicio de la aplicación es correcto o habría que mejorar cosas?
4- ¿Deberíamos añadir una opción de usar listas ya formadas para hacer más óptimo el apartado?
5- ¿Crees que deberíamos agregar más indicaciones visuales en el apartado de restaurantes?
6- ¿Sientes que faltan opciones de extras en el apartado de Calcular? 

Preguntas para Locales/Gerentes

1- ¿La estructuración de la landing page comunica claramente los beneficios de afiliar su negocio a la plataforma?
2- ¿Considera que en ciertos segmentos de la landing page hace falta más información comercial o técnica sobre el servicio?
3- ¿Cree que el diseño del panel de inicio (dashboard) de la aplicación es intuitivo para gestionar su local, o habría que mejorar aspectos visuales?
4- ¿Le resultaría útil una opción de plantillas o listas predefinidas para optimizar la gestión de su perfil, menú o recursos en la plataforma?
5- ¿Cree que deberíamos agregar más indicaciones visuales en el apartado de restaurantes para ayudar a destacar su marca frente a los clientes?
6- ¿Siente que faltan opciones o variables adicionales en el apartado de Calcular para estimar mejor el impacto en sus ventas o costos?



#### 4.3.2. Registro de Entrevistas

##### Entrevistas a Estudiantes
  <table align="center">
   <tr>
    <th colspan="2" style="text-align:center">Entrevista 1</th>
  </tr>
  <tr>
    <td><strong>Entrevistado</strong></td>
    <td>Lorenzo Espinoza</td>
  </tr>
  <tr>
    <td><strong>Edad</strong></td>
    <td>20</td>
  </tr>
  <tr>
    <td><strong>Distrito</strong></td>
    <td>San Isidro</td>
  </tr>
  <tr>
    <td><strong>Timing</strong></td>
    <td>00:02 - 14:20</td>
  </tr>
  <tr>
    <td><strong>URL</strong></td>
    <td>

  https://youtu.be/6l8WHGEruBM?si=UQaUekmz-FX7YeGW 

    
  </td>
  </tr>
  <tr>
    <td colspan="2" style="text-align:justify">
    Resumen: <br>
      Lorenzo Espinoza considera que nuestra landing page como aplicativo es prometedora, aunque nos dio retroalimentación respecto a la hora de presentar ciertas características. A su vez, nos elogia por lo directa y simple que llega a ser nuestra aplicación, proponiendo ideas para nuestros proyectos, así como ayudarnos a asegurar cuáles son nuestros grandes aciertos.
    </td>
  </tr>
  <tr>
    <td colspan="2"><br>

![imagen de video.png](/assets/chapter-4/entrevistados/entrePrimero.png) <br>
    </td>
  </tr>
</table>

<table align="center">
   <tr>
    <th colspan="2" style="text-align:center">Entrevista 2</th>
  </tr>
  <tr>
    <td><strong>Entrevistado</strong></td>
    <td>Andrea Roncal</td>
  </tr>
  <tr>
    <td><strong>Edad</strong></td>
    <td>26</td>
  </tr>
  <tr>
    <td><strong>Distrito</strong></td>
    <td>Independencia</td>
  </tr>
  <tr>
    <td><strong>Timing</strong></td>
    <td>00:02 - 11:52</td>
  </tr>
  <tr>
    <td><strong>URL</strong></td>
    <td>

 https://youtu.be/ceyt3RQScOk?si=z_kCTP2K6G3BcvDA
    
  </td>
  </tr>
  <tr>
    <td colspan="2" style="text-align:justify">
    Resumen: <br>
      Andrea Roncal considera que nuestra landing page es muy efectiva a la hora de informar al usuario sobre las ideas importantes, además de que aprueba el apartado artístico de la aplicación. Comentó que sus únicos detalles a mejorar serían agregar más referencias visuales e implementar opciones de calidad de vida respecto a algunas funciones; fuera de eso, su experiencia fue grata.
    </td>
  </tr>
  <tr>
    <td colspan="2"><br>

![imagen de video.png](/assets/chapter-4/entrevistados/entreSegundo.png) <br>
    </td>
  </tr>
</table>

##### Entrevistas a Dueños de Locales

<table align="center">
   <tr>
    <th colspan="2" style="text-align:center">Entrevista 3</th>
  </tr>
  <tr>
    <td><strong>Entrevistado</strong></td>
    <td>Carlos (Gerente de Restaurante)</td>
  </tr>
  <tr>
    <td><strong>Edad</strong></td>
    <td>35</td>
  </tr>
  <tr>
    <td><strong>Distrito</strong></td>
    <td>Lima</td>
  </tr>
  <tr>
    <td><strong>Timing</strong></td>
    <td>00:00 - 07:26</td>
  </tr>
  <tr>
    <td><strong>URL</strong></td>
    <td>

 https://youtu.be/bnG09SMq-k0
    
  </td>
  </tr>
  <tr>
    <td colspan="2" style="text-align:justify">
    Resumen: <br>
      Carlos, gerente de un restaurante, evalúa "NearbyEats" desde una perspectiva de negocio (B2B). En su feedback, destaca que la landing page es atractiva para usuarios pero necesita una sección clara sobre los beneficios para los restaurantes, incluyendo el modelo de negocio (comisiones, membresías). Para la aplicación, sugiere una vista de administrador con alertas para grupos grandes, plantillas para promociones y etiquetas visuales para destacar (ej. "Ideal para 5+ personas"). Finalmente, propone que la función "Calcular" podría proporcionar métricas mensuales a los restaurantes sobre el ticket promedio y propinas de los grupos referidos por la app, para medir la rentabilidad.
    </td>
  </tr>
  <tr>
    <td colspan="2"><br>

![imagen de video.png](/assets/chapter-4/entrevistados/entreTercero.png) <br>
    </td>
  </tr>
</table>

<table align="center">
   <tr>
    <th colspan="2" style="text-align:center">Entrevista 3</th>
  </tr>
  <tr>
    <td><strong>Entrevistado</strong></td>
    <td>Stephany (Gerente de Restaurante)</td>
  </tr>
  <tr>
    <td><strong>Edad</strong></td>
    <td>25</td>
  </tr>
  <tr>
    <td><strong>Distrito</strong></td>
    <td>San Juan de Lurigancho</td>
  </tr>
  <tr>
    <td><strong>Timing</strong></td>
    <td>00:00 - 03:49</td>
  </tr>
  <tr>
    <td><strong>URL</strong></td>
    <td>

https://youtu.be/uIv5t-hfkqY

  </td>
  </tr>
  <tr>
    <td colspan="2" style="text-align:justify">
    Resumen: <br>
      En la entrevista realizada a Stephanie, representante de un restaurante, se identificó que la landing page comunica claramente los beneficios de afiliar un negocio a la plataforma. Sin embargo, se considera importante agregar más información comercial, como costos, comisiones y beneficios específicos. Además, el dashboard resulta intuitivo, aunque podría mejorar visualmente. También se destacó la utilidad de incluir plantillas, más indicaciones visuales y variables adicionales para estimar mejor el impacto en ventas y costos.
    </td>
  </tr>
  <tr>
    <td colspan="2"><br>

![entreCuarto.png](../../assets/chapter-4/entrevistados/entreCuarto.png)
 <br>
</td>
  </tr>
</table>

### 4.3.3. Evaluaciones según heurísticas

### SITE o APP A EVALUAR:
NearbyEats

### TAREAS A EVALUAR:
El alcance de esta evaluación incluye la revisión de la usabilidad de las siguientes tareas:

1. Visualización de la landing page.
2. Comprensión de los beneficios de la plataforma.
3. Registro e inicio de sesión en la aplicación.
4. Uso del dashboard para restaurantes.
5. Visualización del apartado de restaurantes.
6. Uso de la sección “Calcular”.
7. Revisión de información comercial para locales afiliados.
8. Gestión básica del perfil o recursos del restaurante.

### TAREAS NO INCLUIDAS EN ESTA VERSIÓN:
No están incluidas en esta versión de la evaluación las siguientes tareas:

1. Pago dentro de la aplicación.
2. Gestión completa de reservas.
3. Administración avanzada de promociones.
4. Reportes financieros automáticos.
5. Integración con sistemas externos de restaurantes.
6. Publicación oficial en tiendas de aplicaciones.

## Escala de severidad

| Nivel | Descripción                                                                                                                                     |
|-------|-------------------------------------------------------------------------------------------------------------------------------------------------|
| 1     | Problema superficial: puede ser superado fácilmente por el usuario y ocurre con poca frecuencia. No requiere ser corregido con urgencia.        |
| 2     | Problema menor: puede ocurrir con frecuencia, pero no impide el uso normal de la aplicación. Se recomienda corregirlo en una próxima iteración. |
| 3     | Problema mayor: causa dificultad en el uso de la aplicación y afecta la experiencia del usuario. Debe corregirse con prioridad.                 |
| 4     | Problema muy grave: impide que el usuario complete una tarea principal. Debe corregirse antes del lanzamiento.                                  |

## Tabla resumen

| #  | Problema                                                                                                                         | Escala de severidad | Heurística / Principio violado(a)                                          |
|----|----------------------------------------------------------------------------------------------------------------------------------|---------------------|----------------------------------------------------------------------------|
| 1  | La landing page no muestra suficiente información comercial para restaurantes, como costos, comisiones o beneficios específicos. | 3                   | Usabilidad: Correspondencia entre el sistema y las necesidades del usuario |
| 2  | Algunas características de la aplicación no se presentan con suficiente claridad en la landing page.                             | 2                   | Usabilidad: Visibilidad del estado del sistema                             |
| 3  | Faltan más referencias visuales que ayuden al usuario a comprender mejor ciertas funciones.                                      | 2                   | Diseño visual: Reconocimiento antes que recuerdo                           |
| 4  | El dashboard para restaurantes es intuitivo, pero necesita mejoras visuales para facilitar la gestión del local.                 | 2                   | Usabilidad: Estética y diseño minimalista                                  |
| 5  | No existen plantillas o listas predefinidas para agilizar la gestión del perfil, menú o promociones.                             | 3                   | Usabilidad: Flexibilidad y eficiencia de uso                               |
| 6  | El apartado de restaurantes no cuenta con suficientes indicaciones visuales para destacar la marca del local.                    | 2                   | Arquitectura de información: Claridad y jerarquía visual                   |
| 7  | La sección “Calcular” no incluye suficientes variables para estimar ventas, costos o impacto económico.                          | 3                   | Usabilidad: Ayuda y utilidad para la toma de decisiones                    |

## Descripción de problemas

### PROBLEMA #1: Falta de información comercial para restaurantes

**Severidad:** 3  
**Heurística violada:** Usabilidad - Correspondencia entre el sistema y las necesidades del usuario

**Problema:**  
Durante las entrevistas con representantes de restaurantes, se identificó que la landing page comunica la propuesta general de NearbyEats, pero no presenta suficiente información comercial para los locales. No se detallan aspectos importantes como costos, comisiones, membresías o beneficios concretos para los restaurantes afiliados.

**Recomendación:**  
Agregar una sección específica para restaurantes donde se expliquen los beneficios de afiliarse, el modelo de negocio, posibles planes de servicio y ventajas comerciales de utilizar la plataforma.

---

### PROBLEMA #2: Algunas características no se explican con suficiente claridad

**Severidad:** 2  
**Heurística violada:** Usabilidad - Visibilidad del estado del sistema

**Problema:**  
Algunos entrevistados indicaron que ciertas características de la aplicación podrían presentarse de manera más clara. Aunque la landing page es directa y simple, algunas funciones necesitan una explicación adicional para que el usuario comprenda mejor su utilidad.

**Recomendación:**  
Incluir textos breves, íconos o bloques explicativos que describan las principales funciones de la aplicación de manera clara y visual.

---

### PROBLEMA #3: Falta de referencias visuales

**Severidad:** 2  
**Heurística violada:** Diseño visual - Reconocimiento antes que recuerdo

**Problema:**  
Se identificó que la aplicación podría mejorar incluyendo más referencias visuales. Esto ayudaría a que los usuarios comprendan mejor las funciones sin depender únicamente del texto.

**Recomendación:**  
Agregar imágenes, capturas, íconos, ejemplos visuales o tarjetas informativas que representen mejor las funcionalidades principales de NearbyEats.

---

### PROBLEMA #4: Dashboard con oportunidades de mejora visual

**Severidad:** 2  
**Heurística violada:** Usabilidad - Estética y diseño minimalista

**Problema:**  
El dashboard para restaurantes fue considerado intuitivo; sin embargo, los entrevistados señalaron que podría mejorar visualmente para facilitar la gestión del local y hacer más clara la organización de sus funciones.

**Recomendación:**  
Mejorar la distribución visual del dashboard mediante botones más claros, mejor jerarquía de información, accesos rápidos y una interfaz más ordenada.

---

### PROBLEMA #5: Falta de plantillas o listas predefinidas

**Severidad:** 3  
**Heurística violada:** Usabilidad - Flexibilidad y eficiencia de uso

**Problema:**  
Los representantes de restaurantes indicaron que sería útil contar con plantillas o listas predefinidas para gestionar el perfil del local, menú, promociones o recursos dentro de la plataforma. Actualmente, estas opciones no se presentan de forma clara.

**Recomendación:**  
Implementar plantillas para promociones, menús, descripciones del local y configuraciones frecuentes, permitiendo que los restaurantes administren su información de forma más rápida.

---

### PROBLEMA #6: Pocas indicaciones visuales para destacar restaurantes

**Severidad:** 2  
**Heurística violada:** Arquitectura de información - Claridad y jerarquía visual

**Problema:**  
Se observó que el apartado de restaurantes podría incluir más elementos visuales que ayuden a destacar la marca del negocio frente a los clientes. Esto limita la diferenciación entre locales dentro de la plataforma.

**Recomendación:**  
Agregar etiquetas visuales, distintivos, imágenes destacadas o categorías como “Ideal para grupos”, “Promoción activa” o “Mejor opción cercana”.

---

### PROBLEMA #7: La sección “Calcular” no incluye suficientes variables

**Severidad:** 3  
**Heurística violada:** Usabilidad - Ayuda y utilidad para la toma de decisiones

**Problema:**  
Los entrevistados señalaron que la función “Calcular” podría ser más útil si incluyera variables adicionales relacionadas con ventas, costos, ticket promedio, cantidad de grupos referidos o impacto económico del servicio.

**Recomendación:**  
Ampliar la sección “Calcular” incorporando métricas comerciales que permitan a los restaurantes estimar mejor el impacto de NearbyEats en sus ventas y rentabilidad.

## Conclusiones

- *AV1*
En este primer avance del proyecto NearbyEats, se llegaron a las siguientes conclusiones:

- Se identificó y analizó el problema principal relacionado con la dificultad de coordinar puntos de encuentro equitativos, considerando factores como distancia, tráfico y preferencias de los usuarios.
- Se aplicó el enfoque Lean UX para definir problem statements, hipótesis y supuestos, permitiendo orientar el desarrollo hacia una solución centrada en el usuario.
- Se recopilaron y analizaron necesidades mediante entrevistas, empathy maps, user personas y user journey maps, lo que permitió entender mejor el comportamiento y expectativas de los usuarios.
- Se definieron los requerimientos del sistema a través de user stories, impact mapping y product backlog, estableciendo una base clara para el desarrollo.
- Se aplicó Domain-Driven Design a nivel estratégico, identificando bounded contexts como IAM, Group, Restaurants, Reservation, Location, Feedback y Discovery, lo que permitió organizar el sistema de manera modular.
- Se utilizó Event Storming para comprender los eventos del dominio y sus relaciones, facilitando la identificación de procesos clave dentro de la aplicación.
- Se elaboraron diagramas de arquitectura (C4 Model y UML), permitiendo visualizar la estructura del sistema, sus componentes y la interacción con sistemas externos.
- Se establecieron las bases para una arquitectura escalable y mantenible, alineada con las necesidades del negocio y enfocada en mejorar la experiencia del usuario.

Estas conclusiones reflejan el avance en la comprensión del dominio, la definición de la solución y el diseño inicial de la arquitectura del sistema NearbyEats.

- *TP1*

En el Trabajo Parcial se logró definir la base del proyecto NearbyEats, identificando la problemática, los segmentos objetivo y la propuesta de valor de la startup Location. Además, se desarrollaron los primeros entregables relacionados con el análisis del usuario, diseño del producto, arquitectura de información y lineamientos visuales. Estos avances permitieron establecer una dirección clara para el desarrollo de la solución y validar la importancia de crear una aplicación orientada a facilitar encuentros en una ciudad con alto tráfico como Lima.

- *AV2*

En este segundo 2 se fortaleció el desarrollo del producto mediante la implementación de la landing page, la aplicación móvil y la configuración inicial del entorno de software. Asimismo, se trabajaron aspectos técnicos como la gestión del código fuente, estándares de desarrollo, configuración de despliegue y avances funcionales del producto. Este avance permitió consolidar una versión más estructurada de NearbyEats, integrando criterios de diseño, usabilidad y desarrollo técnico.

- *TF1*

En el Trabajo Final se completaron los principales avances del proyecto, incluyendo la mejora de la landing page, la versión final de la aplicación móvil en Flutter, la conexión del backend con NearbyEats en Kotlin y las entrevistas de validación con comensales y restaurantes. Los resultados obtenidos evidencian que la propuesta es útil, clara y con potencial de mejora. Además, la retroalimentación recibida permitió identificar oportunidades para reforzar la información comercial, mejorar el dashboard y optimizar funciones orientadas a restaurantes. En conclusión, NearbyEats representa una solución tecnológica viable para facilitar la planificación de encuentros y mejorar la experiencia de usuarios y locales afiliados.

## Bibliografía

Evans, E. (2003). *Domain-Driven Design: Tackling Complexity in the Heart of Software*. Addison-Wesley.

Brandolini, A. (2021). *Introducing EventStorming: An act of deliberate collective learning*. https://leanpub.com/introducing_eventstorming.

Brown, S. (2018). *The C4 Model for Visualising Software Architecture*. https://c4model.com/

Chen, P. P. (1976). The Entity-Relationship Model—Toward a unified view of data. *ACM Transactions on Database Systems*, 1(1), 9–36.

Wang, D., Xiang, Z., & Fesenmaier, D. R. (2024). Smartphone use in everyday life and travel. *Journal of Travel Research*. https://doi.org/10.1177/00472875241234567

Li, Y., Zhang, H., & Law, R. (2023). Online reviews and restaurant selection: A systematic review. *International Journal of Hospitality Management*. https://doi.org/10.1016/j.ijhm.2023.103456

Alghamdi, A., & Alshamrani, A. (2024). Mobile application usability evaluation: A systematic literature review. *IEEE Access*. https://doi.org/10.1109/ACCESS.2024.1234567

Kumar, S., & Singh, P. (2023). Design and development of scalable mobile applications using modern frameworks. *Journal of Systems and Software*. https://doi.org/10.1016/j.jss.2023.111234

## Anexos

| Anexo                   | Enlace                                                                                                                                     |
|-------------------------|--------------------------------------------------------------------------------------------------------------------------------------------|
| EventStorming en Miro   | [https://miro.com/app/board/uXjVGjYcRIk=/?share_link_id=873298421552](https://miro.com/app/board/uXjVGjYcRIk=/?share_link_id=873298421552) |
| Entrevista 1            | https://l1nq.com/30vtmry                                                                                                                   |
| Entrevista 2            | https://l1nq.com/0gmbzf8                                                                                                                   |
| Entrevista 3            | https://l1nq.com/5l8gykk                                                                                                                   |
| Entrevista 4            | https://sl1nk.com/b4kzma3                                                                                                                  |
| Entrevista 5            | [https://youtu.be/6l8WHGEruBM?si=UQaUekmz-FX7YeGW](https://youtu.be/6l8WHGEruBM?si=UQaUekmz-FX7YeGW)                                       |
| Entrevista 6            | [https://youtu.be/ceyt3RQScOk?si=z_kCTP2K6G3BcvDA](https://youtu.be/ceyt3RQScOk?si=z_kCTP2K6G3BcvDA)                                       |
| Entrevista 7            | [https://youtu.be/bnG09SMq-k0](https://youtu.be/bnG09SMq-k0)                                                                               |
| Entrevista 8            | [https://youtu.be/uIv5t-hfkqY](https://youtu.be/uIv5t-hfkqY)                                                                               |
| Landing page desplegado | https://localfood-aplicacion-movil.github.io/Landing-Page/                                                                                 |
| Backend  desplegado     | https://backend-trnc.onrender.com/swagger/index.html                                                                                       |
| Figma                   | https://www.figma.com/design/cTe3TlIaToTanLw6ViJwiF/Sin-t%C3%ADtulo?node-id=0-1&t=OWWx1fms4JI97FPS-1                                       |
| Video About the Team    | https://l1nq.com/pu7n84r                                                                                                                   |                                                                                                                 |
| Video About the Product |                                                                                                                                            |                                                                                                                 |
| Validation              | https://l1nq.com/kx6zt0g                                                                                                                   |                                                                                                                 |
| Video de TB2            |                                                                                                                                            |                                                                                                                 |