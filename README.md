# Jeke Bayesian Model Prototype

Prototipo de modelo bayesiano jerárquico para predicción de resultados de fútbol usando PyMC.

Basado en el paper de Baio y Blangiardo, implementado con datos de Understat.

## Video explicativo

Este notebook es un prototipo que acompaña al video donde explico todo el proceso:

[![YouTube](https://img.shields.io/badge/YouTube-Video-red?logo=youtube)](https://youtu.be/TATxOI4a6c8)

## Pruébalo sin instalar nada

👉 [![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/jeke-deportivas/jeke-bayesian-model-prototype/master?urlpath=%2Fdoc%2Ftree%2Fjeke-bayesian-model-prototype.ipynb)

## Requisitos

- Python 3.13.9
- pyenv (recomendado)

## Instalación

```bash
bin/setup
source .venv/bin/activate
```

## Uso

Abrir el notebook `jeke-bayesian-model-prototype.ipynb` en Jupyter:

```bash
jupyter notebook
```

## Estructura del modelo

El modelo estima:
- **home**: ventaja de jugar en casa
- **atts**: rating de ataque por equipo
- **defs**: rating de defensa por equipo

La expectativa de goles se calcula como:

```
home_goals ~ Poisson(exp(home + atts[home_team] + defs[away_team]))
away_goals ~ Poisson(exp(atts[away_team] + defs[home_team]))
```

## Datos

Los datos se obtienen de Understat mediante `understatapi`. Por defecto descarga la Premier League temporadas 2024 y 2025.

Ligas disponibles: EPL, La_Liga, Bundesliga, Serie_A, Ligue_1, RFPL

## Licencia

[MIT](LICENSE)
