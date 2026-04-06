# Predicción de Precios de Acciones con RNN

Modelo de predicción de precios bursátiles usando una Red Neuronal Recurrente (SimpleRNN) con datos obtenidos via `yfinance` e indicadores técnicos EMA. Incluye un visualizador interactivo para usar directamente en Google Colab.

---

## ¿Cómo usarlo?

1. Abrí `rnn_prediccion_acciones.ipynb` en [Google Colab](https://colab.research.google.com/)
2. Ejecutá la **celda 1** para instalar las dependencias
3. Ejecutá la **celda 2** para cargar el visualizador
4. Ingresá el ticker de la acción (ej: `TSLA`, `AAPL`, `GOOGL`)
5. Seleccioná la fecha de inicio para el entrenamiento de la RNN
6. Hacé click en **Correr predicción**

---

## ¿Qué muestra?

**Gráfico 1 — Historial completo**
Precio de cierre ajustado desde el inicio de los datos disponibles.

**Gráfico 2 — Predicción RNN**
Últimos 30 días reales + predicción a 7 días, con indicadores EMA 20 y EMA 50 superpuestos.

**Señal de tendencia**
Antes de los gráficos se imprime una señal automática basada en la posición del precio respecto a las EMAs:
- **Alcista**: precio por encima de EMA 20 y EMA 50
- **Bajista**: precio por debajo de EMA 20 y EMA 50
- **Mixta**: precio entre EMA 20 y EMA 50

---

## Modelo

- Arquitectura: `SimpleRNN (256 unidades) → Dense (1)`
- Optimizador: Adam
- Función de pérdida: MSE
- Ventana de secuencia: 7 días
- Forecast: iterativo, 7 días hacia adelante
- Escalado: MinMaxScaler

---

## Dependencias

```
yfinance
tensorflow
scikit-learn
pandas
numpy
matplotlib
ipywidgets
```

> En Google Colab todas se instalan automáticamente con la primera celda del notebook.

---

## Estructura del repositorio

```
├── rnn_prediccion_acciones.ipynb        # Notebook principal con visualizador interactivo
└── README.md
```

---

## Advertencia

Este proyecto es de carácter **educativo**. Las predicciones generadas por el modelo no constituyen asesoramiento financiero y no deben usarse para tomar decisiones de inversión.
