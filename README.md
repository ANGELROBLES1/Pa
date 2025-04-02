#    * Gestion de inventarios Kotlin - Paradigmas de Programacion (2025-1) *

- **Nombres:** Julian Caro, Angel Robles
- **Asignatura:** Paradigmas de Programacion
- **Periodo:** 2025-1

# * Informe Técnico * 
# * Controlador *
InventoryController - Sistema de Gestión de Inventario
Este módulo gestiona el inventario de productos mediante una lista mutable. Permite agregar, actualizar, eliminar y consultar productos, además de calcular el total con IVA.

📌 Funcionalidades
Agregar productos: Permite añadir un nuevo producto al inventario.

Obtener productos: Lista todos los productos almacenados.

Verificar existencia: Comprueba si un producto existe en el inventario mediante su ID.

Actualizar productos: Modifica el nombre, cantidad y precio de un producto existente.

Eliminar productos: Elimina un producto del inventario usando su ID.

Calcular total con IVA: Calcula el precio total de un producto incluyendo el 19% de IVA.

🛠️ Métodos y Uso
addProduct(product: Product)
Agrega un nuevo producto a la lista de inventario.

Parámetros:

product: Producto a agregar.

getProducts(): List<Product>
Devuelve una lista con todos los productos registrados.

productExists(id: Int): Boolean
Verifica si un producto con un ID específico existe en el inventario.

Parámetros:

id: Identificador del producto.

Retorna: true si el producto existe, false si no.

updateProduct(id: Int, name: String, quantity: Int, price: Double)
Actualiza los atributos de un producto si este existe.

Parámetros:

id: Identificador del producto.

name: Nuevo nombre del producto.

quantity: Nueva cantidad disponible.

price: Nuevo precio unitario.

deleteProduct(id: Int)
Elimina un producto del inventario por su ID.

Parámetros:

id: Identificador del producto.

calculateTotalWithIVA(id: Int)
Calcula el total de un producto con IVA del 19%.

Parámetros:

id: Identificador del producto.

Salida: Imprime en consola el total con IVA.
