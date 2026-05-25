# Calculadora de Integrales Avanzada (USO DE HILOS)

Una aplicación de escritorio moderna y de alto rendimiento diseñada para la resolución analítica y numérica de 
integrales, construida utilizando **Python**, **PySide6 (Qt para Python)**, **SymPy**, **SciPy** y **Matplotlib**. 
El proyecto implementa un flujo de trabajo asíncrono multi-hilo para evitar 
el congelamiento de la interfaz gráfica durante cálculos matemáticos complejos y pesados.

---

## Estructura y Organización del Proyecto

A continuación, se presenta el diagrama de cómo está organizado el código fuente y los componentes del sistema:

```text
Calculadora_Integrales - USO DE HILOS/
│
├── main.py                  # Punto de entrada de la aplicación y manejo de la pantalla de carga (Splash Screen)
├── main.spec                # Archivo de configuración de PyInstaller para la compilación a ejecutable (.exe)
├── requirements.txt         # Lista de dependencias y librerías externas del proyecto
│
├── ui/                      # Módulos encargados de la interfaz gráfica de usuario (GUI)
│   ├── __init__.py          # Inicializador del paquete de interfaz
│   ├── calculator.py        # Ventana principal, panel de control, teclado matemático, lógica asíncrona e impresión PDF
│   ├── math_view.py         # Componente basado en QWebEngineView para renderizar LaTeX fluido con MathJax local
│   └── plot_dialog.py       # Ventana emergente interactiva para mostrar mallas y regiones gráficas 2D/3D
│
├── utils/                   # Motores lógicos, procesamiento matemático y utilidades del sistema
│   ├── __init__.py          # Inicializador del paquete de utilidades
│   ├── helpers.py           # Gestor de rutas de recursos dinámicos, indispensable para empaquetados herméticos
│   ├── math_engine.py       # Núcleo del motor matemático (Análisis simbólico con SymPy e integración con SciPy)
│   ├── theme.py             # Lector y cargador del archivo de estilos unificados QSS (Temas Claro y Oscuro)
│   └── translations.py      # Diccionario centralizado de traducción bilingüe (Español / Inglés)
│
└── assets/                  # Recursos estáticos e inmutables del software
    ├── icono1.ico           # Icono oficial incrustado en las ventanas del sistema
    ├── logo_carga.png       # Logotipo de presentación renderizado en el Splash Screen al arrancar
    ├── style.qss            # Hoja de estilos Qt global (definiciones de bordes, degradados, fuentes y animaciones)
    └── mathjax/             # Distribución local de MathJax (archivos .js y fuentes .woff) para uso offline