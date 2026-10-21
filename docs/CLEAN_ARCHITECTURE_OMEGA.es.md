# Arquitectura del proyecto — Clean Architecture

Este documento explica cómo está organizado el proyecto, por qué se eligió esta organización y qué contiene cada carpeta. Está dirigido tanto a visitantes que desean entender el funcionamiento general como a desarrolladores que quieren contribuir o mantener la aplicación.

La aplicación sigue una **Clean Architecture**: el núcleo del software está aislado de los detalles técnicos, de las interfaces de usuario y de las dependencias externas. Esta separación hace que el proyecto sea más legible, más fácil de probar, de mantener y de evolucionar.

---

## 1. Principio general

La aplicación está dividida en capas, cada una con un papel específico.

La idea central es sencilla:

```text
La interfaz solicita una acción.
La aplicación orquesta esa acción.
El dominio aplica las reglas de negocio.
Los puertos definen lo que la aplicación necesita.
La infraestructura proporciona las implementaciones concretas.
```

Por ello, la lógica importante del proyecto no depende directamente de:

- la terminal;
- la interfaz gráfica;
- una base de datos;
- la red;
- el sistema de archivos;
- una biblioteca externa;
- una herramienta del sistema.

Esta independencia permite reemplazar una parte del software sin reescribir todo lo demás.

---

## 2. Vista general

```text
[NOMBRE_DEL_PROYECTO]/
└── src/
    └── [nombre_del_proyecto]/
        ├── app/              Bootstrap, ciclo de vida e inyección de dependencias
        ├── core/             Capacidades, enumeraciones y excepciones transversales
        ├── domain/           Lógica de negocio pura
        ├── application/      Casos de uso: commands y queries
        ├── infrastructure/   Backends, almacenamiento, exportaciones, logs, sondas del sistema…
        ├── ports/            Contratos Protocol / ABC
        ├── interfaces/       CLI y TUI
        ├── plugins/          Extensiones integradas
        └── shared/           Parsing, red, formateo y utilidades transversales
```

---

## 3. Esquema de dependencias

Las dependencias siempre deben ir en la misma dirección:

```text
interfaces
    ↓
application
    ↓
domain
    ↑
ports
    ↑
infrastructure
```

En la práctica:

- `interfaces/` puede llamar a `application/`.
- `application/` puede llamar a `domain/` y utilizar los contratos definidos en `ports/`.
- `domain/` no depende ni de `application/`, ni de `infrastructure/`, ni de `interfaces/`.
- `infrastructure/` implementa los contratos definidos en `ports/`.
- `app/` ensambla las capas y proporciona las dependencias necesarias.

Regla esencial:

> El dominio nunca conoce la infraestructura.  
> La infraestructura conoce los puertos, pero el dominio no conoce la infraestructura.

---

## 4. Carpeta `app/`

### Rol

La carpeta `app/` es el **punto de ensamblaje** de la aplicación.

Contiene:

- el arranque del programa;
- el ciclo de vida;
- el contenedor de inyección de dependencias;
- la construcción de los objetos necesarios para el funcionamiento;
- la elección de las implementaciones concretas;
- la inicialización de la configuración;
- la conexión entre las capas.

### Ejemplo de responsabilidades

```text
app/
├── bootstrap.py
├── container.py
└── lifecycle.py
```

| Archivo | Rol |
|---|---|
| `bootstrap.py` | Inicia la aplicación y elige la interfaz que se debe lanzar |
| `container.py` | Crea y conecta las dependencias |
| `lifecycle.py` | Gestiona el arranque, la detención y la limpieza |

### Regla

`app/` no contiene lógica de negocio.

No decide:

- qué es una regla de negocio;
- cómo se debe calcular un dato;
- cómo se debe analizar una solicitud;
- cómo se debe exportar un archivo.

Solo ensambla los componentes existentes.

---

## 5. Carpeta `core/`

### Rol

La carpeta `core/` contiene el **vocabulario transversal** del proyecto.

Agrupa elementos compartidos por varias capas que no constituyen, por sí mismos, una regla de negocio.

Puede contener:

- capacidades;
- enumeraciones;
- constantes;
- excepciones transversales;
- tipos comunes;
- información sobre la plataforma;
- definiciones de niveles o estados.

### Ejemplo

```text
core/
├── capabilities.py
├── constants.py
├── enums.py
└── exceptions.py
```

