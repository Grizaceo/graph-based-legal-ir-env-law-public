# Arquitectura y Garantías Fundamentales

El sistema se construye alrededor de una restricción legal simple: la recuperación solo es útil si la ruta de evidencia puede inspeccionarse.

La arquitectura separa adquisición, recuperación, revisión humana, canonicalización y razonamiento en capas distintas. Esa separación es lo que mantiene el sistema explicable y fail-closed.

---

## La pila de capas

| Capa | Nombre | Responsabilidad principal |
|------|--------|---------------------------|
| 0 | Scrapers / adquisición | Recolectar materiales públicos de PJUD, DT, SUSESO, BCN/LeyChile y otras fuentes aprobadas |
| 1 | IndexO + sentence-index | Recuperación semántica y determinista para evidencia candidata |
| 2 | legal-reviewer | Curación humana, etiquetado y construcción de goldset |
| 3 | review-graph | Ciclo de vida de relaciones: pendiente, aprobado, rechazado, expirado |
| 4 | graph-legal-ir | Grafo canónico con evidencia respaldada por hash y compuertas de promoción |
| 5 | LexO | Harness de razonamiento, coordinación de subagentes y ruta de respuesta fundamentada |
| 6 | LexCon-hub + apps públicas | Navegación pública, orientación y superficies de usuario acotadas |

---

## Principios fundamentales de diseño

### 1. Evidencia exacta primero
Cada relación promovida debe apuntar a un ancla textual que pueda inspeccionarse directamente. Una paráfrasis no es suficiente.

### 2. Validación humana para aristas ambiguas
Si una relación es legalmente sensible, incierta o controvertida, pertenece a revisión antes de volverse canónica.

### 3. Ruta de respuesta fail-closed
Si el sistema no puede respaldar una afirmación con evidencia suficiente, debe abstenerse o redirigir a revisión en vez de improvisar certeza.

### 4. Trazabilidad por construcción
El grafo canónico no es una bolsa de notas. Es una estructura trazable donde cada arista puede verificarse contra el texto fuente y el estado de revisión.

### 5. Mención no es fundamentación
Una fuente puede mencionar a otra fuente sin depender legalmente de ella. La arquitectura mantiene esos roles distintos.

### 6. Conciencia temporal y procedimental
La validez legal depende del tiempo, la secuencia y las condiciones procedimentales. La arquitectura trata estos como restricciones de primera clase.

---

## Ciclo de vida de una relación canónica

Una relación típicamente pasa por estos estados:

PENDIENTE → APROBADO
PENDIENTE → RECHAZADO
PENDIENTE → EXPIRADO

Solo el material aprobado puede promoverse al grafo canónico. El material expirado no persiste silenciosamente como verdad.

---

## Resumen del flujo de datos

Fuentes públicas → adquisición → índice de recuperación → evidencia candidata → review-graph → grafo canónico → razonamiento LexO → superficies públicas o de producto

En la etapa de revisión, la relación puede moverse a uno de tres resultados:
- aprobado → grafo canónico
- rechazado → archivo / no canónico
- expirado → reencolar o retirar

---

## Para qué está optimizada esta arquitectura

- IR legal explicable
- inspección exacta de evidencia
- recuperación acotada en dominios legales específicos
- promoción revisable de relaciones
- abstención en lugar de especulación

## Para qué no está optimizada

- chat genérico
- asesoría legal amplia sin evidencia
- minería de relaciones no revisadas
- reemplazar profesionales legales
