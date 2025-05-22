# JS Ofuscador

Una potente herramienta para ofuscar código JavaScript y protegerlo de ingeniería inversa.

![JS Ofuscador](https://via.placeholder.com/800x400?text=JS+Ofuscador)

## Características

- ✨ Ofuscación avanzada de código JavaScript
- 🛡️ Cuatro niveles predefinidos de ofuscación (bajo, medio, alto, extremo)
- 🔐 Técnicas anti-desofuscación de nivel militar
- 🧬 Ofuscación metamórfica y polimórfica
- 🔄 Interfaz web moderna y responsiva con EJS
- 💻 Potente interfaz de línea de comandos (CLI)
- 📁 Capacidad para procesar archivos individuales o directorios completos
- 📦 Soporte para procesar archivos ZIP
- 🧪 Verificación de sintaxis de código
- 📊 Estadísticas detalladas del proceso de ofuscación
- 🔌 Disponible como API para integrar en otros proyectos

## Requisitos previos

- Node.js (v12.0.0 o superior)
- npm (v6.0.0 o superior)

## Instalación

### Instalación local

```bash
git clone https://github.com/tu-usuario/js-ofuscador.git
cd js-ofuscador
npm install
```

### Instalación global

Para usar la herramienta desde cualquier ubicación:

```bash
npm install -g .
```

## Uso

### Interfaz web

Inicia el servidor web:

```bash
npm start
```

El servidor se iniciará en `http://localhost:3000` donde encontrarás una interfaz amigable para:

- Ofuscar código JavaScript directamente desde el editor
- Subir y ofuscar archivos .js o archivos .zip con múltiples scripts
- Configurar diferentes niveles y opciones de ofuscación
- Ver estadísticas del proceso
- Descargar el código ofuscado

### Interfaz de línea de comandos (CLI)

#### Ver comandos disponibles

```bash
js-ofuscador --help
```

#### Ofuscar un archivo JavaScript

```bash
js-ofuscador ofuscar ruta/al/archivo.js
```

#### Usar un preset de configuración

```bash
js-ofuscador ofuscar ruta/al/archivo.js -p alto
```

#### Usar el nivel extremo con técnicas avanzadas

```bash
js-ofuscador ofuscar ruta/al/archivo.js -p extremo -X
```

#### Ofuscar con opciones personalizadas

```bash
js-ofuscador ofuscar ruta/al/archivo.js -o ruta/de/salida.js -c true -f 0.8 -d 0.5 -i hexadecimal -s true
```

#### Ofuscar un directorio completo

```bash
js-ofuscador ofuscar ruta/al/directorio -o ruta/de/salida -r true
```

#### Excluir archivos

```bash
js-ofuscador ofuscar ruta/al/directorio -e "node_modules,*.min.js,*.test.js"
```

#### Vista previa de ofuscación

```bash
js-ofuscador preview ruta/al/archivo.js -p medio -l 50
```

#### Verificar sintaxis de un archivo

```bash
js-ofuscador verificar ruta/al/archivo.js
```

#### Ver presets disponibles

```bash
js-ofuscador presets
```

### Opciones de ofuscación

| Opción | Descripción | CLI | Interfaz Web |
|--------|-------------|-----|--------------|
| Preset | Nivel predefinido de ofuscación (bajo, medio, alto, extremo) | `-p, --preset` | ✅ |
| Técnicas avanzadas | Aplica técnicas anti-desofuscación extremas | `-X, --advanced-techniques` | ✅ |
| Compacto | Elimina espacios y saltos de línea | `-c, --compact` | ✅ |
| Control Flow | Dificulta el análisis de flujo de código | `-f, --flow` | ✅ |
| Código muerto | Inserta código que nunca se ejecuta | `-d, --dead-code` | ✅ |
| Identificadores | Forma de generar nombres de variables | `-i, --identifiers` | ✅ |
| Auto-defensivo | Código que se rompe si es formateado | `-s, --self-defending` | ✅ |
| Array de strings | Mueve strings a un array separado | `-S, --string-array` | ✅ |
| Codificación | Tipo de codificación para strings | `-E, --string-encoding` | ✅ |
| Unicode | Usa secuencias unicode | `-u, --unicode` | ✅ |
| Renombrar globales | Cambia nombres de variables globales | `-n, --rename-globals` | ✅ |
| Deshabilitar console | Elimina llamadas a console.log | `-D, --disable-console` | ✅ |
| Protección de depuración | Dificulta la depuración | `-B, --debug-protection` | ✅ |

## Nivel de ofuscación extremo

El nivel de ofuscación `extremo` activa todas las técnicas de protección disponibles:

- **Auto-verificación de integridad**: El código verifica que no ha sido manipulado
- **Protección anti-debugging**: Previene cualquier intento de análisis mediante herramientas de depuración
- **Multi-capa de ofuscación**: Aplica múltiples pasadas de ofuscación con diferentes técnicas
- **Código señuelo**: Inserta código aparentemente válido pero inaccesible para confundir analizadores
- **Encriptación de strings**: Utiliza múltiples técnicas de encriptación para proteger cadenas
- **Verificación de ejecución**: Incluye mecanismos para detectar entornos no autorizados

⚠️ **ADVERTENCIA**: El nivel extremo puede generar códigos significativamente más grandes y potencialmente incompatibles con algunos entornos. Use con precaución.

## API

También puedes usar JS Ofuscador como una biblioteca en tu propio código:

```javascript
const { ofuscarCodigo, ofuscarArchivo, ofuscarDirectorio, verificarSintaxis } = require('js-ofuscador');

// Ofuscar un string de código con un preset
const resultado = ofuscarCodigo('console.log("Hola Mundo")', 'alto');
console.log(resultado.code); // Código ofuscado
console.log(resultado.metadata); // Estadísticas del proceso

// Ofuscar con nivel extremo y técnicas avanzadas
const resultadoExtremo = ofuscarCodigo('console.log("Hola Mundo")', 'extremo', true);
console.log(resultadoExtremo.metadata.securityLevel); // 'extremo'

// Verificar sintaxis de un código
const verificacion = verificarSintaxis('function miFunc() { return x + }');
if (!verificacion.valido) {
  console.error(`Error de sintaxis: ${verificacion.error}`);
}

// Ofuscar un archivo
ofuscarArchivo('entrada.js', 'salida.js', 'medio')
  .then(resultado => console.log(`Archivo guardado en: ${resultado.outputPath}`))
  .catch(error => console.error(error));

// Ofuscar un directorio con exclusiones
ofuscarDirectorio('src', 'dist', 'extremo', true, ['*.min.js', 'node_modules'], true)
  .then(resultado => console.log(`${resultado.metadata.processedFiles} archivos procesados`))
  .catch(error => console.error(error));
```

## Contribuir

Las contribuciones son bienvenidas. Si quieres mejorar esta herramienta, sigue estos pasos:

1. Haz un fork del proyecto
2. Crea una rama para tu funcionalidad (`git checkout -b feature/nueva-funcionalidad`)
3. Haz tus cambios y commits
4. Envía un pull request

## Licencia

MIT 
