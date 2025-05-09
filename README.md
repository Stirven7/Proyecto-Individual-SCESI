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

# 📚 Capítulo 4 - GitHub

<details>
  <summary><strong>🔗 ¿Git y GitHub son lo mismo?</strong></summary>

¡Error común! Son **herramientas diferentes** pero complementarias:

- 🛠️ **Git**: El motor de control de versiones (local)
- ☁️ **GitHub**: La plataforma para alojar repositorios (remoto)

Ejemplo práctico:
```bash
# Esto es Git (local)
git init

# Esto interactúa con GitHub (remoto)
git remote add origin https://github.com/usuario/repo.git
```
Analogía: Git es como tu computadora personal, GitHub es como Dropbox para tu código.

</details><details> <summary><strong>🌐 Repositorios Remotos</strong></summary>
  
Tu backup en la nube para proyectos. Para configurarlo:

Crea repo en GitHub (botón verde "+ New repository")

Conecta tu repo local:

```bash
git remote add origin URL_DEL_REPO
git push -u origin main
```
Dato clave: Puedes tener múltiples remotos:

```bash
git remote add upstream URL_FORK  # Para proyectos open source
```
</details><details> <summary><strong>💻 Clonar un Repositorio</strong></summary>
  
El "Descargar proyecto" de los programadores:

```bash
# Forma básica
git clone https://github.com/usuario/repo.git

# Con nombre personalizado para la carpeta
git clone URL nombre-personalizado

# Para repos privados (requiere configuración SSH)
git clone git@github.com:usuario/repo.git
```
Tip: Usa gh repo clone usuario/repo si tienes GitHub CLI instalado.

</details><details> <summary><strong>🔗 Enlazar Repo Local con Remoto</strong></summary>

Cuando ya tienes código local y quieres subirlo:

```bash
# Paso 1: Crear conexión
git remote add origin URL_DEL_REPO

# Paso 2: Verificar
git remote -v  # Debe mostrar fetch/push

# Paso 3: Primer push
git push -u origin main
```
Si te equivocas de URL:

```bash
git remote set-url origin NUEVA_URL
```
</details><details> <summary><strong>📤 Subir Cambios (Push)</strong></summary>
  
El equivalente a "Guardar en la nube":

```bash
# Forma estándar
git push origin main

# Forma corta (solo si ya configuraste upstream)
git push

# Forzar push (¡Cuidado! Solo para emergencias)
git push --force-with-lease
```
Flujo completo:

```bash
git add .
git commit -m "feat: añade funcionalidad X"
git push
```
</details><details> <summary><strong>❌ Push Rechazado: Soluciones</strong></summary>
  
Causas comunes:

Alguien más subió cambios antes que tú

Historial incompatible

Solución paso a paso:

```bash
# 1. Baja los últimos cambios
git pull origin main

# 2. Resuelve conflictos si los hay
# (Edita los archivos marcados)

# 3. Vuelve a intentar
git push
```
Caso extremo (si el pull crea commits innecesarios):

```bash
git fetch origin
git rebase origin/main
git push
```
</details><details> <summary><strong>🌱 Ramas Remotas</strong></summary>
  
Para publicar una rama local:

```bash
# Publicar rama por primera vez
git push -u origin mi-rama

# Actualizar rama existente
git push origin mi-rama

# Ver todas las ramas remotas
git branch -r
```
Eliminar rama remota:

```bash
git push origin --delete rama-obsoleta
Consejo: Usa nombres descriptivos:

feat/login-social en vez de rama1

fix/error-api en vez de patch
```
</details><details> <summary><strong>🚀 Flujo Colaborativo Típico</strong></summary>
  
Clona el repo:

```bash
git clone URL
```
Crea tu rama:

```bash
git checkout -b mi-feature
```
Trabaja y haz commits:

```bash
git add .
git commit -m "feat: añade X"
```
Sincroniza con los últimos cambios:

