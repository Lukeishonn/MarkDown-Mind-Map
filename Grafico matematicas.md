import pandas as pd
import matplotlib.pyplot as plt
import numpy as np

df = pd.read_csv("StudentsPerformance.csv")

conteos, bins = np.histogram(df["math score"], bins=10)
bin_centers = 0.5 * (bins[1:] + bins[:-1])
anchos = np.diff(bins)
colores = plt.cm.viridis(np.linspace(0, 1, len(conteos)))

plt.figure(figsize=(8, 5))
plt.bar(bin_centers, conteos, width=anchos, color=colores, edgecolor='black')
plt.title("Distribucion de puntajes de Matemáticas")
plt.xlabel("Puntaje")
plt.ylabel("Cantidad de Estudiantes")
plt.grid(axis='y', linestyle='--', alpha=0.7)
plt.tight_layout()
plt.show()