| Archivo | Rol |
|---|---|
| `capabilities.py` | Describe las capacidades disponibles o activables |
| `constants.py` | Contiene las constantes del proyecto |
| `enums.py` | Define los estados, tipos o niveles posibles |
| `exceptions.py` | Define los errores transversales |

### Regla

`core/` debe mantenerse ligero y estable.

No debe contener:

- lógica de negocio compleja;
- llamadas de red;
- acceso al disco;
- interfaz de usuario;
- dependencias directas de bibliotecas externas.

---

## 6. Carpeta `domain/`

### Rol

La carpeta `domain/` es el **núcleo del proyecto**.

Contiene la lógica de negocio pura: las reglas, los conceptos y los cálculos que definen realmente lo que hace la aplicación.

Puede contener:

- entidades;
- value objects;
- políticas;
- reglas de negocio;
- servicios del dominio;
- cálculos;
- validaciones de negocio;
- modelos de datos de negocio.

### Ejemplo

```text
domain/
├── entities/
├── value_objects/
├── policies/
└── services/
```

| Elemento | Rol |
|---|---|
| Entidad | Objeto de negocio con identidad |
| Value object | Valor inmutable y validado |
| Política | Regla de negocio reutilizable |
| Servicio del dominio | Lógica de negocio que no pertenece a una sola entidad |

### Reglas estrictas

La carpeta `domain/`:

- no accede al disco;
- no realiza llamadas de red;
- no ejecuta comandos del sistema;
- no accede a una base de datos;
- no importa la interfaz de usuario;
- no importa la infraestructura;
- no depende de una biblioteca técnica externa cuando esto puede evitarse.

El dominio debe poder probarse sin servidor, sin archivos, sin red y sin interfaz.

---

## 7. Carpeta `application/`

### Rol

La carpeta `application/` orquesta los casos de uso.

Responde a la pregunta:

> «¿Qué ocurre cuando el usuario solicita esta acción?»

Contiene:

- commands;
- queries;
- casos de uso;
- orquestadores;
- gestores de acciones;
- la coordinación entre el dominio y los puertos.

### Distinción entre commands y queries

| Tipo | Objetivo | Modifica datos |
|---|---|---|
| Command | Ejecutar una acción | Sí |
| Query | Leer o calcular información | No |

Ejemplos:

| Command | Query |
|---|---|
| Aplicar una configuración | Leer la configuración actual |
| Lanzar un análisis | Obtener el resultado de un análisis |
| Exportar un informe | Listar los elementos disponibles |
| Purgar datos | Consultar un historial |

### Ejemplo

```text
application/
├── commands/
│   ├── apply_config.py
│   └── export_report.py
└── queries/
    ├── get_status.py
    └── list_items.py
```

### Regla

`application/` no contiene:

- salida en la terminal;
- una interfaz Textual;
- comandos Rich;
- acceso directo a una base de datos;
- llamadas directas a herramientas externas.

Coordina, pero no implementa los detalles técnicos.

---

## 8. Carpeta `ports/`

### Rol

La carpeta `ports/` define los **contratos** que espera la aplicación.

Un puerto describe **lo que la aplicación necesita**, sin imponer cómo debe realizarse.

Generalmente contiene:

- definiciones `Protocol`;
- clases abstractas `ABC`;
- interfaces de repositorio;
- interfaces de exportación;
- interfaces de sonda;
- interfaces de servicios externos;
- interfaces de almacenamiento.

### Ejemplo

```text
ports/
├── repositories.py
├── exporters.py
├── probes.py
└── storage.py
```

| Puerto | Rol |
|---|---|
| `Repository` | Leer o almacenar datos |
| `Exporter` | Producir una salida en un formato determinado |
| `Probe` | Recopilar información del sistema o de la red |
| `Storage` | Gestionar un soporte de persistencia |

### Ejemplo conceptual

```python
class ReportExporter(Protocol):
    def export(self, report: Report, destination: Path) -> None:
        ...
```

Este contrato indica:

> «La aplicación necesita un objeto capaz de exportar un informe.»

No indica:

- si la exportación será en Markdown;
- si la exportación será en JSON;
- si el archivo se escribirá localmente;
- si la exportación se enviará por la red.

Esas decisiones pertenecen a `infrastructure/`.

### Regla

Los puertos son contratos, no implementaciones.

No deben contener:

- lógica de negocio compleja;
- acceso al disco;
- llamadas de red;
- implementaciones concretas;
- dependencias directas de bibliotecas externas.

---

## 9. Carpeta `infrastructure/`

### Rol

La carpeta `infrastructure/` contiene las **implementaciones concretas** de los puertos.

