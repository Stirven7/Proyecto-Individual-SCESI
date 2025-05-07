📚 Capítulo 1 
Introducción a Git y Control de Versiones
1. ¿Qué es un control de versiones?
Un control de versiones es un sistema que registra cada cambio realizado en el código fuente de un proyecto. Esto facilita el trabajo en equipo, ya que cada miembro puede ver los cambios realizados por otros y colaborar de manera más eficiente.

Las ventajas del control de versiones incluyen:

Seguimiento del historial de cambios: puedes ver qué cambios se hicieron y cuándo.

Recuperación de versiones anteriores: puedes deshacer cambios si algo no funciona como esperabas.

Colaboración eficiente: varios usuarios pueden trabajar sobre el mismo proyecto sin sobrescribir los cambios de los demás.

2. Fundamentos de Git
Repositorios: Git utiliza repositorios para almacenar el código y el historial de cambios. Los repositorios pueden ser:

Local: en tu ordenador, para realizar cambios y pruebas sin necesidad de conexión a internet.

Remoto: en un servidor (por ejemplo, en GitHub), lo que permite que otros colaboradores sincronicen sus cambios y aportes.

Ramas: Git permite crear ramas para trabajar en diferentes características o correcciones sin afectar el código principal. Estas ramas se pueden combinar (merge) en el repositorio principal.

Merge: El proceso de fusionar los cambios de una rama con la rama principal (usualmente main o master).

Esto asegura que los cambios de todos los colaboradores se integren de manera ordenada.

Push y Pull:

Push: Enviar tus cambios locales al repositorio remoto.

Pull: Obtener los cambios más recientes del repositorio remoto a tu repositorio local.

3. Configuración inicial de Git
Configurar nombre y correo: Git requiere configurar tu nombre y correo electrónico para identificar los cambios que realices.

Esto lo puedes hacer con:


git config --global user.name "Tu Nombre"
git config --global user.email "tuemail@dominio.com"
Editor de código: Git puede estar configurado para abrir tu editor de código preferido cuando necesites editar mensajes de commit.

Puedes configurar el editor predeterminado, como VSCode, Sublime Text o cualquier otro editor de tu elección:


git config --global core.editor "code --wait"  # Para VSCode
4. Configurar el editor de código que abre Git
Git usa un editor de texto para cuando necesitas escribir mensajes de commit u otros cambios. Puedes cambiar el editor predeterminado en cualquier momento:

Si prefieres un editor como VSCode, usa:


git config --global core.editor "code --wait"
Para Sublime Text, usa:


git config --global core.editor "subl -n -w"
5. Comprobar la configuración de Git
Para verificar la configuración de Git y asegurarte de que todo está correctamente configurado (nombre, correo, editor, etc.), puedes usar:


git config --list
Esto te mostrará todas las configuraciones activas en tu entorno de Git.

6. ¿Cómo inicializar un nuevo proyecto Git?
Para empezar un nuevo proyecto con Git, navega hasta la carpeta de tu proyecto y ejecuta el siguiente comando:


git init
Esto creará un repositorio vacío y permitirá que Git empiece a rastrear los cambios que hagas en los archivos dentro de esa carpeta.

Después de inicializar, agrega tus archivos y realiza el primer commit:

git add .
git commit -m "Primer commit"   