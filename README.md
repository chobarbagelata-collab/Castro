# Buenos Aires - Nueva York, Sept 2026

Sitio estático de una sola página con la propuesta de viaje. Todo el diseño (HTML + CSS + JS) vive en `index.html`; las fotos están en `images/` como archivos sueltos.

## Estructura

```
bue-nyc-sept2026/
├── index.html
├── images/
├── vercel.json      # config mínima para Vercel (URLs limpias)
├── .gitignore
└── README.md
```

## 1. Subir a GitHub

Desde esta carpeta:

```bash
git init
git add .
git commit -m "Propuesta de viaje"
git branch -M main
git remote add origin https://github.com/<tu-usuario>/<nombre-del-repo>.git
git push -u origin main
```

(Primero creá el repo vacío en https://github.com/new — sin README, sin licencia, para evitar conflictos al pushear.)

## 2. Desplegar en Vercel

**Opción A — desde la web:**
1. Entrá a https://vercel.com/new
2. Importá el repositorio de GitHub que acabás de crear
3. Vercel detecta que es un sitio estático automáticamente (no hace falta build command ni output directory)
4. Deploy

**Opción B — desde la CLI:**
```bash
npm i -g vercel
vercel login
vercel --prod
```

## Notas

- No hay build step ni dependencias — es HTML/CSS/JS puro.
- Cualquier cambio de precios, fechas o textos se edita directamente en `index.html` y se resuelve con un nuevo `git push` (Vercel redeploya solo). Para cambios grandes, es más prolijo volver a `proposal.json` y regenerar con `build_proposal.py`.
