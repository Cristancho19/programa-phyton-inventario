# =====================================================================
# Curso: Fundamentos de Programación (213022)
# Fase 5 - Evaluacion Final POA
# Estudiante: Cristian Eduardo Mora Vanegas
# Problema Seleccionado: Problema 3 - Auditoría de Inventario
# =====================================================================

def calcular_cantidad_a_pedir(stock_actual, stock_minimo):
    """
    Modulo (funcion) para determinar la cantidad exacta a pedir para un artículo.
    Logica de negocio:
    - Si Stock Actual < Stock Minimo: cantidad = Minimo - Actual
    - Si Stock Actual >= Stock Minimo: cantidad = 0
    """
    if stock_actual < stock_minimo:
        return stock_minimo - stock_actual
    else:
        return 0

def ejecutar_auditoria():
    # Matriz inicializada con 5 artículos (Código, Nombre, Stock Actual, Stock Mínimo Requerido)
    inventario = [
        ["ART01", "Filtro de Aceite", 12, 15],
        ["ART02", "Inyector Diesel", 4, 3],
        ["ART03", "Bomba de Combustible", 2, 5],
        ["ART04", "Sensor de Voltaje AVR", 8, 8],
        ["ART05", "Filtro de Aire Industrial", 5, 10]
    ]
    
    print("=" * 60)
    print("   INFORME DE AUDITORIA DE INVENTARIO Y REABASTECIMIENTO")
    print("=" * 60)
    print(f"{'Articulo':<30} | {'Cantidad a Solicitar':<20}")
    print("-" * 60)
    
    # Recorrido de la matriz para evaluar cada articulo
    for articulo in inventario:
        nombre = articulo[1]
        stock_actual = articulo[2]
        stock_minimo = articulo[3]
        
        # Llamado al modulo de calculo
        cantidad_pedir = calcular_cantidad_a_pedir(stock_actual, stock_minimo)
        
        # Impresion de la salida formateada
        print(f"{nombre:<30} | {cantidad_pedir:<20}")
        
    print("=" * 60)

if __name__ == "__main__":
    ejecutar_auditoria()
