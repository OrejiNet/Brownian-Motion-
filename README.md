# Simulación del Movimiento Browniano

Simulación computacional del movimiento browniano de un conjunto de partículas
mediante la integración numérica de la **ecuación de Langevin** por el método de
Euler, implementada en Python. El proyecto incluye una animación 3D interactiva
de la nube de partículas y la verificación física del comportamiento difusivo a
través del desplazamiento cuadrático medio (MSD).

Trabajo desarrollado para el **Módulo de Programación** del Diplomado en
Fundamentos de la Física, Universidad de Chile (2026).

## ¿Qué simula?

El movimiento browniano es el desplazamiento errático de una partícula
microscópica suspendida en un fluido, causado por los choques continuos con las
moléculas que la rodean. La dinámica se describe con la ecuación de Langevin:

$$m\frac{d\mathbf{V}}{dt} = -\zeta\,\mathbf{V} + \mathbf{F}$$

donde el primer término es la fricción del fluido (proporcional a la velocidad)
y el segundo es una fuerza estocástica que modela los choques moleculares.

Discretizada por el método de Euler, con el incremento de Wiener para la fuerza
aleatoria:

$$\mathbf{V}_{i+1} = \left(1 - \frac{\zeta}{m}\Delta t\right)\mathbf{V}_i + \frac{1}{m}\Delta\mathbf{W}_i, \qquad \mathbf{R}_{i+1} = \mathbf{R}_i + \mathbf{V}_i\,\Delta t$$

## Características

- Simulación de cientos de partículas independientes en 3D, vectorizada con NumPy.
- Animación interactiva con Plotly: botón de reproducción, deslizador temporal y
  rotación con el mouse. Las partículas se colorean según su rapidez instantánea.
- Verificación física: el desplazamiento cuadrático medio reproduce la ley de
  difusión $\langle R^2 \rangle = 6Dt$, con el coeficiente de difusión dado por
  la relación de Einstein $D = k_BT/\zeta$.

## Requisitos

- Python 3
- NumPy
- Plotly
- Matplotlib

Pensado para ejecutarse en **Google Colab** (no requiere instalación local;
todas las librerías vienen preinstaladas).

## Uso

1. Abre el notebook `Movimiento_Browniano_Simulation.ipynb` en Google Colab.
2. Ejecuta las celdas en orden (menú *Entorno de ejecución → Ejecutar todo*).
3. Ajusta los parámetros de la simulación en la celda correspondiente para
   explorar distintos escenarios (número de partículas, pasos, temperatura,
   fricción, paso de tiempo).

Los parámetros principales:

| Parámetro | Descripción |
|---|---|
| `numero_particulas` | Cantidad de partículas a simular |
| `numero_pasos` | Pasos de integración temporal |
| `paso_tiempo` | Incremento de tiempo Δt |
| `coeficiente_friccion` | Fricción del fluido (ζ) |
| `masa_particula` | Masa de cada partícula |
| `temperatura` | Temperatura (kᵦT) |

## Estructura del repositorio

- `Movimiento_Browniano_Simulation.ipynb` — notebook con la simulación, la
  animación y la verificación.
- `informe.pdf` — informe del proyecto (introducción, desarrollo, resultados y
  conclusiones).

## Referencias

- Hoyuelos, M. (2022). *Introducción al no equilibrio: Mecánica estadística y
  termodinámica de procesos irreversibles*. Editorial Reverté.
- Schilling, R. L., Partzsch, L., & Böttcher, B. (2014). *Brownian Motion: An
  Introduction to Stochastic Processes* (1.ª ed.). De Gruyter.
- Rosero Cárdenas, O. D. (2021). *Simulación computacional del movimiento
  browniano* [Proyecto final, Física Estadística, Universidad de Nariño].
  https://www.youtube.com/watch?v=zFQnLPknXus

## Autor

Cristopher René Alexander Angulo Ahumada
