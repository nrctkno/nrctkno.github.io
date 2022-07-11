Empleo nuevo, equipo nuevo. En esta ocasión, la compañía utiliza Mac para todo tipo de actividad, desde diseño y desarrollo hasta tareas administrativas. Yo, como humilde obrero procedente del mundo de Linux y Windows que soy, he tenido que adaptarme rápidamente a este nuevo entorno lo cual, reconozco, no ha sido tan fácil. Sin embargo, con el pasar de los días este nuevo entorno ha ido convirtiendo de un desafío en una experiencia positiva.

El propósito de este artículo es recopilar algunos conceptos y atajos que he tenido que aprender a las apuradas, para que usted, querido lector, no deba pasar por lo mismo. Debo reconocer que, salvando las diferencias entre este S.O. y los antes mencionados, varios aspectos resultan intuitivos y no requieren de configuraciones complejas en absoluto.

# Antes de comenzar

Cuando utilice la manzanita (🍎), me estaré refiriendo al ícono ubicado en la barra de menú, arriba a la izquierda:

# Administración de ventanas

El primer gran cambio que experimentamos en Mac es que las ventanas y las aplicaciones son conceptos diferentes. Una aplicación puede estar ejecutándose sin tener ventanas abiertas, o tener varias ventanas abiertas al mismo tiempo.

Maximizar: doble click en la barra de título, también en el menú Window > Zoom. Si la versión de Mac tiene por defecto la acción de pantalla completa, podemos presionar OPTION al posicionarnos sobre el botón verde, y cambiará al modo Zoom (maximizar).

Minimizar: COMMAND+M

Cerrar: COMMAND+W

Alternar entre aplicaciones: COMMAND+TAB

Alternar entre ventanas de una misma aplicación: COMMAND+tilde ("`", a la izquierda del "1")

Alternar entre pestañas de una misma ventana: CONTROL+TAB

Entrar/salir de pantalla completa: CONTROL+COMMAND+F

# Permisos

Este punto es muy importante, sobre todo antes de realizar nuestra primera videollamada. Es común encontrarnos con que nuestro navegador no detecte la cámara. Para configurarla: 🍎 > System preferences > Camera y agregaremos las aplicaciones autorizadas a acceder a la misma. Para que esta opción se active, debemos desbloquear la configuración tocando el candado en Click the lock to make changes abajo, a la izquierda.

# Teclado

## Configuración

Usar las teclas de función por defecto (en lugar de tener que presionar FN+tecla de función): 🍎 > System preferences > keyboard > Use F1, F2, etc. keys as standard function keys

También podrá consultar y personalizar todos los atajos de teclado en la sección Shortcuts de esta misma ventana de diálogo.

## Abrir aplicaciones

COMMAND+ESPACIO abrirá Spotlight, cuadro de búsqueda que nos permitirá iniciar cualquier aplicación. Otra opción es clickear en en ícono de Lanchpad en la barra de aplicaciones.

## Navegación

Saltar al principio/fin de una línea: COMMAND+IZQ, COMMAND+DER. Se puede combinar con la tecla SHIFT para seleccionar el texto.

Saltar entre palabras: OPTION+IZQ, OPTION+DER. Se puede combinar con la tecla SHIFT para seleccionar el texto.

Deshacer/rehacer: COMMAND+Z, COMMAND+SHIFT+Z

Mostrar ventanas de la aplicación actual: CONTROL+ABAJO

Mostrar todas las ventanas de todas las aplicaciones CONTROL+ARRIBA, también con el gesto de arrastrar tres dedos hacia arriba

Eliminar una palabra completa: OPTION+DELETE

Saltos de página: dado que no tenemos las teclas PAGE UP y PAGE DOWN, podemos utilizar el atajo FN+flechas.

Ir al principio o final de una página: el equivalente a CONTROL+INICIO/FIN es COMMAND+ARRIBA/ABAJO.

Desplegar emojis: presionar y soltar la tecla FN.

## Localización

Tildes: mantener la letra presionada; se mostrará un menú y se podrá elegir la tilde usando los números. Otra opción es presionar OPTION+E y luego la letra en cuestión (Ej: OPTION+E a escribirá á)

Barra vertical (pipe): está bajo la tecla DELETE 😉

Apertura de signo de interrogación: OPTION+SHIFT+?

## Acciones

Eliminar un ítem (ej. un archivo en Finder): COMMAND+DELETE

Copiar: COMMAND+C

Cortar: COMMAND+X

Pegar: COMMAND+V

Pegar sin formato: COMMAND+OPTION+SHIFT+V

## Capturas de pantalla

Guardar una región de pantalla: COMMAND+SHIFT+4 y seleccionar la región

Copiar una región de pantalla: COMMAND+SHIFT+CONTROL+4 y seleccionar la región


# Ratón

## Navegación

Scroll: arrastrar dos dedos hacia arriba o abajo

Mostrar widgets: arrastrar dos dedos desde afuera del pad por la derecha, hacia el centro

## Acciones

Click derecho: presionar con dos dedos sobre un ítem

Seleccionar varios elementos: presionando con un dedo (punto de anclaje) y arrastrando con el segundo dedo (fin de la selección).


# Herramientas

## Slack

No recibimos notificaciones: 🍎 > System preferences > Notifications and focus; seleccionamos Slack y veremos que la opción Allow notifications está desactivada. Podemos activarla y elegir el tipo de notificación que deseamos.

## GIT

Para instalar GIT, la opción más simple es escribir GIT en una shell; aparecerá un cartel que nos pregunta si deseamos instalar command line developer tools. Tardará un rato.

 
## Terminal

Limpiar la terminal: COMMAND+K

Cambiar la consola predeterminada: Mac nos permite usar zsh (predeterminada) ó bash. Para modificarla, 🍎 > System preferences >Users & groups; desbloqueamos los cambios haciendo click en el candado ubicado en la parte inferior izquierda, y presionando la tecla CONTROL hacemos click sobre nuestro usuario (que figura como Current user); se desplegará un menú con la opción Advanced options. Aquí podremos elegir la consola predeterminada en la sección Login shell. 