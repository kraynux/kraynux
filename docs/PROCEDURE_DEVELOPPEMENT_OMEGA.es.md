# Procedimiento de desarrollo — [NOMBRE_DEL_PROYECTO]

| Campo | Valor |
|---|---|
| Proyecto | [NOMBRE_DEL_PROYECTO] |
| Versión objetivo | [VERSIÓN_OBJETIVO] |
| Responsable | [NOMBRE] |
| Fecha de creación | [AAAA-MM-DD] |
| Última actualización | [AAAA-MM-DD] |
| Estado general | Borrador / En curso / Validado / En producción |
| Entorno objetivo | [Linux / Debian / Servidor / Estación de trabajo] |
| Lenguaje principal | [Python / Bash / Lua / Otro] |
| Repositorio | [URL_OU_RUTA] |

## Reglas transversales

- [ ] No se escribe código antes de validar el plan definitivo.
- [ ] Toda decisión importante queda documentada.
- [ ] Toda anomalía queda registrada.
- [ ] Toda corrección se prueba.
- [ ] Todo cambio de comportamiento queda documentado.
- [ ] Se realizan copias de seguridad antes de cualquier intervención en producción.
- [ ] La IA analiza y propone; el humano decide, valida y despliega.
- [ ] El código permanece alineado con la documentación definitiva.

## Seguimiento global de las fases

| Fase | Actor | Entregable principal | Estado | Fecha de validación |
|---:|---|---|---|---|
| 1 | Humano | Necesidades y diseño | [ ] | [AAAA-MM-DD] |
| 2 | Humano | Borrador de arquitectura y plan preliminar | [ ] | [AAAA-MM-DD] |
| 3 | IA | Análisis, efectos secundarios y plan definitivo | [ ] | [AAAA-MM-DD] |
| 4 | Humano | Núcleo del proyecto codificado | [ ] | [AAAA-MM-DD] |
| 5 | IA | Auditoría de código, correcciones y pruebas | [ ] | [AAAA-MM-DD] |
| 6 | Humano | Pruebas reales en producción | [ ] | [AAAA-MM-DD] |
| 7 | IA | Plan de correcciones y codificación definitiva | [ ] | [AAAA-MM-DD] |
| 8 | Humano | Prueba definitiva | [ ] | [AAAA-MM-DD] |
| 9 | Humano | Borrador de documentación | [ ] | [AAAA-MM-DD] |
| 10 | IA | Documentación definitiva | [ ] | [AAAA-MM-DD] |
| 11 | Humano | Despliegue en producción | [ ] | [AAAA-MM-DD] |

---

# Fase 1 — Reflexión, necesidades, uso y diseño

**Actor: Humano**  
**Objetivo:** definir el problema, los usuarios, el uso real, las restricciones y los límites del proyecto.

## 1. Problema inicial

- Problema identificado: [POR COMPLETAR]
- Situación actual: [POR COMPLETAR]
- Consecuencia del problema: [POR COMPLETAR]
- Objetivo del proyecto: [POR COMPLETAR]

## 2. Usuarios objetivo

| Usuario | Necesidad principal | Nivel técnico | Uso previsto |
|---|---|---|---|
| [Usuario 1] | [POR COMPLETAR] | [Principiante / Técnico / Experto] | [POR COMPLETAR] |
| [Usuario 2] | [POR COMPLETAR] | [Principiante / Técnico / Experto] | [POR COMPLETAR] |

## 3. Escenarios de uso

### Escenario nominal

- Contexto: [POR COMPLETAR]
- Acción del usuario: [POR COMPLETAR]
- Resultado esperado: [POR COMPLETAR]

### Escenario límite

- Contexto: [POR COMPLETAR]
- Acción del usuario: [POR COMPLETAR]
- Resultado esperado: [POR COMPLETAR]

### Escenario de error

- Contexto: [POR COMPLETAR]
- Acción del usuario: [POR COMPLETAR]
- Resultado esperado: [POR COMPLETAR]

### Escenario prohibido o peligroso

- Contexto: [POR COMPLETAR]
- Comportamiento esperado: [Rechazo / Advertencia / Bloqueo / Registro]
- Justificación: [POR COMPLETAR]

