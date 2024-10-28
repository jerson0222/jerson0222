import numpy as np
import matplotlib.pyplot as plt

# Datos de factores de seguridad para cada punto (sustituye con tus valores específicos)
points = ["Punto 1", "Punto 2", "Punto 3", "Punto 4", "Punto 5", "Punto 6", "Punto 7", "Punto 8"]
rankine_fs = [1.64, 0.43, 1.24, 0.48, 1.54, 0.62, 0.76, 2.11]  # Valores de Rankine
tresca_fs = [67.28, 0.45, 1.24, 0.49, 1.00, 0.65, 0.76, 1.44]  # Valores de Tresca
von_mises_fs = [1.66, 0.44, 1.24, 0.49, 1.14, 0.64, 0.76, 1.63]  # Valores de von Mises

# Crear gráfico de barras
x = np.arange(len(points))  # Posiciones de los puntos en el eje X
width = 0.25  # Ancho de las barras

fig, ax = plt.subplots(figsize=(10, 6))
bar1 = ax.bar(x - width, rankine_fs, width, label='Rankine')
bar2 = ax.bar(x, tresca_fs, width, label='Tresca')
bar3 = ax.bar(x + width, von_mises_fs, width, label='von Mises')

# Etiquetas y título
ax.set_xlabel('Punto')
ax.set_ylabel('Factor de Seguridad')
ax.set_title('Factores de Seguridad por Punto y Teoría de Falla')
ax.set_xticks(x)
ax.set_xticklabels(points)
ax.axhline(1, color='red', linestyle='--', label='Límite de Seguridad (FS=1)')  # Línea de referencia para FS=1
ax.legend()

# Mostrar gráfico
plt.show()
