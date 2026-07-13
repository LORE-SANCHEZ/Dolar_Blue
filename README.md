# 💵 Dólar Blue Scraper
# [Cotización del Dólar Blue](captura.png)

Herramienta desarrollada en **Python** que obtiene de forma automática la cotización del **dólar blue** (compra y venta) desde distintos portales financieros de Argentina, y la muestra en una ventana simple mediante una interfaz gráfica.

El objetivo es evitar la búsqueda manual en varias páginas web: el programa hace el trabajo de consultar, extraer y ordenar la información en segundos.

---

## ⚙️ ¿Cómo funciona?

El programa aplica **Web Scraping**, una técnica que permite extraer información directamente del código de una página web, simulando la visita de un usuario real.

El flujo de trabajo es el siguiente:

1. **Solicitud HTTP**: el programa se conecta a cada sitio web (Clarín, Cronista y DolarHoy) usando la librería `requests`, incluyendo un encabezado (`User-Agent`) que simula ser un navegador convencional, para evitar bloqueos.
2. **Extracción de datos**: con `BeautifulSoup` se recorre el HTML (o el JSON embebido, en el caso de Clarín) de cada página, hasta localizar los valores de compra y venta del dólar blue.
3. **Formateo de valores**: los números obtenidos se convierten a un formato de moneda legible (por ejemplo, `$ 1.250,50`).
4. **Presentación de resultados**: se abre una ventana con `tkinter` que muestra, fuente por fuente, los valores de compra y venta obtenidos.
5. **Manejo de errores**: si alguna fuente no responde o cambia su estructura, el programa lo detecta y continúa con las demás fuentes disponibles, sin interrumpir la ejecución.

---

## 🌐 Fuentes de datos

| Fuente | Dato que aporta |
|---|---|
| [Clarín](https://www.clarin.com/economia/divisas-acciones-bonos/monedas/dolar-blue) | Cotización compra/venta (extraída de JSON embebido) |
| [Cronista](https://www.cronista.com/MercadosOnline/moneda.html?id=ARSB) | Cotización compra/venta (extraída de HTML) |
| [DolarHoy](https://dolarhoy.com/cotizaciondolarblue) | Cotización compra/venta (extraída de HTML) |

> Nota: si alguna de estas páginas modifica su estructura HTML, la función de extracción correspondiente puede requerir ajustes.

---

## 🛠️ Tecnologías utilizadas

- **Python 3**
- [`requests`](https://pypi.org/project/requests/) — para las solicitudes HTTP
- [`BeautifulSoup4`](https://pypi.org/project/beautifulsoup4/) — para el parseo de HTML
- `re` y `json` — para procesar datos embebidos en formato JSON
- `tkinter` — para la interfaz gráfica (incluida en la instalación estándar de Python)

---

## 📦 Instalación

1. Cloná este repositorio:
```bash
git clone https://github.com/LORE-SANCHEZ/Dolar_Blue.git
cd Dolar_Blue
```

2. Instalá las dependencias necesarias:
```bash
pip install requests beautifulsoup4
```

> `tkinter` ya viene incluido con Python en la mayoría de los casos. Si no lo tenés, en Windows se instala junto con Python desde [python.org](https://www.python.org/downloads/).

---

## ▶️ Uso

Ejecutá el archivo principal:
```bash
python dolar_blue_tk.pyw
```

Se abrirá una ventana con la cotización de compra y venta del dólar blue según cada fuente consultada.

---

## 📋 Ejemplo de salida

```
Clarin    - Compra: $ 1.250,00 , Venta: $ 1.270,00
Cronista  - Compra: $ 1.248,50 , Venta: $ 1.268,00
DolarHoy  - Compra: $ 1.249,00 , Venta: $ 1.269,00
```

---

## 🚀 Posibles mejoras futuras

- Agregar más fuentes de cotización
- Guardar un historial de valores en un archivo o base de datos
- Mostrar un gráfico de evolución del valor a lo largo del tiempo
- Actualización automática cada X minutos

---

## 👩‍💻 Autora

**Lorena Sánchez**
Desarrollo en Python | Web Scraping | Automatización

📫 Contactame por [LinkedIn](#) *https://www.linkedin.com/in/lorenasanchezcrearcontextos/*

---

## 📄 Licencia

Este proyecto es de código abierto. Podés usarlo, modificarlo y compartirlo libremente.