## 4. Funcionalidades

### Indispensables

- [ ] [Funcionalidad 1]
- [ ] [Funcionalidad 2]
- [ ] [Funcionalidad 3]

### Útiles pero aplazables

- [ ] [Funcionalidad 1]
- [ ] [Funcionalidad 2]

### Opcionales

- [ ] [Funcionalidad 1]

### Excluidas

- [ ] [Funcionalidad excluida]
- Justificación: [POR COMPLETAR]

## 5. Restricciones

| Ámbito | Restricción | Prioridad |
|---|---|---|
| Sistema | [Linux / Debian / Versión] | [Alta / Media / Baja] |
| Lenguaje | [Python / Bash / Lua] | [Alta / Media / Baja] |
| Dependencias | [POR COMPLETAR] | [Alta / Media / Baja] |
| Rendimiento | [POR COMPLETAR] | [Alta / Media / Baja] |
| Seguridad | [POR COMPLETAR] | [Alta / Media / Baja] |
| Compatibilidad | [POR COMPLETAR] | [Alta / Media / Baja] |
| Mantenimiento | [POR COMPLETAR] | [Alta / Media / Baja] |
| Despliegue | [POR COMPLETAR] | [Alta / Media / Baja] |

## 6. Riesgos identificados

| Riesgo | Impacto | Probabilidad | Medida de prevención |
|---|---|---|---|
| [Riesgo 1] | [Bajo / Medio / Alto] | [Bajo / Medio / Alto] | [POR COMPLETAR] |
| [Riesgo 2] | [Bajo / Medio / Alto] | [Bajo / Medio / Alto] | [POR COMPLETAR] |

## 7. Decisiones tomadas

| ID | Decisión | Justificación | Fecha |
|---:|---|---|---|
| D-001 | [POR COMPLETAR] | [POR COMPLETAR] | [AAAA-MM-DD] |
| D-002 | [POR COMPLETAR] | [POR COMPLETAR] | [AAAA-MM-DD] |

## 8. Preguntas abiertas

- [ ] [Pregunta 1]
- [ ] [Pregunta 2]

## Validación de la fase 1

- [ ] El problema está claramente formulado.
- [ ] Los usuarios están identificados.
- [ ] Los escenarios de uso principales están descritos.
- [ ] Las funcionalidades indispensables están listadas.
- [ ] Los límites del proyecto son explícitos.
- [ ] Las restricciones técnicas son conocidas.
- [ ] Los riesgos principales están identificados.

**Estado:** [ ] Borrador / [ ] Validado  
**Validado por:** [NOMBRE]  
**Fecha:** [AAAA-MM-DD]

---

# Fase 2 — Borrador, componentes principales y plan de desarrollo

**Actor: Humano**  
**Objetivo:** transformar las necesidades en una arquitectura lógica y en un plan de desarrollo accionable.

## 1. Componentes principales

| Componente | Responsabilidad | No debe hacer | Prioridad |
|---|---|---|---|
| Interfaz / CLI | [POR COMPLETAR] | [POR COMPLETAR] | [Alta / Media / Baja] |
| Núcleo de negocio | [POR COMPLETAR] | [POR COMPLETAR] | [Alta / Media / Baja] |
| Configuración | [POR COMPLETAR] | [POR COMPLETAR] | [Alta / Media / Baja] |
| Modelos de datos | [POR COMPLETAR] | [POR COMPLETAR] | [Alta / Media / Baja] |
| Servicios | [POR COMPLETAR] | [POR COMPLETAR] | [Alta / Media / Baja] |
| Almacenamiento | [POR COMPLETAR] | [POR COMPLETAR] | [Alta / Media / Baja] |
| Exportación | [POR COMPLETAR] | [POR COMPLETAR] | [Alta / Media / Baja] |
| Registro de eventos | [POR COMPLETAR] | [POR COMPLETAR] | [Alta / Media / Baja] |
| Seguridad | [POR COMPLETAR] | [POR COMPLETAR] | [Alta / Media / Baja] |
| Pruebas | [POR COMPLETAR] | [POR COMPLETAR] | [Alta / Media / Baja] |

