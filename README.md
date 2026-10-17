# Pam Bendito TV — Web de Directo

Web que detecta automaticamente cuando el canal [@pambenditoTV](https://www.youtube.com/@pambenditoTV) esta en directo en YouTube y muestra el stream en vivo. Se actualiza automaticamente en GitHub Pages.

## Como funciona

```
OBS --> YouTube (directo)
                |
    GitHub Action (cada 5 min) comprueba si hay directo
                |
        Actualiza status.json
                |
    index.html lee status.json cada 60s
                |
    EN DIRECTO --> muestra el embed de YouTube
    SIN DIRECTO --> muestra pantalla de espera elegante
```

## Configuracion inicial (solo una vez)

### 1. Subir a GitHub

```bash
git init
git add .
git commit -m "primera version"
git branch -M main
git remote add origin https://github.com/TU_USUARIO/TU_REPO.git
git push -u origin main
```

### 2. Activar GitHub Pages

1. Ve a tu repositorio en GitHub
2. Settings --> Pages
3. Source: Deploy from a branch
4. Branch: main / (root)
5. Guarda. En unos minutos tendra URL tipo: https://TU_USUARIO.github.io/TU_REPO

### 3. Activar permisos del workflow

1. Ve a Settings --> Actions --> General
2. En "Workflow permissions" selecciona **Read and write permissions**
3. Guarda

### Listo! El bot comprueba cada 5 minutos si estas en directo.

## Archivos

| Archivo | Descripcion |
|---------|-------------|
| `index.html` | La web principal |
| `status.json` | Estado del directo (actualizado por el bot) |
| `.github/workflows/check-live.yml` | GitHub Action que detecta el directo |

## Ejecucion manual del workflow

En GitHub: Actions --> "Detectar Directo YouTube" --> Run workflow