```bash
git fetch origin
git rebase origin/main
```
Sube tus cambios:

```bash
git push origin mi-feature
```
Crea Pull Request en GitHub

</details>

# 📚 Capítulo 5 - Push, pull && pull request

<details>
  <summary><strong>🔗 ¿Qué es un Pull Request?</strong></summary>

Un **Pull Request (PR)** es como proponer una mejora en un proyecto compartido. Imagina que:

- ✉️ Es una solicitud formal para incluir tus cambios
- 👀 Permite revisiones de código antes de fusionar
- 🤝 Facilita el trabajo en equipo

**Flujo completo desde terminal**:
```bash
# 1. Crea una rama específica
git checkout -b fix/login-error

# 2. Haz tus cambios y commitea
git add .
git commit -m "fix: corrige validación de email en login"

# 3. Sube la rama
git push origin fix/login-error

# 4. Crea el PR (requiere GitHub CLI)
gh pr create \
  --title "Corrige validación de emails" \
  --body "Soluciona el problema con dominios .edu" \
  --reviewer equipo-qa
```
Dato : En GitHub, los PR generan automáticamente:

✅ Checks de integración continua

💬 Hilos de discusión

🔍 Vista de diferencias (diffs)

</details><details> <summary><strong>📝 PRs en Borrador (Draft)</strong></summary>
  
Los Draft PRs son como "Trabajo en progreso" para tu código:

¿Cuándo usarlos?

🚧 Cuando necesitas feedback temprano

⏳ Para cambios complejos que llevarán tiempo

👥 Para coordinar con otros devs

Cómo gestionarlos:

```bash
# Crear PR como borrador (CLI)
gh pr create --draft

# Convertir a PR listo (desde GitHub UI)
# O via CLI:
gh pr ready 1234  # Número del PR
```
Ventajas:

🔒 No se puede mergear accidentalmente

🏷 Se ve diferente en la lista de PRs

💡 Permite recibir sugerencias tempranas

</details><details> <summary><strong>✅ Pull Requests de Calidad</strong></summary>
  
Plantilla para PRs efectivas:

```bash
## Qué hace este PR
- Corrige el cálculo de impuestos para clientes internacionales
- Añade validación de formato VAT

## Por qué es necesario
Fixes #123  (Referencia al issue)

## Capturas (opcional)
| Antes         | Después       |
|-------        |---------      |
| ![Error](url) | ![Fixed](url) |

## Cómo probar
1. Ejecutar `npm test`
2. Verificar flujo de checkout con:
   ```bash
   curl -X POST /checkout -d '{"country": "DE"}'
```
**Errores comunes a evitar**:
- 🔄 Mezclar múltiples funcionalidades en un PR
- 📝 Mensajes genéricos como "Fix bugs"
- 🚫 Ignorar las guías de estilo del proyecto
</details>

<details>
  <summary><strong>🔍 Revisando PRs como Pro</strong></summary>

**Comandos útiles para revisores**:
```bash
# Probar localmente el PR
gh pr checkout 1234

# Ver cambios directamente en terminal
gh pr diff 1234

# Aprobar con comentario
gh pr review 1234 --approve -b "LGTM!"
```
Checklist de revisión:

🔎 El código cumple su propósito

🧪 Tiene tests adecuados

📚 La documentación se actualizó

🎨 Sigue el estilo del proyecto

⚡ No introduce regresiones

Ejemplo de feedback constructivo:

Sugerencia para `validation.js`:
```javascript
// En vez de:
if (email.includes('@'))
// Podría ser:
if (isValidEmail(email))  // Usa la función existente
Esto mantendría consistencia con el resto del códigobase.
```
</details>

<details>
  <summary><strong>🚀 Flujo Avanzado: Rebasar PRs</strong></summary>

Cuando tu PR tiene conflictos:

```bash
# 1. Traer últimos cambios
git fetch origin main

