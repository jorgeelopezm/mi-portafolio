---
description: Publica el portafolio en GitHub Pages (verifica, commitea y, tras confirmar, pushea a main)
argument-hint: "[asunto de commit opcional]"
allowed-tools: Bash(git status:*), Bash(git add:*), Bash(git diff:*), Bash(git log:*), Bash(git commit:*), Bash(git push:*), Bash(ls:*)
---

# Deploy a GitHub Pages

Publica el sitio estático de este repositorio en GitHub Pages (rama `main`). Sigue los
pasos en orden y **no hagas push hasta que el usuario lo confirme explícitamente**.

Asunto de commit proporcionado por el usuario (puede estar vacío): **$ARGUMENTS**

## Pasos

1. **Verifica la raíz.** Comprueba que `index.html` existe en la raíz del repositorio
   (es requisito de GitHub Pages). Si no está, **detente** y explica el problema; no
   continúes con el commit.

2. **Revisa el estado.** Ejecuta `git status` y `git diff` (y `git diff --staged` si
   aplica) para entender qué cambió. Si no hay nada que commitear, avísalo y termina.

3. **Prepara los cambios.** Ejecuta `git add -A`.

4. **Define el mensaje de commit:**
   - Si **$ARGUMENTS** no está vacío, úsalo tal cual como **asunto** del commit.
   - Si está vacío, **autogenera** un asunto en formato Conventional Commits
     (`feat:`, `fix:`, `docs:`, `style:`, `refactor:`, `chore:`…) a partir del diff,
     y añade un cuerpo breve con viñetas que resuma los cambios.

5. **Commitea.** El shell por defecto de este entorno es **PowerShell**: para mensajes
   multilínea usa un here-string `@'...'@` (con `'@` en la columna 0) o varios flags `-m`.
   ⚠️ No uses la sintaxis `@'...'@` dentro de la herramienta *Bash* — ahí el `@` se
   interpreta literalmente y acaba en el asunto del commit. Cierra el mensaje con:

   ```
   Co-Authored-By: Claude Opus 4.8 <noreply@anthropic.com>
   ```

6. **Pausa para confirmar.** Muestra un resumen (asunto del commit + archivos incluidos) y
   **pregunta al usuario si desea hacer push a `main`**. Espera su respuesta. No pushees
   sin un "sí" explícito.

7. **Push.** Tras la confirmación, ejecuta `git push origin main` y reporta el resultado
   (incluido cualquier error de autenticación).

8. **Recordatorio de GitHub Pages.** Indica al usuario que confirme en
   **GitHub → repo → Settings → Pages**: *Source* = **Deploy from a branch**, rama
   **`main`**, carpeta **`/ (root)`**. La URL publicada será
   `https://jorgeelopezm.github.io/mi-portafolio/`.