## 2. Flujo principal

```text
[Entrada del usuario]
    → [Interfaz]
    → [Validación]
    → [Núcleo de negocio]
    → [Servicios / Módulos]
    → [Resultado]
    → [Salida / Almacenamiento / Logs]
```

## 3. Módulos previstos

| Módulo | Rol | Dependencias | Prioridad |
|---|---|---|---|
| [modulo_1] | [POR COMPLETAR] | [POR COMPLETAR] | [Alta / Media / Baja] |
| [modulo_2] | [POR COMPLETAR] | [POR COMPLETAR] | [Alta / Media / Baja] |
| [modulo_3] | [POR COMPLETAR] | [POR COMPLETAR] | [Alta / Media / Baja] |

## 4. Estructura de directorios preliminar

```text
[NOMBRE_DEL_PROYECTO]/
├── src/
│   └── [nombre_del_proyecto]/
│       ├── __init__.py
│       ├── config.py
│       ├── exceptions.py
│       ├── logging.py
│       ├── models/
│       ├── core/
│       ├── services/
│       └── cli/
├── tests/
│   ├── unit/
│   └── integration/
├── docs/
├── scripts/
└── CHANGELOG.md
```

## 5. Dependencias previstas

| Dependencia | Uso | Versión mínima | Justificación |
|---|---|---|---|
| [Dependencia 1] | [POR COMPLETAR] | [POR COMPLETAR] | [POR COMPLETAR] |
| [Dependencia 2] | [POR COMPLETAR] | [POR COMPLETAR] | [POR COMPLETAR] |

## 6. Desglose del desarrollo

| Fase | Contenido | Prioridad | Estimación |
|---:|---|---|---|
| 1 | Fundamentos: estructura, configuración, errores, logs | [Alta / Media] | [Duración] |
| 2 | Modelos y contratos | [Alta / Media] | [Duración] |
| 3 | Núcleo de negocio | [Alta / Media] | [Duración] |
| 4 | Interfaz / CLI | [Alta / Media] | [Duración] |
| 5 | Almacenamiento / exportación | [Alta / Media] | [Duración] |
| 6 | Pruebas | [Alta / Media] | [Duración] |
| 7 | Documentación y empaquetado | [Alta / Media] | [Duración] |

## Validación de la fase 2

- [ ] Los componentes principales están identificados.
- [ ] Cada módulo tiene una responsabilidad clara.
- [ ] Los flujos principales están descritos.
- [ ] La estructura de directorios preliminar está definida.
- [ ] Las dependencias principales están identificadas.
- [ ] El orden de desarrollo está definido.
- [ ] No se ha iniciado ningún desarrollo.

**Estado:** [ ] Borrador / [ ] Validado  
**Validado por:** [NOMBRE]  
**Fecha:** [AAAA-MM-DD]

---

# Fase 3 — Análisis con IA, efectos secundarios y plan definitivo

**Actor: IA**  
**Objetivo:** analizar los documentos elaborados por el humano, identificar riesgos y producir un plan definitivo accionable.

## 1. Documentos analizados

- [ ] `PROJECT_00_NECESIDADES_Y_DISENO.md`
- [ ] `PROJECT_01_BORRADOR_ARQUITECTURA.md`
- [ ] `PROJECT_02_BORRADOR_PLAN_DESARROLLO.md`
- [ ] [Otro documento]

## 2. Prompt de análisis con IA

```text
Analiza este proyecto sin escribir código.

1. Detecta incoherencias.
2. Detecta funciones ausentes.
3. Detecta responsabilidades mal ubicadas.
4. Identifica posibles efectos secundarios.
5. Identifica casos de fallo.
6. Identifica riesgos de seguridad.
7. Identifica problemas de compatibilidad.
8. Propón una estructura de proyecto más robusta.
9. Propón un plan de desarrollo definitivo.
10. Indica los puntos que deben seguir siendo decisión humana.
```

## 3. Incoherencias detectadas

