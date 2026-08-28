---
name: manus-universal-skills-suite
description: Orquestación modular del corpus completo de habilidades de Manus AI. Usar cuando una tarea combine varias áreas, requiera seleccionar entre habilidades del registro, coordinar dependencias, preservar trazabilidad, validar entregables o preparar un release; para tareas estrechas, cargar directamente el módulo especializado.
---

# Manus Universal Skills Suite

Activa esta habilidad como **capa de coordinación**, no como sustituto de las habilidades especializadas. Selecciona siempre la unidad mínima que cubra la petición.

## Flujo obligatorio

1. Define objetivo, entradas, salida, fecha de corte, riesgos, permisos y criterio de finalización.
2. Consulta `references/registry.json` cuando necesites localizar módulos por nombre, categoría o recursos.
3. Elige el módulo más específico. Añade módulos de soporte sólo si existe una dependencia clara y documentada.
4. Separa hechos verificados, inferencias, recomendaciones, hipótesis y pendientes. Para datos actuales, verifica fuentes primarias.
5. Antes de publicar, borrar, pagar, enviar, cambiar cuentas o ejecutar acciones irreversibles, detén el flujo y solicita confirmación explícita.
6. Valida estructura, contenido, referencias, seguridad, resultado y entrega. Conserva logs, hashes y rollback cuando haya modificaciones.
7. Entrega el resultado con límites, evidencia y archivos relevantes; no presentes un `WARN` como `PASS`.

## Resolución de solapamientos

Prioriza especificidad sobre amplitud. Si dos módulos parecen equivalentes, compara sus activadores, riesgos, entradas, salidas y autoridad del dominio; conserva ambos hasta demostrar que uno es redundante. No fusiones instrucciones incompatibles en tiempo de ejecución: registra el conflicto y elige una precedencia explícita.

## Recursos incluidos

- `references/registry.json`: inventario de módulos y recursos.
- `references/ARCHITECTURE.md`: arquitectura, precedencia y límites.

## Condición de parada

Detente si falta una entrada esencial, permiso, fuente primaria, credencial autorizada, licencia, ruta, dependencia o mecanismo de rollback. Declara el bloqueo y pide sólo la información necesaria.
