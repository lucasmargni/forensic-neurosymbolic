# forensic-neurosymbolic

## Requisitos

- [uv](https://docs.astral.sh/uv/), el gestor de dependencias y entornos de Python del proyecto.

No hace falta instalar Python a mano: uv descarga la versión indicada en `.python-version` (3.12) si no la encuentra en el sistema.

Para instalar uv en Linux o macOS:

```bash
curl -LsSf https://astral.sh/uv/install.sh | sh
```

## Instalación

```bash
git clone https://github.com/lucasmargni/forensic-neurosymbolic.git
cd forensic-neurosymbolic
uv sync
```

`uv sync` crea el entorno virtual en `.venv/` e instala las versiones exactas que figuran en `uv.lock`, incluidas las herramientas de desarrollo (Jupyter, pytest, ruff). Para instalar solo las dependencias principales, usá `uv sync --no-dev`.

## Uso

Con `uv run` los comandos se ejecutan dentro del entorno, sin tener que activarlo:

```bash
uv run python script.py
uv run jupyter lab
uv run pytest
```

## Manejo de dependencias

```bash
uv add <paquete>          # agrega una dependencia principal
uv add --dev <paquete>    # agrega una dependencia de desarrollo
uv remove <paquete>       # quita una dependencia
```

Estos comandos actualizan `pyproject.toml` y `uv.lock`.
