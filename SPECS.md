# AgentHub — Especificación del Panel de Administración

## 1. Descripción del producto

AgentHub es una plataforma SaaS que permite a empresas contratar y gestionar agentes de inteligencia artificial equipados con distintas skills.

El objetivo de este proyecto es construir un prototipo frontend completamente funcional del panel interno de administración de AgentHub.

El usuario principal es un administrador de la plataforma que necesita supervisar usuarios, agentes, skills, contratos y errores del sistema desde una única interfaz.

El prototipo utilizará datos hardcodeados y no tendrá conexión con backend ni API.

---

# 2. Stack tecnológico

El proyecto debe utilizar exclusivamente:

- HTML5 semántico.
- Tailwind CSS cargado mediante CDN.
- JavaScript vanilla.
- Datos hardcodeados.

No utilizar:

- React.
- Vue.
- Angular.
- jQuery.
- Bootstrap.
- Librerías externas de componentes.
- Herramientas de build.
- Backend.
- APIs externas.
- Archivos CSS personalizados.
- Estilos mediante atributos `style`.

Toda la presentación visual debe implementarse mediante clases utilitarias de Tailwind CSS.

---

# 3. Estructura general

La aplicación debe tener una estructura de panel administrativo formada por:

- Sidebar persistente a la izquierda.
- Área principal de contenido a la derecha.
- Barra superior dentro del contenido principal.
- Contenido central correspondiente a la sección activa.

La aplicación debe incluir seis secciones:

1. Dashboard.
2. Gestión de usuarios.
3. Gestión de agentes.
4. Skills.
5. Contrataciones de agentes.
6. Log de errores.

La navegación lateral debe permitir cambiar entre las seis vistas.

La sección activa debe estar visualmente diferenciada.

El diseño debe ser usable en escritorio y tablet y adaptarse correctamente a pantallas pequeñas.

---

# 4. Componentes reutilizables

## Sidebar

Debe incluir:

- Identidad visual de AgentHub.
- Enlaces a las seis secciones.
- Icono por sección.
- Estado visual de sección activa.
- Comportamiento persistente durante la navegación entre vistas.

## Barra superior

Debe incluir:

- Nombre de la sección actual.
- Toggle de modo claro/oscuro.

El estado del modo visual debe mantenerse al cambiar entre secciones.

## Tarjeta de métrica

Componente reutilizable que incluye:

- Icono.
- Etiqueta.
- Valor principal.

## Badge de estado

Se utilizará para representar estados como:

- Activo.
- Inactivo.
- Fallando.
- Resuelto.
- Pendiente.

Los estados deben diferenciarse visualmente mediante color.

## Dropdown de acciones

Botón representado mediante `⋮`.

Al pulsarlo se muestra un pequeño menú contextual.

El dropdown debe:

- Abrirse al hacer clic.
- Cerrarse al volver a pulsarlo.
- Cerrarse al hacer clic fuera.
- Mostrar únicamente las acciones correspondientes al elemento seleccionado.

## Modal

Componente overlay reutilizable.

Debe incluir:

- Backdrop.
- Contenedor central.
- Título.
- Contenido.
- Botón para cerrar.

Debe cerrarse:

- Mediante el botón de cierre.
- Al hacer clic sobre el backdrop.

## Lista de skills colapsable

Lista inicialmente oculta.

Debe:

- Expandirse al pulsar su control.
- Mostrar las skills asociadas.
- Volver a ocultarse al pulsar de nuevo.
- Mostrar una transición visual suave.

---

# 5. Dashboard

La vista Dashboard debe ofrecer una visión general del estado de AgentHub.

### Especificaciones

1. Mostrar cuatro tarjetas de métricas en una cuadrícula responsive.

2. Las métricas serán:

   - Ingresos totales del mes.
   - Pérdidas por descuentos y cupones.
   - Agentes activos.
   - Agentes fallando.

3. Cada tarjeta debe incluir:

   - Icono.
   - Nombre de la métrica.
   - Valor hardcodeado claramente visible.

4. Debajo de las métricas debe existir un área de ancho completo que represente un gráfico de actividad semanal.

5. El gráfico no necesita una librería ni datos reales: debe representarse mediante un placeholder visual claramente identificado como actividad semanal.

6. La cuadrícula debe adaptarse al tamaño de pantalla sin provocar scroll horizontal.

---

# 6. Gestión de usuarios

La sección debe permitir visualizar usuarios registrados en AgentHub.

### Especificaciones

1. Mostrar una tabla con al menos cinco usuarios hardcodeados.

