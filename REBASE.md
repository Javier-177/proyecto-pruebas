Tarea 5: Limpieza de commits con git rebase -i
------------------------------------------------

1. Introducción
En esta tarea he aprendido a limpiar y reorganizar el historial de commits utilizando
git rebase -i. El objetivo es mejorar la claridad del historial, corregir mensajes
poco descriptivos y fusionar commits que no aportan valor por separado.

2. Creación de commits poco claros
Para realizar la práctica, generé tres commits con mensajes poco informativos:
- "Arreglos"
- "Cambios"
- "Actualización de cosas"

Cada commit añadía una línea nueva al archivo archivo.txt.

3. Reescritura de mensajes con rebase interactivo
Ejecuté el siguiente comando para editar los últimos tres commits:

    git rebase -i HEAD~3

En el editor cambié "pick" por "reword" en los tres commits. Git me fue pidiendo
uno por uno los nuevos mensajes. Reescribí cada mensaje para que fuera claro y
descriptivo, por ejemplo:
- "Añadir primera línea de prueba a archivo.txt"
- "Añadir segunda línea de prueba a archivo.txt"
- "Añadir tercera línea de prueba a archivo.txt"

4. Fusión de commits con squash
Después volví a ejecutar:

    git rebase -i HEAD~3

Esta vez dejé el primer commit como "pick" y los otros dos como "squash" para
fusionarlos en un único commit. Git abrió un editor con los mensajes combinados
y dejé un mensaje final único:

    Añadir líneas de prueba a archivo.txt

5. Actualización del historial remoto
Como el rebase reescribe el historial, fue necesario forzar la actualización del
repositorio remoto:

    git push origin main --force

6. Resultado final
- El historial remoto ahora contiene un único commit claro y coherente.
- Los mensajes son descriptivos y explican exactamente qué se hizo.
- El repositorio queda más limpio y fácil de entender.
