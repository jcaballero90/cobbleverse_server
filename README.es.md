# Cobbleverse Server en Docker Compose
## 

## Creditos
Creditos a Blue-Kachina por la solución (https://github.com/Blue-Kachina/cobbleverse_server)

## Cambios
1) Eliminada dependencia con sponge.
2) Actualizadas las versiones de Forge y Cobbleverse a fecha de 07/11/2025.
3) Corregido un problema donde la función `flatten_dp` en `install-modpack.sh` estaba eliminando el directorio `datapacks`.  
   La ausencia del directorio `datapacks` generaba un bug donde aparecía un mensaje en el chat indicando "Unknown series: kanto" en rojo, impidiendo que el jugador recibiera la Pokédex y la tarjeta de entrenador después de elegir el primer Pokémon.

## ¿Qué es esto?
### Cobbleverse
Cobbleverse es un modpack para Minecraft Java que brinda una experiencia similar a los juegos de pokemon al mundo de Minecraft.

### Docker
Docker es una herramienta que permite generar contenedores de aplicaciones y sus dependencias, funcionando de una manera muy parecida a las máquinas virtuales, pero de forma más ligera y eficiente.

### Esta solución en particular
Esta solución te permitirá levantar tu propio server Cobbleverse

## Instrucciones
### Primera vez
1) Asegurate de que tienes Docker/Docker Compose instalado.
2) Clona el repositorio
3) Ve a https://modrinth.com/modpack/cobbleverse/versions, haz click derecho sobre la versión de descarga deseada y selecciona "Copiar dirección del enlace"
4) Reemplaza el valor de MODRINTH_URL con el link obtenido en el paso anterior
5) Si quieres utilizar el env.file, establece tus valores deseados a las variables y cambiale el nombre de .env.example a .env. Si no quieres usar el env.file, modificalo directamente sobre el archivo
   docker-compose.yml, después del guión ("${MODRINTH_URL:-URL}"). Lo mismo para todas las variables.
6) Navega al directorio donde has clonado el repositporio
7) Ejecuta: `docker-compose up -d` Esto iniciará el servidor (Puede tardar un par de minutos)

#### ¿Qué pasara cuando haga esto?
1) El sistema revisara si el `worldname` especificado está en uso
2) En caso que no, creará un directorio para el mundo
3) Si es un nuevo mundo, los mods incluidos en el modpack se descargaran y guardaran en su respectivo lugar.
4) Se inicia el servidor de minecraft

### Recomendaciones
Descarga desde modrinth el cliente con la misma version que has utilizado para preparar el servidor. Recuerda que el cliente y servidor deben de tener la misma versión.
