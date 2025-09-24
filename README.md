# Diagrama de Bifurcación en Internet con Datos Reales

## Andres Castro, Juan Hurtado, Franco Comas

## Resumen

Este proyecto implementa un modelo de **dinámica no lineal** para analizar el comportamiento caótico en métricas de Internet, utilizando un **diagrama de bifurcación**.  
Se usaron datos abiertos de **Speedtest by Ookla** (CC BY-NC-SA 4.0), con más de **4.7 millones de filas** que incluyen información de ancho de banda, latencia y número de pruebas por tile geográfico.

Colab: https://colab.research.google.com/drive/1FybYKjhhU887_wLy3mo4lHu-Nfk5fpIi?usp=sharing
---

## Dataset

* **Fuente**: [Speedtest by Ookla Open Data](https://www.speedtest.net/insights/blog/ookla-open-data/)
* **Tamaño usado**: 4,744,330 filas
* **Campos principales**:
  * `avg_d_kbps`: velocidad de descarga (kbps)
  * `tests`: número de pruebas realizadas
  * `download_mbps`: velocidad de descarga convertida a Mbps
  * `download_mbps_clip`: velocidad de descarga en Mbps con recorte de valores extremos (para normalizar)
* **Cobertura temporal**: desde Q1 2019 hasta el trimestre más reciente
* **Licencia**: CC BY-NC-SA 4.0

---

## Matemática esencial

### 1. Mapa logístico
<img width="236" height="75" alt="image" src="https://github.com/user-attachments/assets/d052ad5c-7487-4b7d-89dd-d4a8f248a419" />


* `x_n`: variable normalizada (ej. Mbps entre 0 y 1)  
* `r`: parámetro de control (mapeado desde variaciones de ancho de banda)  

### 2. Exponente de Lyapunov
<img width="281" height="119" alt="image" src="https://github.com/user-attachments/assets/ebc9c9b5-2cec-4d5a-945c-a38daf3e9fe3" />


* `lambda < 0` → orden  
* `lambda > 0` → caos  

### 3. Derivada del mapa logístico
<img width="195" height="64" alt="image" src="https://github.com/user-attachments/assets/d956b2d2-c735-4819-af44-281bc9d6327f" />


### 4. Ruta a caos
La duplicación de periodo sigue la constante de Feigenbaum (δ ≈ 4.669).

---

## Resultados

<img width="737" height="489" alt="image" src="https://github.com/user-attachments/assets/e48b81ba-1253-4473-a532-1d967b12c6c3" />

*Figura 1. Diagrama de bifurcación usando r mapeado desde Ookla Mobile Download.*

---

## Conclusiones

La gráfica muestra cómo, al aumentar el parámetro `r` (derivado de datos reales de Internet), el sistema transita de estados estables a duplicación de periodo y, finalmente, a caos.  
Esto sugiere que las redes de Internet pueden presentar dinámicas sensibles e impredecibles bajo ciertas condiciones (congestión, cambios de tecnología, picos de tráfico).

---

## Referencias

* Speedtest by Ookla Open Data  
* Strogatz, S. *Nonlinear Dynamics and Chaos*  
* Feigenbaum, M. (1978). *Quantitative Universality for a Class of Nonlinear Transformations*
