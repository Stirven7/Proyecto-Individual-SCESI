📚 Capitulo 1 - Git: Fundamentos y Herramientas
<details> <summary><strong>🔗 Que es un control de versiones?</strong></summary>
Un control de versiones es basicamente un sistema que guarda todos los cambios que haces en el codigo de un proyecto. Asi puedes tener un historial completo de todo lo que ha pasado, como:

Quien lo cambio

Cuando lo hizo

Que modifico exactamente

Sirve mucho para no perderte, volver atras si algo sale mal y trabajar en equipo sin pisarse los codigos.

</details> <details> <summary><strong>⚙️ Lo basico de Git</strong></summary>
La base de Git son los repositorios, que son como carpetas donde se guardan todas las versiones de tus archivos y los cambios que haces. Pueden ser:

Locales: Estan en tu compu.

Remotos: Estan en internet (como GitHub), para que varios puedan trabajar juntos.

Git usa ramas (branches), que te dejan hacer cosas nuevas sin tocar el codigo principal (que suele estar en main).

</details> <details> <summary><strong>🛠 Configuracion inicial de Git</strong></summary>
Antes de empezar, tienes que decirle a Git quien eres con tu nombre y correo. Se hace asi:

bash
git config --global user.name "Tu Nombre"  
git config --global user.email "tuemail@dominio.com"  
Asi todos tus cambios quedan con tu firma.

</details> <details> <summary><strong>🎨 Cambiar el editor de codigo que usa Git</strong></summary> Si quieres que Git abra tu editor favorito (como VSCode) cuando necesite que escribas algo, lo puedes configurar asi:
bash
git config --global core.editor "code --wait"  
</details> <details> <summary><strong>🔧 Revisar tu configuracion de Git</strong></summary> Para ver como tienes configurado Git, usa:
bash
git config --list  
Te muestra todo, desde tu nombre hasta el editor que usas.

</details> <details> <summary><strong>🚀 Como empezar un proyecto nuevo con Git</strong></summary> Para crear un repositorio Git en tu proyecto, solo haz:
bash
git init  
Y listo, Git empieza a rastrear todo lo que haces en esa carpeta.

</details>