 REBASE.md — Contenido
# REBASE.md — Limpieza de commits (Tarea 7)

## 1. Objetivo
Depurar el historial de Git fusionando commits innecesarios y mejorando la claridad de los mensajes mediante `git rebase -i`.

## 2. Procedimiento
1. Creación de commits con mensajes poco claros (`cambio`, `fixx`, `update file`, `ajustes varios`, `.`).  
2. Ejecución de `git rebase -i HEAD~5` con acciones `squash` y `reword`.  
3. Definición del nuevo mensaje final:  


docs: limpiar historial y consolidar commits de prueba (T7)

4. Actualización del repositorio remoto:  
```bash
git push --force-with-lease

3. Resultado

El historial se redujo a un solo commit claro y semántico, verificándose en GitHub la consolidación correcta.

4. Conclusión

El rebase interactivo permite mantener un historial lineal, legible y profesional, mejorando la trazabilidad y la calidad del repositorio.
