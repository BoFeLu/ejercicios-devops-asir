# Tarea 5: - Limpieza de commits con `git rebase -i`

## Objetivo
Aprender a limpiar el historial de commits utilizando `git rebase -i`, cambiando los mensajes para que sean claros y fusionando commits innecesarios que no aporten valor por separado.

## Qué hice
1. Verifiqué el historial inicial, que contenía tres commits poco descriptivos:
   `Arreglos`, `Cambios` y `Actualización de cosas`, todos sobre el archivo **poco-claro.txt**.
2. Ejecuté el comando:
   ```bash
   git rebase -i HEAD~3
```
En el archivo de rebase sustituí las acciones por:

```bash
pick 6cf68ef Arreglos
squash 9886fc0 Cambios
reword d6d56d6 Actualización de cosas
```
Git abrió el editor para los nuevos mensajes. Escribí:

Para el commit combinado (1º + 2º):
```bash
feat: modificar archivo poco-claro.txt y añadir primeras líneas

Combina los cambios de los commits "Arreglos" y "Cambios".
Se modifica el archivo y se añaden las primeras líneas de contenido.
```
Para el último commit:
```bash
feat: actualizar poco-claro.txt con nuevas líneas y ajustes menores
```

Verifiqué el nuevo historial con:

```bash
git log --oneline -5
```

Resultado:
```bash
e319a09 feat: actualizar poco-claro.txt con nuevas líneas y ajustes menores
f61293b feat: modificar archivo poco-claro.txt y añadir primeras líneas
2d08a7a chore: activar la primera ejecución del flujo de trabajo
60d906a chore: añadir workflow validate.yml para validación automática
bdbf0c4 docs: añadir badge de estado del workflow
```

Finalmente actualicé el remoto con:

```bash
git push --force
```

## Resultado
El historial pasó de tres commits confusos a dos commits bien definidos y descriptivos.
El contenido del repositorio se mantiene igual, pero el registro de cambios ahora es más legible y profesional.

## Conclusiones
El comando `git rebase -i` permite limpiar y reorganizar el historial sin alterar el contenido.

Los comandos `reword` y `squash` son útiles para mejorar la trazabilidad y evitar ruido.

Mantener mensajes claros mejora la revisión de código y la comprensión del proyecto.