| ID | Descripción | Impacto | Propuesta | Decisión humana |
|---:|---|---|---|---|
| A-001 | [POR COMPLETAR] | [Bajo / Medio / Alto] | [POR COMPLETAR] | [Aceptada / Rechazada / Aplazada] |
| A-002 | [POR COMPLETAR] | [Bajo / Medio / Alto] | [POR COMPLETAR] | [Aceptada / Rechazada / Aplazada] |

## 4. Efectos secundarios identificados

| ID | Efecto secundario | Desencadenante | Impacto | Prevención | Estado |
|---:|---|---|---|---|---|
| ES-001 | [POR COMPLETAR] | [POR COMPLETAR] | [Bajo / Medio / Alto] | [POR COMPLETAR] | [Abierto / Tratado / Aceptado] |
| ES-002 | [POR COMPLETAR] | [POR COMPLETAR] | [Bajo / Medio / Alto] | [POR COMPLETAR] | [Abierto / Tratado / Aceptado] |

## 5. Casos de fallo que deben anticiparse

| Caso | Comportamiento esperado | Mensaje / log esperado | Prueba asociada |
|---|---|---|---|
| Archivo ausente | [POR COMPLETAR] | [POR COMPLETAR] | [POR COMPLETAR] |
| Permiso denegado | [POR COMPLETAR] | [POR COMPLETAR] | [POR COMPLETAR] |
| Red no disponible | [POR COMPLETAR] | [POR COMPLETAR] | [POR COMPLETAR] |
| Entrada inválida | [POR COMPLETAR] | [POR COMPLETAR] | [POR COMPLETAR] |
| Interrupción del usuario | [POR COMPLETAR] | [POR COMPLETAR] | [POR COMPLETAR] |
| Datos corruptos | [POR COMPLETAR] | [POR COMPLETAR] | [POR COMPLETAR] |

## 6. Riesgos de seguridad

| Riesgo | Escenario | Medida | Prioridad |
|---|---|---|---|
| [Riesgo 1] | [POR COMPLETAR] | [POR COMPLETAR] | [P0 / P1 / P2] |
| [Riesgo 2] | [POR COMPLETAR] | [POR COMPLETAR] | [P0 / P1 / P2] |

## 7. Plan de desarrollo definitivo

| Fase | Objetivo | Entregables | Criterio de finalización | Dependencias |
|---:|---|---|---|---|
| 1 | [POR COMPLETAR] | [POR COMPLETAR] | [POR COMPLETAR] | [Ninguna] |
| 2 | [POR COMPLETAR] | [POR COMPLETAR] | [POR COMPLETAR] | [Fase 1] |
| 3 | [POR COMPLETAR] | [POR COMPLETAR] | [POR COMPLETAR] | [Fase 2] |

## Validación de la fase 3

- [ ] Las incoherencias están tratadas o documentadas.
- [ ] Los efectos secundarios están identificados.
- [ ] Los casos de fallo están previstos.
- [ ] Los riesgos de seguridad están tratados.
- [ ] El plan definitivo está validado por el humano.
- [ ] Las decisiones finales están registradas.

**Estado:** [ ] Borrador / [ ] Validado  
**Validado por:** [NOMBRE]  
**Fecha:** [AAAA-MM-DD]

---

# Fase 4 — Codificación del núcleo del proyecto

**Actor: Humano**  
**Objetivo:** desarrollar el núcleo funcional sin añadir funcionalidades fuera del alcance.

## 1. Alcance de codificación

- [ ] Estructura del proyecto
- [ ] Entorno virtual
- [ ] Dependencias
- [ ] Configuración
- [ ] Modelos de datos
- [ ] Excepciones
- [ ] Registro de eventos
- [ ] Servicios de negocio
- [ ] Núcleo de negocio
- [ ] Pruebas unitarias
- [ ] CLI / interfaz
- [ ] Integración

## 2. Orden de implementación

| Orden | Elemento | Archivo / módulo | Estado | Commit |
|---:|---|---|---|---|
| 1 | [Elemento] | [ruta] | [ ] | [hash] |
| 2 | [Elemento] | [ruta] | [ ] | [hash] |
| 3 | [Elemento] | [ruta] | [ ] | [hash] |

## 3. Reglas de commit

