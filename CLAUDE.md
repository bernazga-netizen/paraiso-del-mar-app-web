# Paraíso del Mar — App Tablets

## Stack
- HTML + CSS + JavaScript vanilla (sin frameworks)
- Deploy en Vercel, producción en branch `main`
- Preview automática en cualquier otro branch

## Archivos
- `index.html` — menú selector de tablets (landing)
- `tablet.html` — app unificada para los 3 puntos de acceso

## Lógica de tablets
`tablet.html` detecta qué tablet es por el parámetro `?tablet=` en la URL:

| Punto de acceso | URL | PIN |
|---|---|---|
| Muelle Principal | `/tablet.html?tablet=muelle` | 1029 |
| Base 4 | `/tablet.html?tablet=base4` | 3847 |
| Base 1 | `/tablet.html?tablet=base1` | 5665 |

- El PIN es específico por tablet
- Al ingresar PIN correcto, solo muestra el botón del acceso correspondiente
- El guardia no puede registrar en el acceso equivocado
- No usar `sessionStorage` para el login — solicitarlo siempre al abrir la URL

## Backend
- URL producción: `https://paraiso-del-mar-backend.onrender.com`
- Endpoint principal: `POST /api/registros`

## Paleta de colores — usar siempre estas variables
```css
--teal:      #007c89;
--teal-lt:   #71aeb7;
--teal-pale: #e8f4f6;
--navy:      #003660;
--navy-lt:   #0a4a7a;
--emerald:   #006b35;
--dust:      #f2efec;
--ink:       #1a2e3a;
--ink-mid:   #3d5a66;
--border:    #c2d8dd;
--warn:      #c87533;
```

## Tipografía
- Cormorant Garamond — numerales
- Jost — texto de UI

## Logo
- Archivo: `PDM_Logo_Primary_RGB.png` (ruta relativa)

## Reglas críticas
- No crear archivos separados por tablet — toda la lógica vive en `tablet.html`
- Cualquier nuevo punto de acceso se agrega como nuevo valor del parámetro `?tablet=`
- La app está diseñada para uso en tablet física con pantalla táctil
