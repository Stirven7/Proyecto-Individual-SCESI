📚 Capitulo 1 - Git: Fundamentos y Herramientas
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