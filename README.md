# Manus Universal Skills Suite

> **Una distribución comunitaria, modular y reproducible de 279 habilidades preservadas más un orquestador para Manus AI.**

**Versión:** `1.0.0`  **Idioma principal:** español, con conservación de los idiomas originales  **Estado:** release candidata para revisión comunitaria  **Autoría de la distribución:** Manus AI, a partir del corpus local proporcionado por el usuario

## Portada y propósito

Esta suite reúne el corpus completo de habilidades disponible en `/home/ubuntu/skills` en una distribución **federada**, no destructiva y preparada para compartir. La suite no aplana 279 instrucciones en un único documento inmanejable. En su lugar, conserva cada habilidad como módulo independiente y añade una capa de orquestación que permite seleccionar la unidad mínima adecuada, resolver solapamientos, controlar riesgos y preservar trazabilidad.

## Cómo usarla

Instala o importa la habilidad raíz `skills/manus-universal-skills-suite/SKILL.md` cuando quieras que Manus coordine varias áreas o elija automáticamente entre módulos. Para una tarea estrecha, usa directamente el `SKILL.md` del módulo correspondiente. Consulta `docs/registry.json` para localizar habilidades por nombre, categoría, recursos y estado.

La regla de selección es simple: **usar la habilidad más específica que cubra la tarea; añadir módulos sólo cuando exista una dependencia explícita; detenerse ante permisos, secretos, publicaciones externas o cambios irreversibles**. La capa raíz no sustituye el juicio de seguridad ni autoriza acciones externas por sí sola.

## Estructura

| Ruta | Función |
|---|---|
| `skills/manus-universal-skills-suite/SKILL.md` | Orquestador raíz reutilizable |
| `skills/<nombre>/SKILL.md` | Las 279 habilidades originales preservadas |
| `docs/registry.json` | Inventario machine-readable y categorías |
| `docs/ARCHITECTURE.md` | Arquitectura, precedencia y límites |
| `docs/RELEASE_NOTES.md` | Cambios y compatibilidad de la distribución |
| `scripts/validate_suite.py` | Validación de estructura, frontmatter, rutas y secretos |
| `assets/cover.svg` | Portada vectorial editable |
| `MANIFEST.sha256` | Integridad de cada archivo publicable; excluye informes derivados |

## Seguridad y preservación

Las habilidades originales se copian sin sobrescritura y la línea base permanece fuera del paquete. No se incluyen credenciales, cookies, tokens ni datos personales intencionales. Los scripts incluidos son validadores locales; no publican, pagan, borran, hacen login ni modifican servicios externos.

## Validación

Ejecuta `python3 scripts/validate_suite.py` desde la raíz del paquete. El resultado se clasifica como `PASS`, `WARN` o `FAIL`. Un `WARN` requiere revisión humana y no debe presentarse como certificación completa.

## Licencias y atribución

Cada módulo conserva los archivos de licencia y avisos que estaban presentes en su fuente. Cuando un módulo no contiene una licencia explícita, debe tratarse como **pendiente de revisión** antes de redistribuirlo fuera del entorno autorizado. Esta distribución no sustituye la revisión de licencias de terceros ni concede derechos adicionales.

## Publicación comunitaria

El paquete está preparado para subida manual a un repositorio o catálogo. Consulta también `docs/PUBLISHING.md` antes de compartirlo. La publicación efectiva requiere que el usuario indique el destino y confirme la operación externa. Antes de publicar, revisa `docs/RELEASE_NOTES.md`, ejecuta el validador, verifica `MANIFEST.sha256` y conserva el archivo comprimido como rollback.
