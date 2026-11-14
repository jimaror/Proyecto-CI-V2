# 📘 Aprendiendo Git — Bitácora del curso de Git y GitHub

**Autor:** Jimmy Javier Marquez Orozco (`jimaror`)
**Curso:** Git y GitHub · 2026
**Profesor:** Roderick David Zapata
**Repositorio:** <https://github.com/jimaror/Proyecto-CI>

---

## 📌 Qué es este repositorio

Es la **bitácora personal del curso de Git y GitHub**. Cada sección de la
página `index.html` documenta una capacidad que se practicó en clase, y cada
sección tiene su **rama propia** y sus **commits** que demuestran el
aprendizaje.

La página se puede abrir directamente en el navegador: no necesita servidor
ni instalación.

---

## 🗂️ Estructura del proyecto

```
Proyecto-CI/
├── index.html          # La bitácora (8 secciones)
├── CSS/
│   └── estilo.css      # Estilos de la página
├── img/                # Recursos gráficos
├── README.md           # Este archivo
└── .gitignore          # Exclusiones de archivos
```

---

## 🧭 Mapa de las secciones y su rama

Cada capacidad del curso tiene una rama asociada. El grafo completo se ve
con el alias `git g`:

| Sección | Tema | Rama | Commit |
|---|---|---|---|
| 2.1 | Instalación y configuración | `main` | `841ba4e` |
| 2.2 | Mi primer repositorio | `main` | `0ede459` |
| 2.3 | Ciclo de vida | `main` | `29c2ef6` |
| 2.4 | Exclusión con `.gitignore` | `main` | `703231c` |
| 3.1 | Ramas | `feature/seccion-ramas` | `a5992bf` |
| 3.2 | Fusiones y conflictos | `feature/seccion-3-2` | `d9a39c8` |
| 3.3 | Bitácora completa | `feature/seccion` | `4587bbe` |
| 3.4 | Historial y recuperación | `feature/seccion-historial` | `6cf3f76` |

---

## 🔀 Ramas del repositorio

```text
  feature/css                 CSS: tamaño de código
  feature/footer              Nuevo pie de página
  feature/seccion             Bitácora de Git con mi nombre
  feature/seccion-3-2         Agrega sección 3.2 y redefine rama
  feature/seccion-ramas       Agrega sección de ramas
* main                        (rama activa)
```

---

## 📚 Capacidades practicadas

### 3.4 · Historial, restauración y recuperación

- **Inspeccionar** el historial con `log`, `blame` y `show`
  (filtrar por mensaje, por contenido, por autor).
- **Comparar** versiones entre commits, ramas y archivos con `diff`.
- **Recuperar** con `revert` (seguro, no reescribe), `reset`
  (`--soft` / `--mixed` / `--hard`), `reflog` (el diario de HEAD) y etiquetas.
- **Gestionar** varios cambios temporales con `stash`, y crear una rama
  desde un cajón con `git stash branch`.

### 3.1 · Ramas locales, remotas y mantenimiento

Creación de ramas, sincronización con el remoto y limpieza de ramas
obsoletas.

### 3.2 · Fusiones

Fusión *fast-forward* y fusión de tres vías con resolución de conflictos
(commit `98ece63 Merge feature/footer (--no-ff)`).

---

## 🧪 Comandos usados en la práctica

```bash
# Inspeccionar
git log --oneline --graph --all --decorate
git log --grep="sección" --oneline
git log -S "conflicto" --oneline
git shortlog -sn HEAD
git blame -L 25,30 index.html

# Comparar
git show HEAD~3 --stat
git diff HEAD~5 HEAD --stat
git diff HEAD~5 HEAD -- index.html
git show HEAD~19:index.html

# Recuperar
git revert HEAD --no-edit
git reset --soft  HEAD~1
git reset --mixed HEAD~1
git reset --hard  HEAD~1
git reflog -8
git reset --hard <hash>

# Temporal
git stash push -m "descripcion"
git stash push -u -m "descripcion"
git stash list
git stash show -p "stash@{1}"
git stash branch feature/seccion-historial "stash@{1}"
git stash drop

# Publicar
git tag -a v1.0 -m "Pagina Aprendiendo Git con la capacidad 3"
git push
git push origin v1.0
```

---

## 🏷️ Versiones

| Etiqueta | Commit | Significado |
|---|---|---|
| `v1.0` | `6cf3f76` | Página con la capacidad 3 completa |

Para volver a esa versión:

```bash
git switch --detach v1.0
```

---

## 🧭 La regla de oro de Git

| Situación | Solución |
|---|---|
| Cambio ya compartido | `git revert` (no reescribe la historia) |
| Commits solo locales | `git reset --soft / --mixed / --hard` |
| Commit "perdido" | `git reflog` → volver al hash |
| Cambios a medias | `git stash` → cajón temporal |

> **Compartido → `revert`. Local → `reset`. ¿Perdido? → `reflog`.**

---

## 📖 Documentos de apoyo

| Archivo | Contenido |
|---|---|
| `COMANDOS-PARA-DIGITAR.md` | Todos los comandos de la práctica, en orden, listos para copiar en la terminal (PowerShell y Git Bash) |
| `QUE-ES-EL-GIT-GRAPH.txt` | Diferencia entre la extensión de VS Code y el `--graph` de la terminal |

---

## 🔗 Recursos

- [Pro Git en español](https://git-scm.com/book/es/v2)
- [Referencia de comandos](https://git-scm.com/docs)
- [Learn Git Branching](https://learngitbranching.js.org)

---

*Curso de Git y GitHub · 2026 · Hecho por Jimmy Javier Marquez Orozco con Git*
