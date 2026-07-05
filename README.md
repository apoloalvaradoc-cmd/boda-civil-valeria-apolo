# Valeria & Apolo · Boda Civil · Invitación

Invitación web para la **boda civil** de Valeria & Apolo (8 de agosto 2026, Punta de Palma,
Izabal). Archivo único: `index.html` — sin build, sin dependencias, **sin base de datos**.

Es un proyecto independiente de la invitación de la boda (7 de noviembre); comparte la
estructura pero con contenido, paleta (costera/marina) y confirmación propios.

---

## 1. Arquitectura

- **Frontend**: `index.html` (HTML/CSS/JS vanilla, un solo archivo, autocontenido).
- **Sin backend**: no usa Supabase ni ninguna base de datos.
- **Confirmación de asistencia**: botón de **WhatsApp** con mensaje pre-escrito.
- **Assets**: artes costeros de la invitación (`portada.png`, `info.jpg`, `plan.jpg`,
  (sello de concha, olas) es SVG/CSS inline.

---

## 2. Secciones

1. **Portada** (`portada.png`) · toca el sello de concha para abrir.
2. **Invitación principal** (`conjunto.png`) · arte completo (sobre + conchas + flores); primera imagen tras la animación.
3. **Cuenta regresiva** · hacia el 8 de agosto 2026.
4. **El plan del día** (`plan.jpg`) · 4:00 ceremonia · 6:00 cena · 8:00 fiesta · 11:00 fin.
5. **Cómo llegar** (`caracol.png`) · Muelle Municipal 3:00 p.m. + lanchas a Punta de Palma, Maps/Waze.
6. **Confirmación** · botón de WhatsApp.
7. **Dress code de playa**, **Regalos**, **FAQ**, **Cierre**.

---

## 3. Configuración

Edita `CONFIG` al inicio del `<script>` en `index.html`:

```js
const CONFIG = {
  brideName: "Valeria",
  groomName: "Apolo",
  weddingDateISO: "2026-08-08T16:00:00-06:00",   // fecha/hora de la boda civil (GT, UTC-6)
  bankAccount: "1591672",
  whatsappNumber: "50200000000",                  // ← PONER el número real (solo dígitos: 502 + número)
  whatsappMessage: "Hola Valeria y Apolo ...",    // mensaje pre-escrito de confirmación
};
```

### Pendientes antes de publicar
- [ ] Poner el **número de WhatsApp** real en `CONFIG.whatsappNumber`.
- [ ] Revisar/afinar los links de **Google Maps / Waze** del Muelle Municipal (sección `location`).
- [ ] (Opcional) Reemplazar los medallones SVG por **fotos reales** de la pareja.
- [ ] Confirmar horarios del **itinerario** y datos de **regalos**.

---

## 4. Correr localmente

```bash
npx http-server . -p 5199 -c-1
# abre http://localhost:5199
```

---

## 5. Despliegue

Archivo estático — cualquier host sirve.

- **GitHub Pages**: push a un repo, Settings → Pages → deploy desde `main` (`index.html` en raíz).
- **Netlify Drop**: arrastra la carpeta a <https://app.netlify.com/drop>.
- **Vercel**: `vercel` en la carpeta.

---

## 6. Archivos

```
boda-civil-valeria-apolo/
├── index.html          ← la invitación completa (texto, estilos, JS)
├── portada.png         ← arte de portada (sello de concha)
├── conjunto.png        ← arte completo (primera imagen tras abrir)
├── plan.jpg            ← "El Plan" (itinerario del día)
├── caracol.png          ← punto de reunión / lanchas
├── README.md           ← este documento
└── .gitignore
```
