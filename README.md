# Zona Rental The Warehouse · Mérida

Sitio web informativo e interactivo para presentar **Zona Rental The Warehouse**, ubicada en Calle Progreso, Ejido 5101, estado Mérida, Venezuela.

La página reúne información general del complejo, una representación 3D conceptual de la zona industrial, un modelo 3D de referencia de un galpón, la ubicación geográfica, una galería fotográfica y un panel de administración de demostración.

## Vista general

- **Identidad visual:** diseño responsive con una paleta basada en blanco, negro y azul.
- **Presentación del complejo:** descripción general y navegación por las secciones principales.
- **Espacios industriales:** sección pública para mostrar galpones y su estado de disponibilidad.
- **Recorrido 3D:** maqueta conceptual con naves perimetrales, cubiertas naranja, fachadas blancas y patio central. Permite rotar, acercar y cambiar entre vistas.
- **Galpón 3D:** modelo conceptual con cubierta naranja, paredes blancas, portón industrial y puerta peatonal independiente.
- **Ubicación:** mapa incrustado de OpenStreetMap y enlaces para abrir Google Maps o consultar cómo llegar.
- **Galería:** área para mostrar fotografías del complejo.
- **Panel administrativo de demostración:** permite registrar, editar y eliminar espacios, cargar o eliminar fotografías y revisar solicitudes creadas desde ese navegador.
- **Formulario de contacto:** prepara un mensaje de consulta. Se puede configurar un número de WhatsApp para abrir la conversación con el mensaje escrito.

## Ubicación

**Dirección:** Calle Progreso, Zona Rental The Warehouse, Ejido 5101, Mérida, Venezuela.

**Coordenadas:** `8.5308889, -71.2493333`  
**Coordenadas en grados, minutos y segundos:** `8°31'51.2"N 71°14'57.6"W`

## Tecnologías utilizadas

- HTML5.
- CSS3, con diseño adaptable a móviles y escritorio.
- JavaScript (módulos ES).
- [Three.js](https://threejs.org/) `0.160.0` para las escenas tridimensionales.
- `OrbitControls` de Three.js para rotación y zoom de los modelos.
- [OpenStreetMap](https://www.openstreetmap.org/) para el mapa incrustado.
- Google Maps para los enlaces de ubicación e indicaciones.
- IndexedDB del navegador para guardar los datos locales de demostración.

No requiere un proceso de compilación ni instalar dependencias mediante npm. Three.js y el mapa se cargan desde servicios externos, por lo que se necesita conexión a Internet para esas funciones.

## Cómo ejecutar el proyecto localmente

1. Descarga o clona este repositorio.
2. Abre una terminal en la carpeta del proyecto.
3. Inicia un servidor HTTP local. Por ejemplo, con Python:

   ```bash
   python -m http.server 8000
   ```

4. Abre en el navegador:

   ```text
   http://localhost:8000/
   ```

   Si conservas el nombre original del archivo, abre:

   ```text
   http://localhost:8000/zona-industrial-the-warehouse.html
   ```

Se recomienda utilizar un servidor HTTP local en lugar de abrir el archivo directamente con `file://`, ya que la página utiliza módulos JavaScript.

## Publicar en GitHub Pages

Para publicar el sitio desde la raíz del repositorio:

1. Coloca el archivo HTML en la raíz del repositorio.
2. Renómbralo a `index.html` para que GitHub Pages lo identifique como página de inicio.
3. Guarda este archivo como `README.md` en la raíz.
4. Sube los cambios a GitHub.
5. En el repositorio, entra en **Settings → Pages**.
6. En **Build and deployment**, selecciona **Deploy from a branch**.
7. Selecciona la rama que contiene el sitio (por ejemplo, `main`) y la carpeta `/ (root)`; guarda los cambios.

Cuando GitHub Pages termine la publicación, mostrará la dirección pública del sitio en la misma sección de Pages.

## Panel administrativo de demostración

El panel puede abrirse desde el enlace **Administración** al pie de la página. También se puede utilizar el atajo `Alt + A` en equipos compatibles.

Desde el panel es posible:

- Registrar un galpón o espacio con su código, área aproximada, estado, empresa o arrendatario, fecha y notas.
- Editar o eliminar registros.
- Cargar fotografías JPG, PNG o WEBP de hasta 12 MB por archivo.
- Eliminar fotografías cargadas.
- Consultar las solicitudes generadas desde esa misma instalación local.

### Limitaciones importantes de la versión actual

Esta versión es una **demostración frontend**, no un sistema administrativo multiusuario:

- Los datos se guardan en IndexedDB del navegador y dispositivo donde se utiliza la página.
- Los registros y fotografías no se sincronizan con otros administradores ni se publican en una base de datos central.
- Las solicitudes del formulario quedan guardadas localmente. Si no se configura WhatsApp, el sitio intenta copiar el mensaje para compartirlo manualmente; no envía correos ni solicitudes a un servidor.
- El panel no tiene inicio de sesión ni control de permisos. Cualquier persona que acceda a la página puede abrirlo.
- Los datos locales pueden perderse al borrar los datos del navegador o cambiar de dispositivo.

**No introduzcas información confidencial, documentos, datos personales sensibles ni información contractual en esta versión.** Antes de utilizar el panel en operaciones reales, se debe implementar autenticación, autorización por roles, una base de datos central, almacenamiento remoto de imágenes y copias de seguridad.

## Configurar el contacto por WhatsApp

En el archivo HTML, busca esta línea dentro del módulo JavaScript:

```javascript
const CONFIG = { whatsapp: '' };
```

Introduce el número de WhatsApp con código de país, sin el signo `+`, espacios ni guiones. Ejemplo de formato:

```javascript
const CONFIG = { whatsapp: '584121234567' };
```

Sustituye el número de ejemplo por el número oficial autorizado para recibir consultas. Si se deja vacío, el formulario no abrirá WhatsApp y ofrecerá copiar el mensaje para compartirlo manualmente.

## Personalización y próximos pasos

Antes de utilizar el sitio como presentación comercial definitiva, se recomienda:

1. Sustituir la maqueta y el galpón conceptuales por modelos 3D basados en planos, medidas y levantamientos reales.
2. Incorporar fotografías actuales y autorizadas de las instalaciones.
3. Confirmar la nomenclatura, áreas y disponibilidad de cada galpón con la administración.
4. Configurar el canal oficial de contacto.
5. Si se necesita administración compartida, implementar un backend seguro con autenticación, base de datos y almacenamiento de imágenes.

> **Nota sobre los modelos:** la geometría 3D actual es ilustrativa y se ajustó visualmente a la fotografía aérea y a las imágenes de fachadas suministradas como referencia. No representa un levantamiento topográfico, un plano acotado ni documentación constructiva.

## Estado del proyecto

Versión inicial de presentación web y demostración interactiva. La publicación del sitio estático puede realizarse con GitHub Pages; las funciones administrativas multiusuario requieren desarrollo e infraestructura adicionales.