# 2. Rebasar tu rama
git checkout mi-pr
git rebase origin/main

# 3. Resolver conflictos (si los hay)
git mergetool

# 4. Forzar push actualizado
git push --force-with-lease
```
Beneficios:

🧹 Mantiene el historial limpio

🔗 Evita commits de merge innecesarios

🚦 Facilita la revisión lineal

</details><details> <summary><strong>💡 Secretos de los Maintainers</strong></summary>
  
Comandos para gestión avanzada:

```bash
# Combinar PR con squash (CLI)
gh pr merge 1234 --squash

# Hacer merge desde terminal
gh pr merge 1234 --merge

# Revertir un PR mal mergeado
gh pr revert 1234
```
</details>

# 📚 Capítulo 6 - GitFlow

<details>

  <summary><strong>🔀 GitFlow: El Flujo Estándar</strong></summary>

GitFlow es como el **sistema de metro** de tu código: líneas claras con paradas definidas. Así funciona:

### 🚉 Estaciones principales (ramas permanentes)
```bash
# Línea de producción (nunca cierra)
git branch main

# Línea de pre-producción (todos suben aquí primero)
git branch develop
```
🚋 Trenes temporales (ramas de trabajo)
```bash
# Tren de nuevas características (feature)
git checkout -b feature/user-auth develop

# Tren de emergencia (hotfix)
git checkout -b hotfix/404-error main

# Tren de lanzamiento (release)
git checkout -b release/v1.3 develop
```
Comandos clave para conductores:

```bash
# Iniciar GitFlow (configura automáticamente todo)
git flow init

# Lanzar nueva feature
git flow feature start search-filters
```
Diagrama del metro:
```bash
main    ——○————————○————————○—————○
           \       |       /
develop    —○—○—○—○—○—○—○—
             /     |     \
feature    ○○○   ○○○   ○○○
```
</details><details> <summary><strong>🔄 Ciclo de Vida de las Ramas</strong></summary>
  
1. Features (2-3 días de vida):

```bash
# Abrir línea nueva
git flow feature start payment-gateway

# Subir al repositorio
git flow feature publish payment-gateway

# Cerrar línea (fusiona a develop)
git flow feature finish payment-gateway
```
2. Hotfixes (Horas):

```bash
git flow hotfix start session-expiry
# ...correcciones rápidas...
git flow hotfix finish session-expiry  # Fusiona a main y develop
```
3. Releases (1-2 semanas):

```bash
git flow release start v1.4
# ...preparar lanzamiento...
git flow release finish v1.4  # Fusiona a main y develop
```
Tip: Usa etiquetas semánticas:

```bash
git tag -a v1.4.0 -m "Lanzamiento estable"
```
</details><details> <summary><strong>⚠️ Casos de Uso Reales</strong></summary>
  
Cuándo usar GitFlow:

🏦 Proyectos empresariales con ciclos de lanzamiento fijos

📱 Apps móviles con versionado estricto

🛠️ Equipos >5 desarrolladores

Cuándo evitar GitFlow:

🚀 Startups con deploy continuo

🧪 Proyectos experimentales

👨‍💻 Equipos pequeños (<3 personas)

Ejemplo en la vida real:

```bash
# 1. Desarrollo normal
git flow feature start dark-mode
git commit -m "feat: añade toggle dark/light"

# 2. Lanzamiento
git flow release start v2.1
git flow release finish v2.1

# 3. Emergencia
git flow hotfix start login-crash
git commit -m "fix: null pointer en auth"
git flow hotfix finish login-crash
```
</details><details> <summary><strong>🔧 Configuración Avanzada</strong></summary>
  
Personaliza nombres de ramas:

```bash
git config gitflow.prefix.feature "func/"
git config gitflow.prefix.hotfix "parche/"
```
Integración con CI/CD:
```bash
# Ejemplo .gitlab-ci.yml
stages:
  - test
  - deploy

