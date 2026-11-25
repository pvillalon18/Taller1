1. Descripción del problema
   Una planta de manufactura cuenta con 6 celdas robotizadas (C1–C6) y debe procesar 6 órdenes (O1-O6) en un turno, asignando exactamente una orden por celda de manera que se minimice el tiempo total de preparación y proceso (en minutos).

   Parte 1 : formulación como problema de flujo a costo mínimo con variables continuas, comprobación numérica de la conservación de flujo, demostración de integralidad automática por unimodularidad total (determinantes de submatrices), verificación independiente por tres vías (Algoritmo Húngaro, certificado de dualidad fuerte y enumeración exhaustiva) y lectura económica de los valores duales.

   Parte 2 : incorporación de la restricción adicional leída desde `datos/restriccion\_adicional.csv` (tope de tiempo conjunto para las celdas `C1` y `C2`), comparación entre la relajación lineal (donde aparecen variables fraccionarias) y el modelo entero binario, cálculo de la brecha de integralidad, demostración matricial de la pérdida de unimodularidad total y análisis de sensibilidad del tope de capacidad.


2. Estructura del repositorio

```text
Taller1/
├── README.md
├── requirements.txt
├── datos/
│   ├── tiempos.csv
│   └── restriccion_adicional.csv
├── resultados/
│   ├── solucion.csv
│   └── duales.csv
└── cuaderno.ipynb
```

3. Instalación y ejecución reproducible
Todos los parámetros del problema se leen dinámicamente desde la carpeta `datos/` (ningún dato numérico está incrustado en el código).\
python -m venv .venv \
source .venv/bin/activate        # En Windows: .venv\\Scripts\\activate \
pip install -r requirements.txt \

Ejecutar el cuaderno de resultados \
jupyter notebook cuaderno.ipynb \
El script resuelve la Parte 1 y la Parte 2 en Pyomo, ejecuta todas las verificaciones y genera `resultados/solucion.csv` y `resultados/duales.csv`. \

Ejecute todas las celdas en orden (Kernel → Restart & Run All).
