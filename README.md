# Proceso de contacto con pesos sobre el grafo completo

Código computacional asociado al trabajo de grado **“El proceso de contacto con pesos en un grafo completo: análisis probabilístico y simulaciones”**, desarrollado en la Maestría en Estadística de la Universidad Nacional de Colombia.

**Autor:** Carlos Alberto Ramos Ortiz  
**Año:** 2026

## Contenido

El repositorio contiene dos cuadernos de Jupyter/Google Colab:

1. [`01_simulaciones_trayectorias.ipynb`](notebooks/01_simulaciones_trayectorias.ipynb)  
   Implementa el método directo de Gillespie para el proceso de contacto con pesos sobre el grafo completo. Incluye trayectorias en los regímenes subcrítico, crítico y supercrítico, ejemplos con distintas distribuciones de pesos y el efecto del tamaño del grafo.

2. [`02_tiempos_extincion.ipynb`](notebooks/02_tiempos_extincion.ipynb)  
   Estudia numéricamente el tiempo de extinción en función del número de vértices. Incluye simulaciones Monte Carlo, comparación con escalas logarítmicas, polinomiales y exponenciales, y una implementación acelerada mediante Fenwick tree y `numba`.

## Modelo

Se considera el proceso de contacto con pesos sobre un grafo completo finito. Cada vértice posee un peso no negativo que modifica la intensidad de las interacciones. Las simulaciones parten de todos los vértices infectados y utilizan el método directo de Gillespie.

## Requisitos

Los notebooks están diseñados para ejecutarse en Python y pueden abrirse directamente en Google Colab. Las dependencias principales son:

```text
numpy
matplotlib
numba
```

En Google Colab, `numpy` y `matplotlib` suelen estar disponibles por defecto. Si `numba` no está instalado, el segundo notebook incluye una alternativa sin compilación JIT, aunque la ejecución puede ser más lenta.

## Reproducibilidad

Las semillas de los generadores pseudoaleatorios se fijan explícitamente dentro de los notebooks. Para reproducir los resultados, se recomienda ejecutar las celdas en orden desde el inicio.

El segundo notebook puede requerir un tiempo de cómputo considerable en el régimen supercrítico. Cuando una trayectoria alcanza el máximo número de eventos antes de extinguirse, el notebook la registra como censurada. En tamaños con censura, la media mostrada se calcula únicamente con las trayectorias que alcanzaron la extinción antes del corte computacional; el número de casos censurados queda almacenado en `censurados`.

## Ejecución local

```bash
git clone <URL-DEL-REPOSITORIO>
cd proceso-contacto-pesos
pip install -r requirements.txt
jupyter notebook
```

También puede abrirse cada archivo `.ipynb` desde Google Colab seleccionando **Archivo → Abrir cuaderno → GitHub** una vez publicado el repositorio.

## Referencia

Ramos Ortiz, Carlos Alberto (2026). *El proceso de contacto con pesos en un grafo completo: análisis probabilístico y simulaciones*. Trabajo de grado, Maestría en Estadística, Universidad Nacional de Colombia.