test_feature:
  only:
    - /^func/.*$/
  script: npm test

deploy_prod:
  only:
    - main
  script: ./deploy.sh
```
Herramientas visuales:

```bash
git log --graph --abbrev-commit --decorate --all
# O instala:
brew install tig  # Navegador interactivo
```
</details><details> <summary><strong>💡 Mitos y Verdades</strong></summary>

Mito: "GitFlow es obligatorio para proyectos serios"
Realidad: Muchos proyectos modernos prefieren GitHub Flow o Trunk-Based

Mito: "Las ramas de release son innecesarias"
Realidad: Son útiles para:

📦 Preparar changelogs

🔍 Última ronda de testing

🏷 Versionado preciso

Comparación de comandos:

Acción	GitFlow	GitHub Flow
Nueva func	git flow feature start	git checkout -b feat
Deploy	git flow release finish	git push origin main
Fix urgente	git flow hotfix start	git checkout -b fix

</details>

# 📚 Capítulo 7 - Buenas Prácticas en Git

<details>
  <summary><strong>⏱️ 1. Frecuencia de commits</strong></summary>

Haz commits frecuentes, pero con sentido. Es mejor hacer varios commits pequeños que uno enorme al final del día. Piensa en commits como puntos de guardado lógicos: cuando arreglas un bug específico o añades una función completa.

```bash
# ✅ Así sí:
git commit -m "fix: corrige error de validación en formulario"

# ❌ Así no:
git commit -m "muchos cambios"
```
🔹 No hagas commits de cambios sin importancia. Cada commit debe tener un propósito claro.

</details><details> <summary><strong>✍️ 2. Mensajes de commit claros</strong></summary>
  
📌 Usa verbos en imperativo (añade, corrige, elimina) y sé específico:

```bash
# 💚 Buen ejemplo:
git commit -m "feat: añade paginación a lista de productos"

# 💔 Mal ejemplo:
git commit -m "paginación"
```
📝 Si el cambio necesita explicación, usa el cuerpo del commit:

```bash
git commit -m "fix: corrige cálculo de impuestos" -m "
- Problema: no consideraba tasa regional
- Solución: añade campo 'tax_rate' al cálculo
- Impacto: afecta reportes fiscales
"
```
🏷️ Prefijos útiles:

feat:: nueva funcionalidad 🆕

fix:: corrección de errores 🐛

docs:: cambios en documentación 📄

</details><details> <summary><strong>🌿 3. Nombrado de ramas</strong></summary>
  
Usa nombres descriptivos y consistentes:

```bash
# 🌟 Para nuevas funcionalidades:
git checkout -b feat/buscador-avanzado

# 🛠️ Para correcciones:
git checkout -b fix/error-login-movil

# 🎫 Si usas sistema de tickets:
git checkout -b fix/PROJ-123-error-404
```
⚠️ Evita nombres genéricos como "prueba" o "cambios".

</details><details> <summary><strong>⏪ 4. Alterar el historial</strong></summary>

🚨 Normalmente no debes modificar el historial de commits, especialmente si ya los compartiste. Pero hay excepciones:

Para commits locales no compartidos:

```bash
git commit --amend  # ✏️ Corrige el último commit
```
Si subiste información sensible:

```bash
git filter-branch --force --index-filter 'git rm --cached --ignore-unmatch archivo-secreto.txt' --prune-empty --tag-name-filter cat -- --all
```
🔒 La alternativa segura:

```bash
git revert mal_commit  # ↩️ Crea commit que deshace cambios
```
</details><details> <summary><strong>🛠️ 5. Herramientas útiles</strong></summary>
  
🔍 Para verificar cambios antes de commitear:

```bash
git diff --staged
```
📜 Para ver el historial claro:

```bash
git log --oneline --graph
```
🧩 Para manejar cambios complejos:

```bash
git add -p  # ➕ Añade cambios interactivamente
```
⚡ Alias recomendados (añade a tu .gitconfig):

```ini
[alias]
hist = log --pretty=format:'%h %ad | %s%d [%an]' --date=short --graph
```
</details>


# 📚 Capítulo 8 - Deshacer Mis Cambios

<details>
  
  </details><details><summary><strong> 📚 ¿Es Recomendable Deshacer Cambios en Git?  Cambios</strong></summary>


1. Información Sensible Expuesta

```bash
# Si subiste credenciales por accidente
git filter-repo --invert-paths --path credentials.txt
```
2. Bugs Recién Descubiertos

```bash
# Si un commit introdujo un error crítico
git revert abc123  # Crea commit que deshace los cambios
```
🔹 Recomendado: Cuando trabajas solo o con cambios no compartidos.

</details><details><summary><strong>🔙 Deshacer el Último Commit</strong></summary>

¿Cometiste un error en tu último commit? No entres en pánico, Git tiene la solución. Aquí tus opciones:

```bash
# 🟢 Conserva cambios en staging (puedes editarlos)
git reset --soft HEAD~1