Es la capa que se comunica con el mundo exterior.

Puede contener:

- acceso a archivos;
- acceso a bases de datos;
- exportaciones en Markdown, JSON, CSV u otros formatos;
- registro de eventos;
- llamadas de red;
- sondas del sistema;
- ejecución controlada de herramientas externas;
- adaptadores para bibliotecas de terceros;
- implementaciones de repositorios;
- implementaciones de almacenamiento.

### Ejemplo

```text
infrastructure/
├── storage/
│   ├── sqlite_repository.py
│   └── json_file_repository.py
├── export/
│   ├── markdown_exporter.py
│   └── json_exporter.py
├── system/
│   ├── process_probe.py
│   └── filesystem_probe.py
└── logging/
    └── structured_logger.py
```

| Elemento | Rol |
|---|---|
| `sqlite_repository.py` | Implementa un repositorio con SQLite |
| `json_file_repository.py` | Implementa un repositorio con archivos JSON |
| `markdown_exporter.py` | Exporta un informe en Markdown |
| `json_exporter.py` | Exporta un informe en JSON |
| `process_probe.py` | Recopila información sobre procesos |
| `filesystem_probe.py` | Recopila información sobre el sistema de archivos |
| `structured_logger.py` | Produce registros estructurados |

### Regla

`infrastructure/` es la única capa autorizada a acceder directamente a:

- el sistema de archivos;
- la red;
- SQLite;
- bibliotecas externas;
- herramientas del sistema;
- subprocesos, cuando sea necesario y controlado.

Esta centralización facilita:

- las pruebas;
- la auditoría de seguridad;
- el reemplazo de un backend;
- la limitación de los efectos secundarios.

---

## 10. Carpeta `interfaces/`

### Rol

La carpeta `interfaces/` contiene los puntos de entrada visibles para el usuario.

Separa claramente:

- la CLI;
- la TUI;
- las posibles futuras interfaces web o API.

### Estructura

```text
interfaces/
├── cli/
│   ├── main.py
│   ├── commands/
│   └── rendering/
└── tui/
    ├── app.py
    ├── screens/
    └── widgets/
```

| Interfaz | Tecnología | Rol |
|---|---|---|
| `cli/` | Rich | Interfaz de línea de comandos |
| `tui/` | Textual | Interfaz interactiva en la terminal |

### CLI

La CLI es la interfaz de línea de comandos.

Permite:

- iniciar la aplicación;
- ejecutar una acción concreta;
- mostrar un resultado;
- automatizar una tarea;
- integrar la herramienta en un script;
- utilizar la aplicación de forma remota mediante SSH.

### TUI

La TUI es la interfaz interactiva en la terminal.

Permite:

- navegar por las funcionalidades;
- visualizar información;
- ejecutar acciones;
- consultar resultados;
- utilizar la aplicación sin memorizar todos los comandos.

### Regla

Las interfaces no contienen lógica de negocio.

Ellas:

- reciben una intención del usuario;
- llaman a un caso de uso en `application/`;
- muestran el resultado;
- traducen los errores en mensajes comprensibles.

No deben:

- llamar directamente a la infraestructura;
- ejecutar subprocesos;
- acceder directamente a los archivos;
- contener reglas de negocio;
- duplicar la lógica de `application/`.

---

## 11. Carpeta `plugins/`

### Rol

La carpeta `plugins/` está reservada para las **extensiones integradas**.

Permite añadir funcionalidades sin sobrecargar el núcleo del proyecto.

Por ejemplo, un plugin puede:

- añadir un tipo de exportación;
- añadir una sonda;
- añadir un comando;
- añadir una pantalla en la TUI;
- añadir una integración externa;
- añadir una capacidad opcional.

### Principio

Un plugin debe respetar las mismas reglas que el resto del proyecto:

- no elude los puertos;
- no modifica directamente el dominio;
- expone sus funcionalidades mediante contratos claros;
- permanece desactivable sin romper la aplicación.

### Estructura posible

```text
plugins/
└── [nombre_del_plugin]/
    ├── __init__.py
    ├── manifest.py
    ├── application/
    ├── infrastructure/
    └── interfaces/
```

### Regla

Un plugin es una extensión, no una puerta trasera.

Debe seguir la arquitectura general y no debe crear dependencias circulares con el núcleo del proyecto.

---

## 12. Carpeta `shared/`

### Rol

La carpeta `shared/` contiene utilidades transversales que no pertenecen ni al dominio, ni a la aplicación, ni a la infraestructura.

