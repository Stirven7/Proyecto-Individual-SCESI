# 📚 Capitulo 1 - Git: Fundamentos y Herramientas

<details> <summary><strong>🔗 ¿Qué es un control de versiones?</strong></summary>
  
Un control de versiones es básicamente un sistema que guarda todos los cambios que haces en el código de un proyecto. Así puedes tener un historial completo de todo lo que ha pasado, como:

¿Quién lo cambió?

¿Cuándo lo hizo?

¿Qué modificó exactamente?

Sirve mucho para no perderte, volver atrás si algo sale mal y trabajar en equipo sin pisarse el código.

</details> <details> <summary><strong>⚙️ Lo básico de Git</strong></summary>
  
La base de Git son los repositorios, que son como carpetas donde se guardan todas las versiones de tus archivos y los cambios que haces. 
Pueden ser:

Locales: Están en tu computadora.

Remotos: Están en internet (como GitHub), para que varios puedan trabajar juntos.

Git usa ramas (branches), que te dejan hacer cosas nuevas sin tocar el código principal (que suele estar en main).

</details> <details> <summary><strong>🛠 Configuración inicial de Git</strong></summary>
Antes de empezar, tienes que decirle a Git quién eres con tu nombre y correo. Se hace así:

``` bash
git config --global user.name "Tu Nombre"  
git config --global user.email "tuemail@dominio.com"
```  
Así todos tus cambios quedan con tu firma.

</details> <details> <summary><strong>🎨 Cambiar el editor de código que usa Git</strong></summary> Si quieres que Git abra tu editor favorito (como VSCode) cuando necesite que escribas algo, lo puedes configurar así:
  
``` bash
git config --global core.editor "code --wait"
``` 
</details> <details> <summary><strong>🔧 Revisar tu configuración de Git</strong></summary> Para ver cómo tienes configurado Git, usa: 
  
``` bash
git config --list
```   
Te muestra todo, desde tu nombre hasta el editor que usas.

</details> <details> <summary><strong>🚀 Cómo empezar un proyecto nuevo con Git</strong></summary> Para crear un repositorio Git en tu proyecto, solo haz:
  
``` bash
git init
  ``` 
Y listo, Git empieza a rastrear todo lo que haces en esa carpeta.

</details>

# 📚 Capítulo 2 - Stages y Commits en Git

<details>
  <summary><strong>🔗 ¿Qué es un Commit?</strong></summary>

Un **commit** es como tomar una foto de tu proyecto en un momento exacto. Imagina que cada vez que haces commit, Git guarda una instantánea perfecta de cómo están todos tus archivos en ese instante.

Lo genial es que cada commit guarda:
- 📝 Todos los cambios que preparaste con `git add`
- 👤 Tu nombre y correo (como firmas digitales)
- 📅 La fecha y hora exacta del cambio
- ✉️ El mensaje que escribiste explicando por qué hiciste esos cambios

Ejemplo de un commit real:
```bash
commit a1b2c3d4e5f6g7h8i9j0k1l2m3n4o5p6
Author: Carlos Gómez <carlos@ejemplo.com>
Date:   Tue Oct 10 15:30:22 2023 -0500

    fix: repara el cálculo de descuentos
    
    Se corrigió el error que duplicaba los descuentos en compras
    mayores a $100.000
```
Los commits son la base para trabajar en equipo y poder volver atrás si algo sale mal. ¡Como una máquina del tiempo para tu código!

</details><details> <summary><strong>⚙️ Los 3 estados en Git</strong></summary>
  
Git maneja tus archivos como si pasaran por tres fases:

📝 Modified (Modificado)

Has hecho cambios pero no los has "marcado" para guardar

Como tener borradores de un documento que aún no envías

📦 Staged (Preparado)

Has dicho "esto quiero guardarlo" con git add

Los cambios están listos para la foto final (commit)

```bash
git add script.js  # Prepara solo este archivo
git add .         # Prepara todos los cambios
```
💾 Committed (Confirmado)

La foto ya está tomada y guardada en el historial

Se hace con:

```bash
git commit -m "feat: añade función de búsqueda"
```
Usa git status para ver en qué estado está cada archivo.

</details><details> <summary><strong>🛠 Cómo añadir archivos al área de staging</strong></summary>
  
El área de staging es como una bandeja donde pones los cambios que quieres guardar. Para usarla:

```bash
# Añade un archivo específico
git add index.html

# Añade todos los archivos .js
git add *.js

# Añade TODO lo modificado (con cuidado)
git add .
```
Si quieres ser más selectivo:

```bash
git add -p  # Te pregunta cambio por cambio
```
Recuerda: Lo que no añadas a staging no se guardará en el commit. ¡Revisa siempre con git status antes de continuar!

</details><details> <summary><strong>❌ Cómo sacar archivos del área de staging</strong></summary>
  
¡Ups! ¿Añadiste algo por error? No pasa nada:

```bash
# Saca un archivo específico (pero guarda los cambios)
git reset HEAD archivo-accidental.txt
```
# Saca TODO del staging (pero no borra los cambios)
git reset HEAD
```
Ejemplo práctico:

```bash
$ git add .  # Añadí todo por error
$ git reset HEAD config.yml  # Saco solo este
```
Importante: Esto NO borra tus cambios, solo los saca del área de preparación.

</details><details> <summary><strong>📤 Cómo hacer un Commit que valga la pena</strong></summary>
  
Un buen commit es como un buen mensaje de texto: claro y al punto.

Estructura recomendada:

```bash
git commit -m "tipo: descripción breve" -m "Detalles adicionales..."
```
Tipos de commits útiles:

fix: para correcciones de errores

feat: para nuevas funcionalidades

docs: para cambios en documentación

chore: para tareas de mantenimiento

Ejemplo real:

```bash
git commit -m "feat: añade login con Google" -m "Implementa autenticación OAuth 2.0
para login con cuentas Google. Incluye validación 
de tokens y manejo de errores."
```
Tip: Usa git commit --amend para arreglar el último commit si te equivocaste.

</details><details> <summary><strong>🔄 ¿Qué es el HEAD? (Explicado para humanos)</strong></summary>
  
HEAD es como tu "ubicación actual" en Git. Imagínalo como:

👆 Un dedo señalando el commit donde estás parado

📍 Un marcador que sigue tu posición en el historial

Cosas importantes sobre HEAD:

Siempre apunta al último commit de tu rama actual

Se mueve automáticamente cuando haces nuevos commits

Puedes ver qué commit está señalando con:

```bash
git show HEAD
```
Cuando cambias de rama, HEAD se mueve para apuntar al último commit de esa nueva rama.

Tip : Usa git log para ver tu historial de commits y confirmar que todo está como quieres.

</details>

# 📚 Capítulo 3 - Ramas, Merge y Conflictos en Git

<details>

  <summary><strong>🔀 ¿Qué es una Rama y para qué sirve?</strong></summary>

Las ramas son como **líneas de tiempo alternativas** para tu proyecto. Imagina que:

- 🌱 Cada rama es un universo paralelo donde puedes experimentar
- 🛡️ La rama principal (`main/master`) queda protegida
- 🧪 Perfecto para probar nuevas ideas sin romper lo que ya funciona

**Casos de uso reales:**
```bash
# Nueva funcionalidad
git checkout -b feature/login-social

# Corrección urgente 
git checkout -b hotfix/pago-fallido

# Refactorización
git checkout -b refactor/mejora-performance
```
📌 Dato curioso: Las ramas son solo punteros ligeros a commits, ¡no duplican tu repositorio!

</details><details> <summary><strong>💻 Trabajar con Ramas (Comandos Esenciales)</strong></summary>
  
Crear y moverse entre ramas:

```bash
# Crea rama y cámbiate a ella (en un solo paso)
git checkout -b nueva-rama

# Alternativa moderna (Git 2.23+)
git switch -c nueva-rama

# Listar todas las ramas (local y remotas)
git branch -a

# Ver rama actual
git branch --show-current
```
Flujo de trabajo típico:

1️⃣ **Creas rama desde main** (siempre actualizada)  
2️⃣ **Trabajas en tus cambios**  
3️⃣ **Haces commits frecuentes**  
4️⃣ **Fusionas cuando está lista**  
5️⃣ **Eliminas la rama** (¡no acumules basura!)

</details><details> <summary><strong>⚙️ Fusionar Ramas (Merge)</strong></summary>
  
Fusión básica:

```bash
# 1. Vuelve a la rama principal
git checkout main

# 2. Actualiza con los últimos cambios
git pull origin main

# 3. Fusiona la rama feature
git merge feature/awesome
```
Tipos de merge:

🔀 Fast-forward: Cuando no hay divergencias

🔄 3-way merge: Cuando ambas ramas tienen cambios distintos

🧩 Squash merge: Combina todos los commits en uno solo (ideal para limpieza)

Ejemplo visual:
```bash
main:    A -- B -- C
               \
feature:        D -- E
```
Después de git merge feature:
``` bash
main: A -- B -- C -- F (merge commit)
               \     /
feature:        D -- E
```
</details><details> <summary><strong>🔥 Resolver Conflictos (Guía de Supervivencia)</strong></summary>
  
Cuando Git te dice:
```bash
CONFLICT (content): Merge conflict in archivo.txt
Automatic merge failed; fix conflicts and then commit the result.
Pasos para resolver:
```

Abre el archivo conflictivo

Busca los marcadores:
```bash
python
<<<<<<< HEAD
Tu versión actual
=======
Versión que intentas fusionar
>>>>>>> rama-conflicto
```
Edita para dejar solo lo correcto

Finaliza la resolución:

```bash
git add archivo-resuelto.txt
git commit  # Git autocompleta el mensaje
```
Herramientas útiles:

VS Code tiene resaltado de conflictos integrado

Usa git mergetool para abrir ayudas visuales

</details><details> <summary><strong>🗑️ Eliminar Ramas (Limpieza necesaria)</strong></summary>
  
Eliminación segura:

```bash
# Elimina rama local (solo si está fusionada)
git branch -d rama-vieja

# Fuerza eliminación (no fusionada)
git branch -D rama-experimental

# Elimina rama remota
git push origin --delete rama-remota-obsoleta
```
Verifica antes de borrar:

```bash
# Muestra ramas ya fusionadas
git branch --merged

# Ramas no fusionadas
git branch --no-merged
```
💡 Tip : Usa nombres descriptivos como feat/user-profile en vez de rama1
</details>