# 🟡 Devuelve cambios al área de trabajo (sin staging)
git reset --mixed HEAD~1  # Este es el predeterminado

# 🔴 Elimina TODO (cambios y commit)
git reset --hard HEAD~1
```
💡 Tip: Usa --soft cuando solo quieras reescribir el mensaje del commit o agregar archivos olvidados.

</details><details> <summary><strong>📝 Arreglar el Último Commit</strong></summary>
  
¿Olvidaste incluir un archivo o escribiste mal el mensaje? Arreglémoslo:

```bash
# 1. Añade los archivos que faltaban
git add archivo-olvidado.js

# 2. Corrige el commit
git commit --amend
```
⚠️ Importante: Si ya hiciste push, evita --amend para no romper el historial compartido. Mejor usa:

```bash
git revert HEAD
```

</details><details> <summary><strong>❌ Deshacer Cambios No Committeados</strong></summary>

¿Cambios que no quieres guardar? Así los eliminas:

```bash
# Descartar cambios en un archivo
git restore archivo-arruinado.js

# Descartar TODOS los cambios locales
git restore .

# Eliminar archivos no rastreados (¡Cuidado!)
git clean -fd
```
🔸 Recuerda: git clean borra archivos permanentemente. Usa -n primero para simular:

```bash
git clean -n  # "Dry run" - muestra qué borraría
```

</details><details> <summary><strong>🔄 Revertir Commits Públicos</strong></summary>
  
Si ya hiciste push, usa revert para deshacer cambios sin alterar el historial:

```bash
# Revertir el último commit
git revert HEAD

# Revertir un commit específico
git revert abc1234

# Revertir un rango de commits
git revert abc1234..def5678
```
🌐 Ventaja: Esto es seguro para trabajo en equipo, ya que no reescribe historia.

</details><details> <summary><strong>📅 Deshacer un Merge Problemático</strong></summary>
  
Merge que salió mal? Soluciones:

```bash
# Si NO has committeado el merge:
git merge --abort

# Si YA committeaste el merge:
git revert -m 1 <merge-commit-hash>
```
🛠️ Ejemplo completo:

```bash
# 1. Encuentra el hash del merge
git log --merges

# 2. Reviértelo
git revert -m 1 d4f5g6h
```
🔧 La opción -m 1 especifica mantener la rama principal (usualmente main/master).

</details><details> <summary><strong>💡 Rescate de Emergencia</strong></summary>
  
¿Perdiste cambios importantes? Tu salvavidas:

```bash
# Ver TODO lo que has hecho (incluyendo lo "perdido")
git reflog
# Recupera un commit eliminado
git checkout abc1234  # Hash del commit desde reflog
git checkout -b rescate-abc1234  # Crea rama de rescate
```
🧠 Dato curioso: reflog guarda tus acciones por ~90 días. ¡Tu red de seguridad!

</details>