- Un commit = una única intención.
- No mezclar funcionalidad, corrección y refactorización.
- Mensaje recomendado:

```text
[tipo]: [descripción breve]

[tipo] = feat, fix, refactor, test, docs, chore
```

Ejemplo:

```text
feat: añadir carga y validación de la configuración
```

## 4. Pruebas iniciales

| Prueba | Objetivo | Comando | Resultado esperado | Estado |
|---|---|---|---|---|
| [Prueba 1] | [POR COMPLETAR] | [comando] | [POR COMPLETAR] | [ ] |
| [Prueba 2] | [POR COMPLETAR] | [comando] | [POR COMPLETAR] | [ ] |

## Validación de la fase 4

- [ ] El núcleo de negocio funciona.
- [ ] Las entradas principales están validadas.
- [ ] Los errores principales están gestionados.
- [ ] Las pruebas unitarias pasan.
- [ ] El proyecto se inicia en modo básico.
- [ ] No se ha añadido ninguna funcionalidad fuera del alcance.

**Estado:** [ ] En curso / [ ] Validado  
**Validado por:** [NOMBRE]  
**Fecha:** [AAAA-MM-DD]

---

# Fase 5 — Análisis del código, corrección y pruebas con IA

**Actor: IA**  
**Objetivo:** detectar defectos, efectos secundarios y riesgos antes de las pruebas reales.

## 1. Prompt de auditoría con IA

```text
Analiza el código sin reescribirlo por completo.

1. Verifica la conformidad con el plan de desarrollo.
2. Detecta errores probables.
3. Detecta efectos secundarios.
4. Detecta fugas de recursos.
5. Detecta errores no gestionados.
6. Detecta entradas no validadas.
7. Detecta problemas de seguridad.
8. Detecta problemas de rendimiento.
9. Detecta código muerto.
10. Detecta responsabilidades mal ubicadas.
11. Propón correcciones específicas.
12. Propón las pruebas que faltan.
```

## 2. Conclusiones de la auditoría

| ID | Archivo / función | Constatación | Gravedad | Corrección propuesta | Estado |
|---:|---|---|---|---|---|
| C-001 | [ruta] | [POR COMPLETAR] | [Crítica / Mayor / Menor] | [POR COMPLETAR] | [Abierto / Corregido / Validado] |
| C-002 | [ruta] | [POR COMPLETAR] | [Crítica / Mayor / Menor] | [POR COMPLETAR] | [Abierto / Corregido / Validado] |

## 3. Pruebas añadidas

| Prueba | Objetivo | Archivo de prueba | Estado |
|---|---|---|---|
| [Prueba 1] | [POR COMPLETAR] | [ruta] | [ ] |
| [Prueba 2] | [POR COMPLETAR] | [ruta] | [ ] |

## Validación de la fase 5

- [ ] Los errores críticos están corregidos.
- [ ] Los efectos secundarios están tratados o documentados.
- [ ] Las pruebas unitarias pasan.
- [ ] Las pruebas de integración pasan.
- [ ] El código cumple el plan definitivo.
- [ ] Las correcciones se han aplicado progresivamente.

**Estado:** [ ] En curso / [ ] Validado  
**Validado por:** [NOMBRE]  
**Fecha:** [AAAA-MM-DD]

---

# Fase 6 — Estudio y pruebas reales en producción

**Actor: Humano**  
**Objetivo:** validar el software en condiciones reales y registrar todas las anomalías.

## 1. Entorno de prueba

| Elemento | Valor |
|---|---|
| Máquina | [POR COMPLETAR] |
| Sistema | [POR COMPLETAR] |
| Versión del software | [POR COMPLETAR] |
| Entorno | [Producción controlada / Staging / Servidor real] |
| Copia de seguridad realizada | [Sí / No] |
| Fecha de la copia de seguridad | [AAAA-MM-DD] |
| Método de rollback | [POR COMPLETAR] |

## 2. Escenarios probados

