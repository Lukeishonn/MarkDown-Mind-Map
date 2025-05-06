import matplotlib.pyplot as plt
import pandas as pd
df = pd.read_csv("users.csv")
conteo_genero = df.groupby("genero") ["nombre"].count()
colores=['pink', 'blue']
plt.figure(figsize=(6,6))
plt.pie(conteo_genero, colors=colores, labels=conteo_genero.index, autopct='%1.1f%%', startangle=90)
plt.title('Distribucion por genero')
plt.axis('equal')
plt.show()
