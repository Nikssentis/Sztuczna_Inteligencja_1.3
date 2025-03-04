import numpy as np
import pandas as pd

# Wczytanie pliku car.txt (dane o samochodach)
data = pd.read_csv('car.txt', sep=' ', header=None)

# Wczytanie pliku car-type.txt (typy atrybutów)
types = {}
with open('car-type.txt', 'r') as f:
    for line in f:
        attribute, attr_type = line.strip().split()
        types[attribute] = attr_type


# 3a) Wypisanie unikalnych klas decyzyjnych (zakładając, że ostatnia kolumna to klasy decyzyjne)
decision_classes = data.iloc[:, -1].unique()
print("Symbole klas decyzyjnych:", decision_classes)
print("---------------------------------------------------------------------------------")

# 3b) Liczba obiektów w każdej klasie decyzyjnej
class_counts = data.iloc[:, -1].value_counts()
print("Wielkości klas decyzyjnych:\n", class_counts)
print("---------------------------------------------------------------------------------")

# 3c) nie robimy (nie ma numerycznych)

# 3d) Liczba różnych wartości dla każdego atrybutu
unique_values_count = data.nunique()

print("Liczba różnych dostępnych wartości dla każdego atrybutu:\n", unique_values_count)
print("---------------------------------------------------------------------------------")

# 3e) Lista wszystkich różnych dostępnych wartości dla każdego atrybutu
unique_values = data.apply(lambda x: x.unique())

print("Lista różnych dostępnych wartości dla każdego atrybutu:\n", unique_values)
print("---------------------------------------------------------------------------------")