| ID | Escenario | Comando | Resultado esperado | Resultado obtenido | Estado |
|---:|---|---|---|---|---|
| T-001 | [POR COMPLETAR] | [comando] | [POR COMPLETAR] | [POR COMPLETAR] | [OK / KO / Parcial] |
| T-002 | [POR COMPLETAR] | [comando] | [POR COMPLETAR] | [POR COMPLETAR] | [OK / KO / Parcial] |

## 3. Cuadrícula de observación

| Ámbito | Elemento observado | Resultado | Comentario |
|---|---|---|---|
| Funcional | Función esperada | [OK / KO] | [POR COMPLETAR] |
| Interfaz | Claridad de los comandos | [OK / KO] | [POR COMPLETAR] |
| Rendimiento | Tiempo de ejecución | [OK / KO] | [POR COMPLETAR] |
| Estabilidad | Ausencia de fallos inesperados | [OK / KO] | [POR COMPLETAR] |
| Errores | Comprensibilidad de los mensajes | [OK / KO] | [POR COMPLETAR] |
| Logs | Calidad y utilidad | [OK / KO] | [POR COMPLETAR] |
| Seguridad | Comportamiento seguro | [OK / KO] | [POR COMPLETAR] |
| Compatibilidad | Funcionamiento en el objetivo real | [OK / KO] | [POR COMPLETAR] |
| Estética | Legibilidad de la salida | [OK / KO] | [POR COMPLETAR] |
| Uso real | Fluidez del recorrido | [OK / KO] | [POR COMPLETAR] |

## 4. Registro de anomalías

| ID | Fecha | Gravedad | Descripción | Logs | Hipótesis | Corrección propuesta | Estado |
|---:|---|---|---|---|---|---|---|
| BUG-001 | [AAAA-MM-DD] | [Crítica / Mayor / Menor / Estética] | [POR COMPLETAR] | [POR COMPLETAR] | [POR COMPLETAR] | [POR COMPLETAR] | [Abierto / Corregido / Validado] |
| BUG-002 | [AAAA-MM-DD] | [Crítica / Mayor / Menor / Estética] | [POR COMPLETAR] | [POR COMPLETAR] | [POR COMPLETAR] | [POR COMPLETAR] | [Abierto / Corregido / Validado] |

## Validación de la fase 6

- [ ] Todos los escenarios críticos han sido probados.
- [ ] Los errores están registrados.
- [ ] Los problemas de uso están registrados.
- [ ] Los problemas estéticos están registrados.
- [ ] Ningún error crítico bloqueante queda ignorado.

**Estado:** [ ] En curso / [ ] Validado  
**Validado por:** [NOMBRE]  
**Fecha:** [AAAA-MM-DD]

---

# Fase 7 — Plan de mejora, correcciones y codificación definitiva

**Actor: IA**  
**Objetivo:** transformar las anomalías en correcciones priorizadas y aplicar después los cambios de código necesarios.

## 1. Prompt de análisis de anomalías

```text
Este es el registro de las pruebas en producción.

1. Clasifica las anomalías por gravedad.
2. Agrupa las anomalías relacionadas.
3. Identifica las causas probables.
4. Propón una corrección mínima para cada anomalía.
5. Indica los riesgos de regresión.
6. Propón las pruebas que deben añadirse.
7. Propón mejoras de uso.
8. Propón mejoras estéticas.
9. Modifica solo lo necesario.
10. Conserva los comportamientos validados.
```

## 2. Priorización de anomalías

| Prioridad | Tipo | Anomalías afectadas | Tratamiento |
|---|---|---|---|
| P0 | Fallo, pérdida de datos, vulnerabilidad | [BUG-XXX] | Corrección inmediata |
| P1 | Funcionalidad incorrecta | [BUG-XXX] | Corrección antes de la validación final |
| P2 | Mala experiencia de uso | [BUG-XXX] | Corrección si es razonable |
| P3 | Estética, mensaje, formato | [BUG-XXX] | Corrección o aplazamiento |
| P4 | Mejora futura | [BUG-XXX] | Backlog |

## 3. Correcciones aplicadas

