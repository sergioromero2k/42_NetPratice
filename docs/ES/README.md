*This project has been created as part of the 42 curriculum by serromer.*

# NetPractice

## Descripcion

NetPractice es un proyecto practico de redes del curriculum de 42. El objetivo es configurar redes simuladas a pequena escala ajustando correctamente las direcciones IP, mascaras de subred y puertas de enlace predeterminadas para que los dispositivos puedan comunicarse entre si.

El proyecto consta de 10 niveles de complejidad creciente, desde conexiones simples entre dos hosts hasta topologias con multiples routers que requieren configuracion de rutas estaticas. Todas las redes son simuladas y se accede a ellas a traves de una interfaz web local; no se utiliza hardware real.

---

## Instrucciones

### Arrancar la interfaz

1. Descarga los archivos del proyecto desde la pagina del proyecto en 42 y extrae el contenido en la carpeta que prefieras.
2. Abre una terminal en esa carpeta.
3. Ejecuta el script de arranque:
   ```bash
   ./run.sh
   ```
4. La interfaz se abrira automaticamente en tu navegador. Si el script no funciona, arranca el servidor local manualmente:
   ```bash
   python3 -m http.server 49242
   ```
   Luego navega a `http://localhost:49242` en tu navegador.

### Trabajar con los niveles

- Introduce tu login de intranet (`serromer`) en la interfaz antes de empezar. Esto genera tu configuracion personal.
- Cada nivel muestra un diagrama de red que no funciona. Modifica los campos sin sombrear (direcciones IP, mascaras de subred, rutas) hasta que la red funcione correctamente.
- Usa el boton **Check again** para verificar tu configuracion.
- Los logs en la parte inferior de la pagina te indicaran exactamente que falla si la verificacion no pasa.
- Cuando completes un nivel aparecera el boton **Next level**.

### Exportar las configuraciones

Tras completar cada nivel, haz clic en **Get my config** para descargar tu archivo de configuracion. Hazlo antes de pasar al siguiente nivel, ya que no se puede recuperar despues.

### Entrega

- Coloca los **10 archivos de configuracion** (uno por nivel) en la raiz de tu repositorio Git junto a este README.
- Haz commit y push como de costumbre. Solo se evalua lo que este en el repositorio.

Estructura esperada del repositorio:

```
.
├── README.md
├── level1.cfg
├── level2.cfg
├── level3.cfg
├── level4.cfg
├── level5.cfg
├── level6.cfg
├── level7.cfg
├── level8.cfg
├── level9.cfg
└── level10.cfg
```

> Usa los nombres exactos de archivo que genera el boton "Get my config".

---

## Defensa por pares

Durante la defensa tendras que resolver **3 niveles aleatorios** en un tiempo limitado. No se permiten herramientas externas; solo se tolera una calculadora basica como `bc`. Debes ser capaz de explicar cada valor que introduzcas, por lo que entender los conceptos es imprescindible.

---

## Recursos

### Conceptos de red estudiados

- **Direccionamiento TCP/IP** — como se enrutan los paquetes IP a traves de redes interconectadas
- **Mascaras de subred** — como determinar las partes de red y host de una direccion IP y calcular rangos de hosts validos
- **Notacion CIDR** — representacion de mascaras de subred como longitud de prefijo (por ejemplo /24, /28)
- **Puerta de enlace predeterminada** — la interfaz del router que usa un host para alcanzar destinos fuera de su propia subred
- **Enrutamiento estatico** — rutas configuradas manualmente en una tabla de rutas, incluida la ruta por defecto `0.0.0.0/0`
- **Routers y switches** — el papel de cada dispositivo en el reenvio de trafico dentro de un segmento de red y entre segmentos
- **Modelo OSI** — el modelo de comunicacion en red de siete capas, con especial atencion a la capa 2 (enlace de datos) y la capa 3 (red)

### Material de referencia

- [Cisco Networking Basics — Coursera](https://www.coursera.org/learn/networking-basics)
- [Subnetting Practice — subnettingpractice.com](https://subnettingpractice.com)
- [RFC 791 — Internet Protocol](https://datatracker.ietf.org/doc/html/rfc791)
- [Wikipedia — Classless Inter-Domain Routing](https://en.wikipedia.org/wiki/Classless_Inter-Domain_Routing)

### Uso de IA

Las herramientas de IA se usaron de las siguientes maneras durante el proyecto:

- **Aclaracion de conceptos** — consultar explicaciones en lenguaje sencillo sobre notacion CIDR, calculo de subredes y logica de tablas de rutas cuando la documentacion escrita no era suficientemente clara.
- **Formato de documentacion** — estructurar y mejorar la redaccion de este README.
- **Verificacion** — despues de trabajar la logica de un nivel de forma independiente, usar la IA para comprobar el razonamiento antes de contrastarlo con otros estudiantes.

Ningun valor de configuracion fue copiado de la salida de una IA. Todas las soluciones se trabajaron manualmente y se verificaron a traves de la interfaz y con discusion entre pares, conforme a las normas del proyecto.