2. Cada fila debe mostrar:

   - Nombre.
   - Email.
   - Plan.
   - Estado mediante badge.

3. Cada usuario debe tener un dropdown `⋮`.

4. El dropdown debe contener:

   - Ver detalle.
   - Eliminar.

5. Seleccionar "Ver detalle" debe abrir un modal.

6. El modal debe mostrar el registro completo del usuario, incluyendo información adicional a la disponible directamente en la tabla.

7. El modal debe poder cerrarse mediante:

   - Botón de cierre.
   - Clic sobre el backdrop.

8. La tabla debe seguir siendo usable en pantallas pequeñas mediante una solución responsive adecuada.

---

# 7. Gestión de agentes

Esta sección debe mostrar los agentes registrados en la plataforma.

### Especificaciones

1. Mostrar al menos cuatro agentes hardcodeados.

2. Cada agente debe mostrar:

   - Nombre.
   - Propietario.
   - Estado.
   - Control para mostrar las skills.
   - Dropdown de acciones.

3. Los estados disponibles serán:

   - Activo.
   - Inactivo.
   - Fallando.

4. Las skills deben estar colapsadas por defecto.

5. Pulsar el control de skills debe expandirlas mediante una transición visual.

6. Volver a pulsar el control debe colapsarlas.

7. Cada agente debe tener un dropdown con:

   - Configurar.
   - Eliminar.

8. "Configurar" debe abrir un modal.

9. El modal debe incluir el prompt de sistema del agente dentro de un `<textarea>` editable.

10. Los nombres de los agentes utilizados deben coincidir con los utilizados en Contrataciones y Log de errores cuando corresponda.

---

# 8. Skills

La sección mostrará el catálogo de capacidades que pueden asignarse a los agentes.

### Especificaciones

1. Mostrar una explicación breve indicando que una skill es una capacidad que puede habilitarse en un agente para realizar determinados tipos de tareas.

2. Mostrar al menos cuatro skills.

3. Cada skill debe mostrar:

   - Nombre.
   - Descripción.
   - Número de agentes que actualmente la tienen habilitada.

4. Cada skill debe incluir un dropdown `⋮`.

5. El dropdown debe incluir:

   - Ver detalle.
   - Eliminar.

6. "Ver detalle" debe abrir un modal con información ampliada sobre la skill.

7. Las skills deben presentarse mediante tarjetas o una lista clara y visualmente consistente.

---

# 9. Contrataciones de agentes

Esta vista representa los contratos de alquiler de agentes realizados por clientes.

### Especificaciones

1. Mostrar una tabla con al menos cuatro contratos hardcodeados.

2. Cada contrato debe mostrar:

   - Cliente.
   - Agente contratado.
   - Skills contratadas.
   - Fecha de inicio.
   - Fecha de finalización.
   - Importe total pagado.

3. Cada fila debe incluir un dropdown de acciones.

4. El dropdown debe contener "Ver detalle".

5. "Ver detalle" debe abrir un modal.

6. El modal debe mostrar:

   - Cliente.
   - Agente.
   - Periodo del contrato.
   - Importe total.
   - Lista desglosada de skills contratadas.
   - Precio individual de cada skill.

7. Los nombres de agentes deben mantenerse consistentes con Gestión de agentes y Log de errores.

---

# 10. Log de errores

Esta sección permite revisar errores producidos durante la ejecución de agentes.

### Especificaciones

1. Mostrar al menos seis errores hardcodeados.

2. Cada entrada debe mostrar:

   - Timestamp.
   - Nombre del agente.
   - Tipo de error.
   - Descripción breve.

3. El tipo o gravedad del error debe representarse mediante badges con diferentes colores.

4. Cada entrada debe tener un dropdown `⋮`.

5. Las acciones disponibles deben ser:

   - Ver detalle.
   - Marcar como resuelto.

6. "Ver detalle" debe abrir un modal.

7. El modal debe mostrar la traza completa del error y datos adicionales relevantes.

8. "Marcar como resuelto" debe modificar visualmente el estado de ese error en la interfaz.

9. Los nombres de agentes utilizados deben coincidir con los de Gestión de agentes.

---

# 11. Modo claro y oscuro

El panel debe incluir un toggle global para cambiar entre modo claro y oscuro.

### Comportamiento

1. El control estará situado en la barra superior.

2. Debe utilizar las utilidades `dark:` de Tailwind.

3. El cambio debe afectar a toda la interfaz.

4. El estado elegido debe mantenerse mientras el usuario cambia entre las seis secciones.

