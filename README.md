# 🤖 HypeBotFarming

<div align="center">
  <img src="https://img.shields.io/badge/Python-3.8+-blue.svg" alt="Python 3.8+">
  <img src="https://img.shields.io/badge/License-MIT-green.svg" alt="License: MIT">
  <img src="https://img.shields.io/badge/Platform-Hyperliquid-purple.svg" alt="Platform: Hyperliquid">
  <img src="https://img.shields.io/badge/Interface-Telegram-blue.svg" alt="Interface: Telegram">
</div>

<p align="center">
  <b>Un sistema avanzado de trading automatizado con inteligencia artificial para tokens en Hyperliquid, con interfaz conversacional vía Telegram</b>
</p>

---

## 📁 Descripción

**HypeBotFarming** es una solución de trading automatizado que integra inteligencia artificial, estrategias algorítmicas y sistemas expertos para operar de forma segura y eficiente en la plataforma Hyperliquid. Su objetivo es maximizar el rendimiento y minimizar el riesgo a través de decisiones inteligentes y personalizadas.

Este bot fue desarrollado como proyecto final del Grado en Inteligencia Artificial y Big Data, y combina programación asíncrona, procesamiento de series temporales, visualización de datos, y aprendizaje automático.

## 📚 Arquitectura del Sistema

### 🔎 Enfoque Modular

El sistema está organizado en tres capas:

1. **Interfaz de Usuario (Telegram Bot):**

   * Gestiona la comunicación con el usuario.
   * Permite enviar comandos, ver balances, configurar estrategias.

2. **Lógica de Negocio:**

   * Motor de estrategias automáticas.
   * Sistema experto para decisiones adaptativas.
   * Módulo de predicción LSTM.

3. **Integración con Exchanges:**

   * API de Hyperliquid.
   * Manejo seguro de wallets y ejecución de órdenes.

### 🪧 Novedades:

* **Modelo LSTM integrado**: entrenado con datos reales de BTC, utilizando indicadores técnicos y etiquetas inteligentes.
* **Sistema experto**: toma decisiones basadas en reglas adaptativas, evaluando condiciones excepcionales.
* **Almacenamiento distribuido**: uso de Amazon S3 y Elasticsearch para trazabilidad y visualización.

## 🌟 Características Clave

* Ciclos automáticos de trading cada 10 minutos (configurable).
* Estrategias Farming / Neutro / Hardcore.
* Configuración vía Telegram.
* Sistema de predicción con LSTM.
* Balanceo automático del dataset.
* Reportes visuales (PnL, volumen, historial).
* Dashboard en React (interfaz web opcional).

## 📈 Modelo de IA y Sistema Experto

### Modelo LSTM:

* Entrada: secuencias de 48 horas de datos escalados (RSI, MACD, Bollinger, etc.).
* Salida: probabilidad de señal (-1, 0, 1).
* Entrenado en Jupyter con EarlyStopping y Dropout para evitar overfitting.

### Sistema Experto:

* Evalúa rentabilidad, riesgo, volatilidad, tendencia y volumen.
* Desautoriza operaciones o ajusta parámetros.
* Se activa esporádicamente en eventos de mercado adversos.

## 🌌 Flujo de Datos

1. Se obtienen datos de mercado.
2. El modelo LSTM genera predicciones.
3. El sistema experto analiza y aprueba/rechaza la acción.
4. Se ejecuta la orden en Hyperliquid.
5. Se almacena el resultado en JSON (S3) y se indexa en Elastic.
6. Se actualiza el dashboard y se notifica al usuario.

## 🔒 Seguridad y Rendimiento

* Acceso restringido por ID.
* Variables sensibles en `.env`.
* Reintentos automáticos ante fallos.
* Caché en peticiones a la API.
* Asincronía con `asyncio` para eficiencia.
* Almacenamiento en la nube (S3 + Elastic).

## 🏃 Instalación Rápida

```bash
# Clona el repositorio
git clone https://github.com/tu-usuario/HypeBotFarming.git
cd HypeBotFarming

# Crea el entorno virtual
python -m venv venv
source venv/bin/activate  # Windows: venv\Scripts\activate

# Instala dependencias
pip install -r requirements.txt

# Ejecuta el bot
python main.py
```

## 🔍 Exploración Avanzada

* `/start`, `/menu`, `/auto_trading`, `/balance`, `/manual_position`, `/signals`, `/trading_report`.
* Modo manual + automático.
* Cambio entre Farming, Neutro y Hardcore desde Telegram.

## 🔧 Estructura del Proyecto

```
/HypeBotFarming
├── main.py                  # Entrada del sistema
├── telegram_bot.py          # UI Telegram
├── auto_trading_strategy.py # Ciclos y estrategias
├── expert_system.py         # Sistema experto
├── model_loader.py          # Carga del modelo .h5
├── trading_api.py           # Conexión a Hyperliquid
├── utils.py, config.py      # Auxiliares y configuración
├── .env                     # Variables privadas
├── logs/, backups/, tests/  # Persistencia y pruebas
```

## 🚀 Desarrollo Futuro

* Más tokens soportados.
* Estrategias basadas en sentimiento.
* Backtesting en dashboard.
* Mejora de UX con interfaz web ampliada.

---

<p align="center">
  <b>Desarrollado como proyecto final para el Grado en Inteligencia Artificial y Big Data</b><br>
  <i>2025 © HypeBotFarming Team</i>
</p>