| ID | Anomalía | Corrección | Archivos modificados | Pruebas añadidas | Riesgo de regresión | Estado |
|---:|---|---|---|---|---|---|
| FIX-001 | [BUG-XXX] | [POR COMPLETAR] | [ruta] | [ruta] | [Bajo / Medio / Alto] | [Aplicado / Validado] |
| FIX-002 | [BUG-XXX] | [POR COMPLETAR] | [ruta] | [ruta] | [Bajo / Medio / Alto] | [Aplicado / Validado] |

## Validación de la fase 7

- [ ] Cada anomalía tiene un estado claro.
- [ ] Las correcciones se aplican por prioridad.
- [ ] Las pruebas de no regresión pasan.
- [ ] Los comportamientos validados se conservan.
- [ ] Cada corrección queda documentada.

**Estado:** [ ] En curso / [ ] Validado  
**Validado por:** [NOMBRE]  
**Fecha:** [AAAA-MM-DD]

---

# Fase 8 — Prueba definitiva

**Actor: Humano**  
**Objetivo:** validar la versión candidata antes de la documentación final y del despliegue estable en producción.

## 1. Pruebas de validación

| Prueba | Objetivo | Comando | Resultado esperado | Resultado obtenido | Estado |
|---|---|---|---|---|---|
| Escenario nominal | [POR COMPLETAR] | [comando] | [POR COMPLETAR] | [POR COMPLETAR] | [ ] |
| Escenario de error | [POR COMPLETAR] | [comando] | [POR COMPLETAR] | [POR COMPLETAR] | [ ] |
| Opciones CLI | [POR COMPLETAR] | [comando] | [POR COMPLETAR] | [POR COMPLETAR] | [ ] |
| Configuración | [POR COMPLETAR] | [comando] | [POR COMPLETAR] | [POR COMPLETAR] | [ ] |
| Permisos | [POR COMPLETAR] | [comando] | [POR COMPLETAR] | [POR COMPLETAR] | [ ] |
| Interrupción | [POR COMPLETAR] | [comando] | [POR COMPLETAR] | [POR COMPLETAR] | [ ] |
| No regresión | [POR COMPLETAR] | [comando] | [POR COMPLETAR] | [POR COMPLETAR] | [ ] |

## 2. Lista de verificación final

- [ ] El proyecto se inicia correctamente.
- [ ] Los comandos principales funcionan.
- [ ] Los errores son comprensibles.
- [ ] Los logs son utilizables.
- [ ] No hay errores críticos.
- [ ] No se detecta ninguna regresión.
- [ ] El rendimiento es aceptable.
- [ ] La seguridad cumple los requisitos.
- [ ] La versión es identificable.
- [ ] Es posible hacer rollback.

## Validación de la fase 8

**Decisión:** [ ] Versión candidata / [ ] Volver a corrección  
**Validado por:** [NOMBRE]  
**Fecha:** [AAAA-MM-DD]

---

# Fase 9 — Borrador de la documentación

**Actor: Humano**  
**Objetivo:** documentar el software tal como funciona realmente.

## 1. Documentos que deben producirse

| Documento | Objetivo | Estado |
|---|---|---|
| `README.md` | Presentación e inicio rápido | [ ] |
| `GUIA_USUARIO.md` | Guía de uso detallada y accesible | [ ] |
| `GUIA_TECNICA.md` | Arquitectura y funcionamiento interno | [ ] |
| `GUIA_DESARROLLO.md` | Entorno, pruebas, convenciones | [ ] |
| `INSTALACION.md` | Requisitos previos e instalación | [ ] |
| `SEGURIDAD.md` | Riesgos, permisos, buenas prácticas | [ ] |
| `SOLUCION_DE_PROBLEMAS.md` | Errores frecuentes y soluciones | [ ] |
| `CHANGELOG.md` | Historial de versiones | [ ] |

## 2. Contenido que debe verificarse

- [ ] Cada comando está documentado.
- [ ] Cada opción está documentada.
- [ ] Cada archivo de configuración está documentado.
- [ ] Cada dependencia está documentada.
- [ ] Cada error frecuente está explicado.
- [ ] Los límites son explícitos.
- [ ] Los ejemplos son verificables.

## Validación de la fase 9

**Estado:** [ ] Borrador / [ ] Validado  
**Validado por:** [NOMBRE]  
**Fecha:** [AAAA-MM-DD]