Agrupa funciones genéricas reutilizables.

Puede contener:

- parsing;
- utilidades de red;
- formateo;
- manipulación de texto;
- helpers de fechas;
- helpers de rutas;
- utilidades de validación genérica;
- helpers de serialización.

### Ejemplo

```text
shared/
├── parsing/
├── network/
├── formatting/
└── utils/
```

| Carpeta | Rol |
|---|---|
| `parsing/` | Análisis de texto, JSON, YAML u otros formatos |
| `network/` | Utilidades de red genéricas |
| `formatting/` | Formateo de valores, fechas, tamaños o tablas |
| `utils/` | Funciones utilitarias transversales |

### Regla

`shared/` no debe convertirse en una carpeta catch-all.

Una utilidad se coloca en `shared/` solo si es:

- reutilizable;
- genérica;
- independiente de un caso de uso concreto;
- útil para varias capas.

---

## 13. Resumen de responsabilidades

| Carpeta | Rol principal | Puede depender de | No debe depender de |
|---|---|---|---|
| `app/` | Ensamblar e iniciar la aplicación | Todas las capas | — |
| `core/` | Vocabulario, constantes, enumeraciones y excepciones | `shared/` si es necesario | `infrastructure/`, `interfaces/` |
| `domain/` | Lógica de negocio pura | `core/` | `application/`, `infrastructure/`, `interfaces/` |
| `application/` | Orquestar los casos de uso | `domain/`, `ports/`, `core/` | `infrastructure/`, `interfaces/` |
| `ports/` | Definir los contratos | `domain/` si es necesario | `infrastructure/`, `interfaces/` |
| `infrastructure/` | Implementar los puertos y comunicarse con el exterior | `ports/`, `domain/`, `core/`, `shared/` | `interfaces/` |
| `interfaces/` | Interactuar con el usuario | `application/`, `core/` | `infrastructure/` directamente |
| `plugins/` | Añadir extensiones | Según el tipo de extensión | Eludir la arquitectura |
| `shared/` | Utilidades transversales | Ninguna capa de negocio | Lógica de negocio específica |

---

## 14. Ejemplo de recorrido de una acción

Tomemos el ejemplo de un usuario que solicita exportar un informe en Markdown.

```text
1. El usuario ejecuta un comando CLI.

2. interfaces/cli/
   Recibe el comando y sus opciones.

3. interfaces/cli/
   Llama al caso de uso correspondiente en application/.

4. application/
   Valida la intención y prepara la acción.

5. application/
   Utiliza el dominio para construir o validar el informe.

6. application/
   Solicita una exportación mediante el puerto ReportExporter.

7. infrastructure/
   Proporciona la implementación MarkdownExporter.

8. infrastructure/
   Escribe el archivo Markdown en el disco.

9. interfaces/cli/
   Muestra el resultado al usuario.
```

Esquema simplificado:

```text
CLI
 ↓
Application
 ↓
Domain
 ↓
Puerto Exporter
 ↓
Infraestructura Markdown
 ↓
Archivo Markdown
```

---

## 15. ¿Por qué esta arquitectura?

### Legibilidad

Cada carpeta tiene un rol único, lo que facilita encontrar dónde añadir o corregir una funcionalidad.

### Facilidad de prueba

El dominio puede probarse sin interfaz, sin base de datos y sin acceso a la red.

### Mantenibilidad

Un cambio en la interfaz, el almacenamiento o una herramienta externa no debe obligar a reescribir la lógica de negocio.

### Seguridad

Los accesos sensibles —archivos, red, subprocesos, bases de datos— están concentrados en `infrastructure/`. Esto facilita su auditoría y control.

### Evolutividad

Se pueden añadir:

- una nueva interfaz;
- un nuevo formato de exportación;
- un nuevo backend de almacenamiento;
- un nuevo plugin;
- una nueva sonda del sistema;

sin modificar el núcleo de negocio.

### Portabilidad

La aplicación puede evolucionar hacia otros entornos, sistemas o modos de interacción sin estar ligada a una tecnología concreta.

---

## 16. Reglas para recordar

- El dominio es puro.
- La aplicación orquesta.
- Los puertos declaran necesidades.
- La infraestructura implementa.
- Las interfaces muestran y recopilan.
- `app/` ensambla.
- `core/` y `shared/` proporcionan el vocabulario y las utilidades transversales.
- Los plugins extienden sin eludir la arquitectura.

En una frase:

> **La aplicación separa lo que hace, cómo lo hace y cómo la utiliza el usuario.**
