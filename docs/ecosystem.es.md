# El Ecosistema LexCon

El ecosistema LexCon es una infraestructura legal en capas, no un modelo único ni una aplicación única. Su función es mantener adquisición, revisión, canonicalización, razonamiento y presentación pública suficientemente separados para que cada capa pueda inspeccionarse por sí misma.

---

## Mapa de componentes

### Capa 0-1: adquisición y recuperación
- `n8n-judicial` — adquisición y normalización de fuentes públicas
- `IndexO` — recuperación semántica y ranking sobre el corpus legal
- `sentence-index` — navegación determinista más liviana

### Capa 2-3: revisión humana y estado de relaciones
- `legal-reviewer` — etiquetado, curación y producción de goldset
- `review-graph` — ciclo de vida pendiente / aprobado / rechazado / expirado para relaciones

### Capa 4-5: razonamiento legal fundamentado
- `graph-legal-ir` — grafo canónico con relaciones promovidas y compuertas de evidencia
- `LexO` — harness de razonamiento que opera solo sobre material fundamentado y revisable
- Subagentes — trabajadores especializados usados dentro del harness cuando una tarea se beneficia de descomposición

### Capa 6: superficies públicas y de producto
- `LexCon-hub` — punto de entrada público y capa de navegación
- `lexito` — superficie asistente orientada al ciudadano
- `lexo-citizen-assistant` — capa de orientación simplificada
- `lexo-case-writer` — soporte de redacción con restricciones de evidencia
- `procurador-digital` — soporte procedimental para plazos y flujo de trabajo

---

## Límite público vs privado

El repositorio público documenta el sistema; no expone la vault, las colas de revisión internas ni el trabajo en progreso. Ese límite es intencional.

La historia pública debe mantenerse legible sin revelar:
- corpus privados
- artefactos con datos personales
- prototipos inestables
- notas internas
- atajos de laboratorio que confundirían a lectores externos

---

## Enfoque estratégico actual

1. IR legal basado en evidencia
2. Pilotos de dominio acotado
3. Revisabilidad antes que canonicalización
4. Superficies públicas que puedan explicarse claramente
5. Higiene de publicación que evite hype y desorden interno

---

## Estrategia de dominio

El ecosistema actualmente enfatiza:
- derecho ambiental
- derecho laboral
- soporte procedimental como capa de aplicación

Esos dominios no se eligen porque sean fáciles. Se eligen porque son lo suficientemente legibles para probar el método.

---

## Postura de escalabilidad

El ecosistema está diseñado para crecer sin perder trazabilidad.

Eso significa:
- los nuevos dominios deben heredar las mismas reglas de evidencia
- los estados de revisión deben permanecer explícitos
- la promoción canónica debe mantenerse gobernada por humanos
- las afirmaciones públicas deben permanecer acotadas por la cobertura real
