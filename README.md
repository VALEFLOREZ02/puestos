# Sistema de puestos (gratis)

- `index.html`  → **página pública** (solo ve disponible / sin pagar / pagado).
- `admin.html`  → **administración** (requiere correo y contraseña). Ventas, pagos, pendientes, resumen y CSV.

Costo: $0 (GitHub Pages + Firebase plan Spark, sin tarjeta).

## Paso a paso
1. Entra a https://console.firebase.google.com → **Crear proyecto** (puedes desactivar Analytics).
2. En el proyecto:
   - **Build → Firestore Database → Crear base de datos** (modo producción, cualquier región).
   - **Build → Authentication → Comenzar → Correo/contraseña → Habilitar**. Luego pestaña *Users → Add user* con TU correo y una contraseña.
3. **Configuración del proyecto (engranaje) → Tus apps → `</>` Web** → registra la app y copia los valores de `firebaseConfig` dentro de `firebase-config.js`.
4. **Firestore → Reglas**: pega el contenido de `firestore.rules`, cambia `TU_CORREO@gmail.com` por tu correo y pulsa **Publicar**. (Esto es lo que mantiene privados los datos.)
5. Sube estos archivos a un repositorio de GitHub → **Settings → Pages → Deploy from branch (main, /root)**.
6. Enlaces:
   - Público (compártelo): `https://TU_USUARIO.github.io/TU_REPO/`
   - Admin (solo tú): `https://TU_USUARIO.github.io/TU_REPO/admin.html`
7. Entra al admin → **Ajustes**: define número de puestos, precio y vendedores.

Los cambios que haces en admin se reflejan solos en la página pública.
