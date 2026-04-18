# GeoJusticia CDMX

GeoJusticia es una plataforma ciudadana para identificar, priorizar y reportar problemas urbanos en la Ciudad de Mexico mediante contexto territorial.

## Idea del proyecto

En CDMX, muchas quejas urbanas no se atienden a tiempo por duplicidad, desorden y falta de priorizacion geografica. GeoJusticia transforma esos reportes en informacion accionable para ciudadania y alcaldias.

Objetivo principal:

- Facilitar denuncias ciudadanas claras y con seguimiento.
- Visualizar concentraciones de incidencias por zona.
- Apoyar la priorizacion territorial por tema y estatus.

Propuesta de valor:

- No es un buzon aislado de quejas.
- Es una herramienta de gestion urbana basada en datos.

## Arquitectura de carpetas

```text
.
├── README.md
├── package.json
├── package-lock.json
├── front/
│   ├── package.json
│   ├── src/
│   │   ├── components/
│   │   ├── data/
│   │   ├── pages/
│   │   ├── App.jsx
│   │   ├── index.css
│   │   └── main.jsx
│   └── ...
├── back/
│   ├── README.md
│   ├── src/
│   └── tests/
└── extra/
    ├── README.md
    ├── data/
    ├── documents/
    ├── notebooks/
    └── web/
```

Descripcion de carpetas:

- front: aplicacion principal (React + Vite).
- back: base para servicios y pruebas backend.
- extra: datasets, notebooks y recursos de referencia.

## Funcionalidad actual

Rutas principales:

- /: inicio con buscador de direcciones y sugerencias.
- /mapas: visor geoespacial con capas, filtros y metricas.
- /delegados_geojusticia: portal de denuncias.
- /denuncias: alias del portal de denuncias.

Flujo de uso:

1. El usuario busca una direccion.
2. El mapa se centra en la zona consultada.
3. El usuario revisa capas y contexto territorial.
4. El usuario registra una denuncia.
5. El sistema genera folio y guarda historial local.

Portal de denuncias:

- Seleccion de alcaldia con autocompletado.
- Seleccion de categoria y nivel de urgencia.
- Captura de datos de contacto y descripcion.
- Generacion de folio de reporte.
- Persistencia local en localStorage.

## Datos utilizados

### Datos usados directamente por la app actual

- Nominatim (OpenStreetMap): geocodificacion y sugerencias de direcciones.
- Datos operativos del mapa en front/src/data/geojusticiaMock.js:
  - COMPLAINTS
  - HEAT_POINTS
  - WIFI_POINTS
- Datos reales incorporados en frontend:
  - pasos-seguros-cdmx.csv (base de SAFE_CROSSINGS)
  - ubicacion_c5_c2.csv (base de C5_C2_LOCATIONS)

### Datos disponibles como referencia (no usados en runtime del frontend)

- 07-2025-wifi_gratuito_en_postes-del-c5.xlsx
- diccionario_coloniasiecm_2022.xlsx
- diccionario_datos_ri_6.csv
- equivalencias_parada_id.csv
- MEX-INEGI.40.201.01-INV-2010.xml
- archivos en extra/documents
- archivos en extra/web
- archivos en extra/notebooks

Nota:

- En esta version final del frontend no se usa pipeline de salud para render o logica funcional.

## Stack tecnologico

- React 19
- Vite
- React Router
- Leaflet
- React Leaflet
- leaflet.heat
- CSS por pagina/modulo

## Ejecucion local

Frontend:

```bash
cd front
npm install
npm run dev
```

Comandos utiles:

```bash
npm run build
npm run lint
```

## Estado del proyecto

Version final presentable (MVP funcional).

Incluye:

- Navegacion completa de Inicio a Mapas y Denuncias.
- Visualizacion territorial para apoyo de priorizacion urbana.
- Registro de denuncias con folio e historial local.

## Nombre oficial

Nombre oficial del proyecto: GeoJusticia.
