# =====================================================
# PROBLEMA 2 - PROMOCIÓN EN MENÚ DE RESTAURANTE
# PRECIOS EN PESOS COLOMBIANOS (COP)
# =====================================================

# Matriz del menú:
# [Nombre del Producto, Categoría, Precio Base]

menu = [
    ["Hamburguesa Clásica", "Comida Rápida", 25000],
    ["Pizza Margarita", "Italiana", 42000],
    ["Ensalada César", "Saludable", 18000],
    ["Sushi Roll", "Japonesa", 55000],
    ["Pasta Alfredo", "Italiana", 38000],
    ["Tacos Mexicanos", "Mexicana", 27000]
]

# Configuración de la promoción
CATEGORIA_OBJETIVO = "Italiana"
UMBRAL_PRECIO = 30000   # Solo aplica si supera este valor
DESCUENTO = 0.15        # 15%


# -----------------------------------------------------
# FUNCIÓN PARA CALCULAR EL PRECIO FINAL
# -----------------------------------------------------
def calcular_precio_final(categoria, precio_base):
    """
    Aplica un descuento del 15% si:
    - El producto pertenece a la categoría objetivo
    - El precio base supera el umbral establecido
    """

    if categoria == CATEGORIA_OBJETIVO and precio_base > UMBRAL_PRECIO:
        precio_final = precio_base - (precio_base * DESCUENTO)
    else:
        precio_final = precio_base

    return round(precio_final)


# -----------------------------------------------------
# MOSTRAR RESULTADOS
# -----------------------------------------------------
print("=" * 60)
print("     MENÚ DEL RESTAURANTE CON PROMOCIONES")
print("=" * 60)

for producto in menu:

    nombre = producto[0]
    categoria = producto[1]
    precio_base = producto[2]

    # Calcular precio final
    precio_final = calcular_precio_final(categoria, precio_base)

    # Mostrar información
    print(f"\nProducto      : {nombre}")
    print(f"Categoría     : {categoria}")
    print(f"Precio Base   : ${precio_base:,.0f} COP")
    print(f"Precio Final  : ${precio_final:,.0f} COP")

    # Verificar si tuvo descuento
    if precio_base != precio_final:
        print("Promoción aplicada: Sí (15% de descuento)")
    else:
        print("Promoción aplicada: No")

print("\n" + "=" * 60)
print("                FIN DEL PROGRAMA")
print("=" * 60)
