#    * Gestion de inventarios Kotlin - Paradigmas de Programacion (2025-1) *

- **Nombres:** Julian Caro, Angel Robles
- **Asignatura:** Paradigmas de Programacion
- **Periodo:** 2025-1

# * Informe Técnico * 
# * Controlador *
package controller

import model.Product

/**
 * Controlador principal para la gestión del inventario de productos.
 * Maneja toda la lógica de negocio relacionada con las operaciones CRUD:
 * - Creación (Create)
 * - Lectura (Read)
 * - Actualización (Update)
 * - Eliminación (Delete)
 * 
 * También incluye operaciones especiales como cálculo de precios con IVA.
 * 
 * @property products Lista mutable que almacena todos los productos del inventario
 */
class InventoryController {
    private val products = mutableListOf<Product>()

    /**
     * Agrega un nuevo producto al inventario.
     * @param product El producto a agregar (de tipo Product)
     * @sample 
     * val controller = InventoryController()
     * controller.addProduct(Product(1, "Laptop", 10, 999.99))
     */
    fun addProduct(product: Product) {
        products.add(product)
        println("Producto agregado: $product")
    }

    /**
     * Obtiene todos los productos del inventario.
     * @return Lista inmutable de productos
     * @sample 
     * val allProducts = controller.getProducts()
     * allProducts.forEach { println(it) }
     */
    fun getProducts(): List<Product> = products

    /**
     * Verifica la existencia de un producto por su ID.
     * @param id El ID del producto a buscar
     * @return true si el producto existe, false en caso contrario
     * @sample 
     * if (controller.productExists(1)) {
     *     println("Producto encontrado")
     * }
     */
    fun productExists(id: Int): Boolean {
        return products.any { it.id == id }
    }

    /**
     * Actualiza los datos de un producto existente.
     * @param id ID del producto a actualizar
     * @param name Nuevo nombre del producto
     * @param quantity Nueva cantidad en stock
     * @param price Nuevo precio unitario
     * @sample 
     * controller.updateProduct(1, "Laptop Premium", 5, 1299.99)
     */
    fun updateProduct(id: Int, name: String, quantity: Int, price: Double) {
        val product = products.find { it.id == id }
        if (product != null) {
            product.name = name
            product.quantity = quantity
            product.price = price
            println("Producto actualizado: $product")
        } else {
            println("Producto no encontrado.")
        }
    }

    /**
     * Elimina un producto del inventario.
     * @param id ID del producto a eliminar
     * @sample 
     * controller.deleteProduct(1)
     */
    fun deleteProduct(id: Int) {
        if (products.removeIf { it.id == id }) {
            println("Producto eliminado.")
        } else {
            println("Producto no encontrado.")
        }
    }

    /**
     * Calcula el precio total con IVA (19%) para un producto específico.
     * @param id ID del producto a calcular
     * @sample 
     * controller.calculateTotalWithIVA(1)
     */
    fun calculateTotalWithIVA(id: Int) {
        val product = products.find { it.id == id }
        if (product != null) {
            val total = product.quantity * product.price
            val iva = total * 0.19
            println("Total con IVA: ${total + iva}")
        } else {
            println("Producto no encontrado.")
        }
    }
}