---

# Fase 10 — Formato y documentación definitiva

**Actor: IA**  
**Objetivo:** completar, estructurar y armonizar la documentación sin inventar comportamientos que no existan en el código.

## 1. Prompt de completación documental

```text
Estos son los borradores de documentación.

1. Verifica la coherencia con el código real.
2. Detecta funciones no documentadas.
3. Detecta opciones CLI no documentadas.
4. Detecta mensajes de error no explicados.
5. Detecta dependencias ausentes.
6. Detecta pasos de instalación ausentes.
7. Detecta incoherencias entre documentos.
8. Mejora la estructura y la legibilidad.
9. Completa las secciones que faltan.
10. No modifiques el comportamiento descrito sin pruebas en el código.
```

## 2. Controles documentales

| Control | Estado | Comentario |
|---|---|---|
| Coherencia con el código | [ ] | [POR COMPLETAR] |
| Comandos documentados | [ ] | [POR COMPLETAR] |
| Opciones documentadas | [ ] | [POR COMPLETAR] |
| Códigos de salida documentados | [ ] | [POR COMPLETAR] |
| Configuración documentada | [ ] | [POR COMPLETAR] |
| Dependencias documentadas | [ ] | [POR COMPLETAR] |
| Errores frecuentes documentados | [ ] | [POR COMPLETAR] |
| Ejemplos verificables | [ ] | [POR COMPLETAR] |
| Estructura armonizada | [ ] | [POR COMPLETAR] |

## Validación de la fase 10

**Estado:** [ ] Borrador / [ ] Validado  
**Validado por:** [NOMBRE]  
**Fecha:** [AAAA-MM-DD]

---

# Fase 11 — Despliegue definitivo en producción

**Actor: Humano**  
**Objetivo:** desplegar la versión validada, documentada y probada.

## 1. Preparación

- [ ] Versión validada en la fase 8.
- [ ] Documentación definitiva validada en la fase 10.
- [ ] Copia de seguridad del entorno existente realizada.
- [ ] Procedimiento de rollback disponible.
- [ ] Etiqueta de versión creada.

Comandos:

```bash
git tag -a v[VERSION] -m "Versión estable [VERSION]"
git push origin v[VERSION]
```

## 2. Empaquetado

```bash
python -m build
```

Verificación:

```bash
sha256sum dist/*
```

## 3. Despliegue

| Etapa | Comando / acción | Estado | Comentario |
|---:|---|---|---|
| 1 | Copia de seguridad | [ ] | [POR COMPLETAR] |
| 2 | Desplegar la versión etiquetada | [ ] | [POR COMPLETAR] |
| 3 | Verificar el servicio | [ ] | [POR COMPLETAR] |
| 4 | Comprobar los logs | [ ] | [POR COMPLETAR] |
| 5 | Probar el comando principal | [ ] | [POR COMPLETAR] |
| 6 | Documentar la versión desplegada | [ ] | [POR COMPLETAR] |

## 4. Verificaciones posteriores al despliegue

```bash
systemctl status [NOMBRE_DEL_SERVICIO]
journalctl -u [NOMBRE_DEL_SERVICIO] -n 100 --no-pager
```

- [ ] El servicio está activo.
- [ ] No aparece ningún error crítico en los logs.
- [ ] El comando principal responde.
- [ ] La versión desplegada corresponde a la etiqueta validada.
- [ ] El rollback está documentado y es verificable.

## Validación final

| Campo | Valor |
|---|---|
| Versión desplegada | [VERSIÓN] |
| Fecha de puesta en producción | [AAAA-MM-DD] |
| Entorno | [POR COMPLETAR] |
| Responsable | [NOMBRE] |
| Rollback probado | [Sí / No] |
| Estado final | [En producción / Fallo / Rollback] |

---

# Historial de modificaciones del documento

| Fecha | Versión | Autor | Modificación |
|---|---|---|---|
| [AAAA-MM-DD] | 0.1 | [NOMBRE] | Creación de la plantilla |
| [AAAA-MM-DD] | [VERSIÓN] | [NOMBRE] | [POR COMPLETAR] |
