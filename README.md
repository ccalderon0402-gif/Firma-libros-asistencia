# BERLIAM · Sistema de Consulta Firma Libro de Asistencia
## Guía de publicación en GitHub Pages

---

## Estructura de archivos

```
/
├── index.html          ← Página pública para trabajadores
├── trabajadores.json   ← Nómina generada por RRHH (actualizable)
├── firma_dia.png       ← Foto ejemplo firma turno DÍA
├── firma_noche.png     ← Foto ejemplo firma turno NOCHE
└── conversor.html      ← Herramienta interna RRHH (NO subir a GitHub)
```

> ⚠️ El archivo `conversor.html` es de uso interno RRHH. No es necesario subirlo a GitHub.

---

## Paso 1 — Preparar imágenes de firma

Toma fotos del libro físico mostrando cómo se debe firmar:

- `firma_dia.png` → Foto mostrando firma turno DÍA (entrada 08:00, salida 20:00)
- `firma_noche.png` → Foto mostrando firma turno NOCHE (entrada 20:00, salida 08:00 día siguiente)

---

## Paso 2 — Generar trabajadores.json

1. Abre `conversor.html` en cualquier navegador (no requiere internet)
2. Carga el Excel de dotación con columnas: **NOMBRE COMPLETO**, **RUT**, **TURNO**
3. Mapea las columnas si es necesario
4. Descarga el archivo `trabajadores.json` generado

---

## Paso 3 — Subir a GitHub

### Opción A: Desde GitHub.com (interfaz web)

1. Crea un repositorio nuevo en https://github.com
2. Sube estos archivos arrastrándolos:
   - `index.html`
   - `trabajadores.json`
   - `firma_dia.png`
   - `firma_noche.png`
3. Ve a **Settings → Pages**
4. En **Source** selecciona: `Deploy from a branch`
5. Branch: `main` / Folder: `/ (root)`
6. Haz clic en **Save**

### Opción B: Desde terminal (Git)

```bash
git init
git add index.html trabajadores.json firma_dia.png firma_noche.png
git commit -m "Sistema BERLIAM - v1"
git remote add origin https://github.com/TU_USUARIO/TU_REPO.git
git push -u origin main
```

---

## Paso 4 — Obtener el link público

Después de activar GitHub Pages, tu URL será:

```
https://TU_USUARIO.github.io/TU_REPOSITORIO/
```

Comparte ese link con los trabajadores. Solo verán el buscador por RUT.

---

## Paso 5 — Actualizar la dotación

Cuando cambie la dotación o los turnos:

1. Abre `conversor.html` localmente
2. Carga el nuevo Excel
3. Descarga el nuevo `trabajadores.json`
4. Reemplaza **solo ese archivo** en GitHub
5. La página se actualiza automáticamente en ~1 minuto

---

## Seguridad

- El Excel **nunca** se sube a internet
- Los trabajadores **solo** pueden buscar por RUT
- El JSON solo contiene nombre, RUT y turno (sin datos sensibles adicionales)
- GitHub Pages es HTTPS por defecto

---

## Soporte

Sistema desarrollado para **BERLIAM Servicios Mineros**  
Proyecto: MTTO L4 · Minera Los Pelambres  
Área: RRHH Mantención