5. La información debe mantener suficiente contraste y legibilidad en ambos modos.

---

# 12. Comportamiento de dropdowns

Todos los dropdowns deben seguir el mismo comportamiento.

1. Se abren al pulsar el botón `⋮`.

2. Solo debe permanecer abierto el dropdown correspondiente al elemento seleccionado.

3. Deben cerrarse al hacer clic fuera de su área.

4. Las opciones deben ser claramente seleccionables.

---

# 13. Comportamiento de modales

Todos los modales deben seguir el mismo patrón.

1. Mostrar un backdrop que cubra la interfaz.

2. Mostrar el contenido del modal centrado.

3. Incluir título y contenido correspondiente al elemento seleccionado.

4. Poder cerrarse mediante el botón de cierre.

5. Poder cerrarse haciendo clic en el backdrop.

El comportamiento debe funcionar al menos en:

- Gestión de usuarios.
- Gestión de agentes.
- Skills.
- Contrataciones.
- Log de errores.

---

# 14. Responsive

La aplicación debe ser usable desde móvil hasta escritorio.

### Escritorio

- Sidebar visible.
- Área principal ocupando el espacio restante.
- Tarjetas de métricas distribuidas en cuadrícula.
- Tablas aprovechando el ancho disponible.

### Tablet

- Mantener la navegación accesible.
- Reducir columnas cuando sea necesario.
- Evitar desbordamientos horizontales innecesarios.

### Móvil

- El contenido debe adaptarse a una sola columna cuando corresponda.
- Las tablas deben permitir visualizar su contenido sin romper el layout.
- Los modales deben caber dentro del viewport.
- Los controles interactivos deben seguir siendo accesibles.

---

# 15. Datos de demostración

Todos los datos serán hardcodeados.

Los mismos nombres y entidades deben mantenerse coherentes entre secciones.

Ejemplo de agentes que pueden reutilizarse:

- Atlas.
- Nova.
- Orion.
- Luna.

Ejemplo de skills:

- Navegación web.
- Lectura de documentos.
- Gestión de calendario.
- Análisis de datos.

Ejemplo de clientes:

- Acme Corp.
- Northstar Labs.
- BluePeak.
- Vertex Solutions.

Los valores pueden ser ficticios, pero deben parecer datos realistas de una plataforma SaaS.

---

# 16. Criterios de aceptación

El prototipo se considerará terminado cuando se cumplan todos los siguientes puntos:

1. `SPECS.md` aparece en el historial de Git en un commit anterior a cualquier archivo HTML del proyecto.

2. Las seis secciones están implementadas y accesibles desde la navegación lateral.

3. El sidebar muestra claramente cuál es la sección activa.

4. Toda la interfaz utiliza Tailwind mediante CDN.

5. No existen archivos CSS personalizados ni estilos inline.

6. Toda la interactividad se implementa con JavaScript vanilla.

7. Dashboard contiene las cuatro métricas requeridas y el placeholder del gráfico semanal.

8. Gestión de usuarios contiene al menos cinco usuarios.

9. Gestión de agentes contiene al menos cuatro agentes.

10. Skills contiene al menos cuatro skills.

11. Contrataciones contiene al menos cuatro contratos.

12. Log de errores contiene al menos seis errores.

13. Todos los dropdowns se abren correctamente.

14. Los dropdowns se cierran al hacer clic fuera de ellos.

15. "Ver detalle" abre modales funcionales en al menos cuatro secciones diferentes.

16. Todos los modales pueden cerrarse mediante su botón de cierre.

17. Todos los modales pueden cerrarse haciendo clic en el backdrop.

18. Las skills de los agentes están colapsadas inicialmente.

19. Las listas de skills pueden expandirse y volver a colapsarse mediante clic.

20. La expansión de skills tiene una transición visual.

21. "Configurar" en Gestión de agentes abre un modal con el prompt del agente dentro de un `<textarea>` editable.

22. El modo oscuro/claro modifica toda la interfaz.

23. El estado del modo oscuro/claro se mantiene al cambiar entre secciones.

24. Los nombres y datos compartidos son coherentes entre Gestión de agentes, Contrataciones y Log de errores.

25. Se utilizan correctamente elementos HTML semánticos como `<nav>`, `<header>`, `<main>`, `<section>` y `<table>`.

26. El diseño es usable en escritorio, tablet y móvil.

27. No existen errores JavaScript en la consola durante las interacciones obligatorias.

28. El repositorio final es público y contiene tanto `SPECS.md` como el prototipo HTML commiteado.
