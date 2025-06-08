# Tabla Hash Abierta en Python (implementación personal)

Este proyecto es una implementación de una tabla hash abierta con encadenamiento separado, realizada paso a paso para entender mejor cómo funcionan internamente este tipo de estructuras de datos.

## ¿Qué hice?

Me propuse partir de una versión básica de una tabla hash y darle algunas mejoras que la hicieran más completa y más útil en un contexto real, pero sin perder la claridad ni la facilidad de uso.

### Estructura base
- Definí una clase `HashTable` que representa la tabla.
- Cada casilla de la tabla contiene una lista (lo que permite manejar colisiones con encadenamiento).
- La función hash que usé simplemente suma los valores ASCII de los caracteres de la clave y le aplica el módulo del tamaño de la tabla.

### Inserción con control de duplicados
- El método `insert()` no solo agrega el elemento si no está repetido, sino que también cuenta si se ha producido una colisión (es decir, si esa casilla ya tenía elementos).

### Búsqueda de elementos
- Implementé `search()` para comprobar si un elemento (por su clave) está dentro de la tabla.

### 🗑Eliminación de elementos
- Añadí un método `delete()` que permite eliminar un elemento dado su clave, algo que no estaba incluido en el ejercicio original.

### Estadísticas útiles
- Incluí un contador de colisiones (`self.collisions`) para tener control de cuántas veces ha habido choque entre claves.
- También desarrollé el método `distribution()` para saber cuántas casillas están vacías y cuántas tienen más de un elemento.
- Por comodidad, también hice que se pueda usar `len(tabla)` para obtener cuántos elementos hay en total (`__len__()`).

### Elementos personalizados
- Creé una clase `Persona` con nombre y edad, que cumple con los requisitos del ejercicio (`get_key()` y `__str__()`), y la usé como tipo de objeto que se guarda en la tabla.

### Pruebas en el programa principal
- En el bloque principal (`if __name__ == "__main__"`), agregué varias pruebas:
  - Inserción de varias personas.
  - Búsqueda de una persona específica.
  - Eliminación de otra persona.
  - Impresión del contenido completo de la tabla.
  - Estadísticas generales.

---

## ¿Por qué lo hice así?

Quise que la tabla fuera sencilla pero funcional. No usé librerías externas ni estructuras raras, solo listas y clases. La idea era entender bien lo que pasa por dentro de una tabla hash y cómo gestionamos las colisiones de forma limpia y ordenada.

---

## ¿Qué aprendí con este proyecto?

- Cómo implementar una función hash simple.
- Cómo manejar colisiones usando listas (encadenamiento separado).
- Qué tipo de detalles adicionales se pueden agregar para hacer que una estructura sea más útil: contar colisiones, permitir borrado, mostrar estadísticas, etc.
- Y sobre todo, cómo escribir código claro, comentado y fácil de mantener.

---

## ¿Qué me gustaría hacer a futuro?

- Cambiar la lista por una lista enlazada propia.
- Hacer una interfaz en consola donde el usuario pueda interactuar con la tabla.
- Explorar otras funciones hash y comparar resultados.
- Guardar y cargar los datos desde archivos para que persistan.

