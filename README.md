# **Simple-Robot-Trading** 🤖

Este proyecto es un Challenge propuesto por el equipo de Alura LATAM para el Bootcamp de Ciencia de Datos. </br>
`Robot-Trading` es un programa simple que identifica cuando comprar, vender o esperar para comprar Bitcoin, de acuerdo al promedio de los precios de cierre del Bitcoin en los últimos 7 días en los que hubo transacciones, además de eso, toma la decisión acorde a las tendencias de cada hora de la página [CoinMarketCap](https://coinmarketcap.com/).

## ⚙️ ¿Cómo funciona?

El flujo del programa está dividido en 6 etapas principales:

### 1. Configuración del entorno

Se importan las bibliotecas necesarias para manejo de datos, visualización, extracción web y automatización:

- `pandas`
- `numpy`
- `matplotlib`
- `yfinance`
- `bs4` (BeautifulSoup)
- `requests`
- `IPython.display`
- `time`

### 2. Obtención de datos

- **Históricos:** Se descargan precios históricos de Bitcoin en intervalos de 5 minutos usando la API de Yahoo Finance (`yfinance`).
- **Actuales:** Se hace web scraping desde CoinMarketCap para obtener el precio actual y la tendencia (subida o bajada).

### 3. Limpieza y análisis

- Se eliminan duplicados y valores sin volumen de transacción.
- Se filtran los precios de cierre dentro del rango intercuartílico (`Q1` a `Q3`).
- Se calcula el **precio medio** del Bitcoin con estos datos filtrados.

### 4. Toma de decisión

Reglas simples:

- Si el precio actual es mayor o igual que el promedio y la tendencia es **baja**, la decisión es **vender**.
- Si el precio actual es menor que el promedio y la tendencia es **alta**, la decisión es **comprar**.
- En otros casos, se recomienda **esperar**.

### 5. Visualización

Se grafica el precio de cierre más reciente junto con el promedio y una flecha indicando la acción recomendada.

### 6. Automatización

El proceso se repite cada 5 minutos. Puede detenerse de forma segura con `Ctrl + C` sin errores.

---

## Ejemplo
![prueba](https://github.com/user-attachments/assets/9a965c8a-fe31-4ed9-badb-026859744acf)


