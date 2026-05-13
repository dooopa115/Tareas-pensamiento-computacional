import tkinter as tk

from tkinter import ttk, messagebox



def evaluar\_salud():

&#x20;   # Datos proporcionados en 1000097901.jpg

&#x20;   dias = \["Lunes", "Martes", "Miércoles", "Jueves", "Viernes"]

&#x20;   niveles\_azucar = \[130, 160, 95, 175, 160]  # mg/dL

&#x20;   niveles\_sal = \[2000, 2400, 1800, 2400, 2700]  # mg

&#x20;   # Para presión usaremos duplas (Sistólica, Diastólica) basadas en los promedios del ejemplo

&#x20;   presion\_sistolica = \[115, 130, 110, 125, 145]

&#x20;   presion\_diastolica = \[75, 85, 70, 78, 92]



&#x20;   # Limpiar tabla anterior si existe

&#x20;   for i in tabla.get\_children():

&#x20;       tabla.delete(i)



&#x20;   alertas\_globales = \[]



&#x20;   for i in range(len(dias)):

&#x20;       # 1. Evaluación Azúcar (70-140 mg/dL)

&#x20;       estado\_azucar = "Normal"

&#x20;       if niveles\_azucar\[i] < 70 or niveles\_azucar\[i] > 140:

&#x20;           estado\_azucar = "ALERTA"

&#x20;       

&#x20;       # 2. Evaluación Sal (máximo 2300 mg)

&#x20;       estado\_sal = "Normal"

&#x20;       if niveles\_sal\[i] > 2300:

&#x20;           estado\_sal = "ALERTA"



&#x20;       # 3. Evaluación Presión Arterial (según tabla AHA en 1000097901.jpg)

&#x20;       sist = presion\_sistolica\[i]

&#x20;       diast = presion\_diastolica\[i]

&#x20;       

&#x20;       if sist >= 140 or diast >= 90:

&#x20;           cat\_presion = "Hipertensión Etapa 2"

&#x20;       elif 130 <= sist <= 139 or 80 <= diast <= 89:

&#x20;           cat\_presion = "Hipertensión Etapa 1"

&#x20;       elif 120 <= sist <= 129 and diast < 80:

&#x20;           cat\_presion = "Elevada"

&#x20;       else:

&#x20;           cat\_presion = "Normal"



&#x20;       # Insertar en la tabla

&#x20;       tabla.insert("", "end", values=(dias\[i], f"{niveles\_azucar\[i]} ({estado\_azucar})", 

&#x20;                                       f"{niveles\_sal\[i]} ({estado\_sal})", 

&#x20;                                       f"{sist}/{diast} ({cat\_presion})"))



&#x20;   # Cálculos de promedios para el resumen

&#x20;   prom\_azucar = sum(niveles\_azucar) / len(niveles\_azucar)

&#x20;   prom\_sal = sum(niveles\_sal) / len(niveles\_sal)

&#x20;   

&#x20;   resumen = f"PROMEDIOS SEMANALES:\\nAzúcar: {prom\_azucar:.2f} mg/dL\\nSal: {prom\_sal:.2f} mg"

&#x20;   label\_resumen.config(text=resumen)



\# Configuración de la Ventana Principal

root = tk.Tk()

root.title("Evaluación de Salud - Pensamiento Computacional")

root.geometry("800x500")



\# Encabezado (Referencia a la Facultad de Ingeniería)

header = tk.Label(root, text="UNIVERSIDAD RAFAEL LANDÍVAR\\nFacultad de Ingeniería", 

&#x20;                font=("Arial", 12, "bold"), pady=10)

header.pack()



\# Tabla de resultados

columns = ("Dia", "Azúcar", "Sal", "Presión Arterial")

tabla = ttk.Treeview(root, columns=columns, show="headings")



for col in columns:

&#x20;   tabla.heading(col, text=col)

&#x20;   tabla.column(col, width=150)



tabla.pack(pady=20, padx=10, fill="x")



\# Área de Resumen y Alertas

label\_resumen = tk.Label(root, text="Presione el botón para evaluar los datos", 

&#x20;                       font=("Arial", 10), justify="left")

label\_resumen.pack(pady=10)



\# Botón de Acción

btn\_evaluar = tk.Button(root, text="Evaluar Semana", command=evaluar\_salud, 

&#x20;                      bg="#0056b3", fg="white", font=("Arial", 10, "bold"), padx=20)

btn\_evaluar.pack(pady=10)



root.mainloop()

