# Guía: Cómo Subir a GitHub

Instrucciones paso a paso para crear el repositorio y subirlo a GitHub.

## Opción 1: Desde cero (recomendado)

### 1. Crear repositorio en GitHub

1. Ve a https://github.com/new
2. Ingresa con tu cuenta (crea una si no tienes)
3. Completa:
   - **Repository name**: `claude-abogados`
   - **Description**: `Guía interactiva de Claude, Proyectos, Artefactos y Cowork para abogados`
   - **Visibility**: Public (si quieres compartirlo)
   - **Initialize with**:
     - ✅ Add .gitignore (selecciona "None")
     - ✅ Add a license (selecciona "MIT")
4. Haz click en **Create repository**

### 2. Clonar y agregar archivos (desde tu computadora)

```bash
# Clonar el repositorio vacío
git clone https://github.com/TU_USUARIO/claude-abogados.git
cd claude-abogados

# Copiar los archivos en esta carpeta:
# - index.html
# - README.md
# - .gitignore
# - GITHUB_SETUP.md
# - LICENSE (opcional, GitHub lo crea automáticamente)

# Verificar que los archivos están
ls -la

# Agregar los archivos al repositorio
git add .

# Crear primer commit
git commit -m "Commit inicial: Guía interactiva de Claude para abogados"

# Subir a GitHub
git push origin main
```

### 3. Activar GitHub Pages (para que sea accesible en web)

1. Ve a tu repositorio en GitHub
2. Haz click en **Settings** (engranaje)
3. En el menú izquierdo, selecciona **Pages**
4. Bajo "Build and deployment":
   - Branch: `main`
   - Carpeta: `/ (root)`
5. Haz click en **Save**

GitHub mostrará: "Your site is live at `https://tu-usuario.github.io/claude-abogados`"

---

## Opción 2: Si ya tienes una carpeta local

```bash
# Desde la carpeta con los archivos
cd /ruta/a/tu/carpeta

# Inicializar Git
git init

# Agregar un .gitignore
curl https://raw.githubusercontent.com/github/gitignore/main/Node.gitignore > .gitignore

# Agregar todos los archivos
git add .

# Crear primer commit
git commit -m "Commit inicial: Guía interactiva Claude para abogados"

# Cambiar rama a 'main' (si Git la creó como 'master')
git branch -M main

# Agregar el repositorio remoto
git remote add origin https://github.com/TU_USUARIO/claude-abogados.git

# Subir a GitHub
git push -u origin main
```

---

## Opción 3: Desde GitHub Desktop (GUI, más fácil)

### Para no técnicos:

1. **Instala GitHub Desktop**: https://desktop.github.com
2. **Abre la app** → "Create a New Repository"
3. Completa:
   - **Name**: `claude-abogados`
   - **Local Path**: Selecciona carpeta donde guardar
   - **Initialize**: ✅ Create a README file
4. Haz click en **Create Repository**
5. Copia los archivos (`index.html`, `README.md`, `.gitignore`) a esa carpeta
6. En GitHub Desktop:
   - Verás los cambios en la lista
   - Escribe mensaje: "Commit inicial: Guía interactiva"
   - Haz click en **Commit to main**
7. Haz click en **Publish repository**
8. Completa credenciales de GitHub

---

## Verificar que funcionó

### 1. El repositorio está en GitHub
- Abre https://github.com/tu-usuario/claude-abogados
- Deberías ver los archivos listados

### 2. El sitio está en vivo
- Abre https://tu-usuario.github.io/claude-abogados
- Deberías ver la guía interactiva

### 3. Verificar Pages está activo
- En el repo de GitHub → **Settings** → **Pages**
- Status: "Your site is published..."

---

## Próximos pasos (opcional)

### Agregar un dominio personalizado
1. En **Settings** → **Pages** → Custom domain
2. Ingresa tu dominio: `nombre.com`
3. Sigue las instrucciones de DNS

### Agregar colaboradores (si trabajas en equipo)
1. En el repo → **Settings** → **Collaborators**
2. Invita otros usuarios

### Automatizar actualizaciones
1. Crea un `workflow` en `.github/workflows/` para:
   - Validar links
   - Minificar HTML
   - Deploys automáticos

### Agregar temas (para mejor SEO)
1. En el repo → **About** (engranaje)
2. Topics: `claude`, `ai`, `legal-tech`, `abogados`, `argentina`

---

## Comandos Git básicos (referencia rápida)

```bash
# Ver estado
git status

# Agregar cambios
git add .           # Todos los archivos
git add archivo.md  # Un archivo específico

# Commit
git commit -m "Descripción del cambio"

# Subir a GitHub
git push origin main

# Bajarse cambios (si otro contribuyó)
git pull origin main

# Ver historial
git log --oneline

# Deshacer último cambio (antes de push)
git reset --soft HEAD~1
```

---

## Troubleshooting

### "fatal: not a git repository"
```bash
# Solución:
git init
git remote add origin https://github.com/tu-usuario/claude-abogados.git
```

### "Permission denied (publickey)"
```bash
# Solución: Configurar SSH keys
ssh-keygen -t ed25519
# Copiar contenido de ~/.ssh/id_ed25519.pub
# Pegar en GitHub → Settings → SSH keys → New SSH key
```

### "everything up-to-date" (pero no veo cambios en GitHub)
```bash
# Solución: Verificar que estás en la rama correcta
git branch
# Deberías ver: * main (el asterisco indica rama activa)

# Si estás en 'master' en lugar de 'main':
git branch -M main
git push -u origin main
```

### GitHub Pages no muestra la guía
1. Verifica que **Settings** → **Pages** → Branch está en `main`
2. Espera 5-10 minutos (GitHub necesita tiempo para publicar)
3. Vacía el cache del navegador (Ctrl+Shift+R o Cmd+Shift+R)
4. Verifica que `index.html` está en el root (no en carpeta)

---

## Licencia y Atribución

Si subiste con licencia MIT (recomendado):
- ✅ Otros pueden copiar, modificar y compartir
- ⚠️ Deben incluir atribución a ti
- 📋 Ver `LICENSE` en el repo

---

## Recursos útiles

- **GitHub Docs**: https://docs.github.com
- **Git cheat sheet**: https://github.github.com/training-kit/downloads/github-git-cheat-sheet.pdf
- **GitHub Pages docs**: https://docs.github.com/en/pages
- **Tutorial interactive Git**: https://learngitbranching.js.org

---

**¿Necesitas ayuda?**
- Abre un issue en GitHub Discussions
- Email: [tu-contacto]
- Stack Overflow: Tag `github` + `git`

---

**Última actualización**: Agosto 2026
