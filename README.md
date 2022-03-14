#!/usr/bin/env python3
# coding:utf-8

"""
\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\
TP rouille
  Ce script permet de déterminer la composition finale d'un système chimique
  particulier siège de la transformation totale suivante: a.A + b.B + c.C -> d.D
\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\
"""

# -------------------------------------------------------------------------------

print("L'équation est de type: a.A + b.B + c.C -> d.D")

# Saisie des coefficients stoechiométriques
a = int(input("Entrer le coefficient stoechiométrique a: "))
b = int(input("Entrer le coefficient stoechiométrique b: "))
c = int(input("Entrer le coefficient stoechiométrique c: "))
d = int(input("Entrer le coefficient stoechiométrique d: "))

# Saisie des quantités de matières initiales
nAi = float(input("Entrer la quantité de matière initiale de A: "))
nBi = float(input("Entrer la quantité de matière initiale de B: "))
nCi = float(input("Entrer la quantité de matière initiale de C: "))
nDi = float(input("Entrer la quantité de matière initiale de D: "))

# -------------------------------------------------------------------------------

# Calcul de l'avancement maximal
xA = nAi/a
xB = nBi/b
xC = nCi/c
xD = nDi/d

xmax = min([xA,xB,xC])
print("La valeur de l'avancement maximal est ",xmax," mL.")

# Recherche du réactif limitant
if xA==xmax:
    print("A est le réactif limitant.")
if xB==xmax:
    print("B est le réactif limitant.")
if xC==xmax:
    print("C est le réactif limitant.")

if (xA==xmax) & (xB==xmax) & (xC==xmax):
    print("Les réactifs ont été introduits dans les proportions stoechiométriques.")

# -------------------------------------------------------------------------------

# Calcul des quantités de matière finales
nAf = nAi - a*xmax
nBf = nBi - b*xmax
nCf = nCi - c*xmax
nDf = nDi + d*xmax

# Affichage des résultats
print("La composition finale du système est:")
print("nf(A) = ",nAf," mL ; nf(B) = ",nBf," mL ; nf(C) = ",nCf," mL ; nf(D) = ",nDf," mL")
