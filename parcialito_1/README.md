# Parcialito nro 1 Técnicas de Documentación y Validación
### Verificación Estática
Es el proceso de examinar el código y los documentos del proyectos sin ejecutarlo. Alguna herramientas utilizadas para la verificación estática son:
- **Revisiones de Código**: Evaluaciones manuales del código por parte de otros desarrolladroes para identificar errores y mejoras potenciales.
- **Análisis Estático**: utilización de herramientas automatizadas que analizan el código para detectar errores stintácticos, violaciones de estándares de codificación y problemas de seguridad.

### Verificación Dinámica
Es la evaluación del producto en funcionamiento. Se realiza mediante pruebas de ejecución que valida el comportamiento y las funcionalidades del sistema en un entorno real o simulado. Las técnicas de verificación dinámica incluyen:
- **Pruebas Unitarias**: Evaluaciones de componentes individuales del software para asegurar que cada uno funciona correctamente por sí mismo.
- **Pruebas de Integración**: Pruebas que verifican la interacción entre diferentes componentes del software para asegurar que funcionan correctamente juntos.
- **Pruebas de Sistema**: Evaluaciones del sistema completo para verificar que todas las partes operan de manera coherente y cumplen con los requisitos especificados.

## Validación y Documentación de Requerimientos
### Especificación de requisitos
- Contiene
    - Información del problema
    - Interfaz externa del sistema con su entorno
    - Propiedades y comportamiento del sistema
    - Restricciones de diseño y fabricación del producto
    - Contribución del sistema
    - Restricciones acerca de las propiedades emergentes

### DRU vs. ERS
Documentación de requerimientos de usuario vs Especificación de requerimientos de software

#### DRU
- Punto de vista del usuario / cliente / interesado.
- Sin demasiado nivel de detalle.
- Se incluye la descipción del problema actual y las metas que se espera lograr con la construcción del nuevo sistema.

#### ERS
- Punto de vista del desarrollador.
- Requisitos del software más detallados.
- Descripción de características del sistema y contribución al logro de los objetivos.

### Requerimientos
Expectativas del cliente que el software debe cumplir, utilizando una serie de herramientas por parte del desarrollador para alcanzar metas.

#### Características deseables
- **Necesario**: Su omisión provoca deficiencia en el sistema.
- **Conciso**: Fácil de leer y entender.
- **Completo**: Se proporciona info suficiente para su comprensión.
- **Consistente**: No se contradice con otro requerimiento.
- **No ambiguo**: Tiene una única interpretación.
- **Verificable**: Se puede corroborar.

#### Clasificación
- **Requerimientos funcionales**:
    - Servicios que proveerá el sistema ante entradas esperadas y no esperada.
    - Servicios que NO debe proveer.
- **Requerimientos no funcionales**:
    - Hacen referencia a las propiedades emergentes de éste tales como la fiabilidad, el tiempo de respuesta, la capacidad de almacenamiento, etc.

#### Matriz de trazabilidad
- Vincula los requisitos del proyecto desde su origen hasta los entregables que los satisfacen.
- Ayuda a asegurar que cada requisito agrega valor al negocio.
- Permite realizar un seguimiento durante el ciclo de vida.

#### Cambios en los requerimientos
- Documento ordenado
- Minimizar referencias externas
- Los rquerimientos y el sistema evolucionan
- Utilizar control de cambios

#### Validación de requerimientos
- Demostrar que los requerimientos definidos representan las necesidades del cliente.
- Los costos de errores en los requerimientos son muy altos, validarlos es muy importante.

##### Prototipado
- **De interfaz de usuario**: Técnica de representación aproximada de la interfaz de usuario de un sistema software que permite a cliente y usuarios entender fácilmente la propuesta. Son **Desechables** y **Evolutivos**.
    - **Mock-ups**: Pantallas dibujadas en papel.
    - **Storyboards**: Evolución de los mock-ups. Secuencia de acciones o escenarios.
    - **Maquetas**: Versión simplificada del sistema software deseado, pantallas e interconexión entre ellas.

##### Generación de casos de prueba
- Los requerimientos deben ser verificables.
- Deben conocerse los datos de entrada así como las tareas a realizar y los resultados esperados.

##### Inspección o recorrido
- Detectar conflictos
- Aumentar el conocimiento
- Permite validar el paso a paso de manera natural

#### Ágiles - User Stories
- Negocian los requerimientos.
- Una oración o más.
- Como <rol_de_usuario> quiero <función_del_sistema> para poder <valor_de_negocio>.
- Independiente, negociable, valiosa, estimable, pequeña, verificable.
- Ejemplo:
    - Como **gerente** quiero poder **seleccionar un proveedor** para **atender un pedido**.
        - **Criterio de aceptación**: Cuando ingrese debo poder ver una grilla con los diferentes pedidos para autorizar, al seleccionar uno debo ver las 3 opciones recomendadas por el sector de compras (al hacer clic sobre alguna de ellas se me debe mostrar el detalle del presupuesto) con una casilla de selección por cada una, el sistema solo debe permitirme seleccionar una opción. Al tener una opción seleccionada se debe habilitar el botón de autorizar pedido.

#### Product backlog
- Contiene una lista de User Stories consensuadas con el cliente.
- Se definen iteraciones y entregas.
- No es necesario que la lista sea completa.
- Se debe considerar que los requerimientos son dinámicos.

## Validación y Documentación de implementación - Manejo de código
### Documentación de código
Sirve para dejar registros de
- Decisiones de implementación.
- Estructuras de artefactos.
- Cambios.

#### Ventajas
- Se documenta utilizando lenguaje natural.
- Especificación local al código.
- Permite comprender razonamientos y decisiones del programador.

#### Desventajas
- Debe ser realizada por el programador (preferentemente)

#### Buenas prácticas
- Primera oración
    - Resumen / descirpción concreta pero precisa del ítem.
    - Aplica a miembro, calse, interface o paquete.
- Dependencia de la implementación
    - No debe indicar detalles de la implementación
    - Definir que es requerido y que variar cuando se cambia de plataforma o implementación.
    - Proveer suficiente información para satisfacer al programador siguiente.
    - Información para poder crear casos de tests sin leer el código fuente.
- Utilizar frases en vez de oraciones completes
- Utilizar tercera persona (declarativa) y no segunda persona (imperativa)
- Un método implementa una operación, entonces, empezar frases con verbos
- Las descripciones de Clases/interfaces/propiedades pueden omitir el sujeto y describir su estado
- Cuando se refiere a instancias de objetos creadas por la clase utilizar “este” en vez de “el”

### JavaDoc
#### Orden de los tags
- @author (Clases e interface únicamente, requerido) - indica autor de la documentación
- @version (Clases e interfaces únicamente, requerido) - versión de la documentación
- @param (Métodos y constructores únicamente) - indica parametros
- @return (Métodos únicamente) - indica dato devuelto por el método
- @exception (@throws es un sinónimo agregado en Javadoc 1.2) - indica las excepciones que un método puede lanzar
- @see - referencia a otra clase o documento
- @since - indica la versión en la que una clase, método, campo o cualquier otro elemento fue introducido o modificado por primera vez
- @serial (o @serialField o @serialData)
- @deprecated - indica que una clase, método, campo, etc esta obsoleto o en desuso.

### Doxygen
Basado en bloque de comentarios
- Brief
- Detailed
- In body (para métodos y funciones)

```java
/**
 * ... Comentario tipo JavaDoc
...
 */
/*!
 * ... Comentario tipo Qt ...
 */
///
/// ... Comentario de al menos dos líneas ...
///
//!
//! ... Comentario de al menos dos líneas ...
//!
```

- **@class**: Describe la clase y su propósito general.
- **@brief**: Proporciona una descripción breve del método o de la clase.
- **@param**: Documenta los parámetros del método, indicando el nombre y la descripción de cada uno.
- **@return**: Describe el valor que devuelve el método.
- **@throws**: Indica las excepciones que el método puede lanzar, si aplica.

```java
/**
 * @class Calculadora
 * @brief Esta clase proporciona métodos básicos para realizar operaciones matemáticas.
 *
 * La clase Calculadora incluye métodos para sumar, restar, multiplicar y dividir dos números.
 * Los métodos aceptan números enteros y devuelven los resultados como enteros.
 */
public class Calculadora {

    /**
     * @brief Suma dos números enteros.
     * @param a El primer número entero.
     * @param b El segundo número entero.
     * @return La suma de a y b.
     *
     * Este método toma dos enteros como parámetros y devuelve su suma.
     */
    public int sumar(int a, int b) {
        return a + b;
    }

    /**
     * @brief Resta dos números enteros.
     * @param a El número entero del que se resta.
     * @param b El número entero que se resta.
     * @return La resta de a menos b.
     *
     * Este método toma dos enteros como parámetros y devuelve la diferencia.
     */
    public int restar(int a, int b) {
        return a - b;
    }

    /**
     * @brief Multiplica dos números enteros.
     * @param a El primer número entero.
     * @param b El segundo número entero.
     * @return El producto de a y b.
     *
     * Este método toma dos enteros como parámetros y devuelve su producto.
     */
    public int multiplicar(int a, int b) {
        return a * b;
    }

    /**
     * @brief Divide dos números enteros.
     * @param a El numerador.
     * @param b El denominador.
     * @return El cociente de a dividido por b.
     * @throws ArithmeticException Si b es cero.
     *
     * Este método toma dos enteros como parámetros y devuelve el cociente de la división.
     * Lanza una excepción si el denominador es cero.
     */
    public int dividir(int a, int b) {
        if (b == 0) {
            throw new ArithmeticException("No se puede dividir por cero.");
        }
        return a / b;
    }
}
```

### Markdown
- Nació como herramienta de conversión de texto plano a HTML.
- Método de escritura.

Sirve para
- Cualquier tipo de publicación en internet donde este presente HTML.
- Para tomar notas y apuntes.
- Escribir un libro.
- En servicios como trello o foros como stackoverflow.

#### Elementos
##### Elementos de bloque
- Párrafos y saltos de línea
- Encabezados
- Citas
- Listas
- Códigos de bloque
- Reglas horizontales

##### Elementos de línea
- Énfasis
- Links o enlaces
- Código
- Imágenes

##### Elementos varios
- Links automáticos
- Omitir Markdown

### Validación de código
#### Acersiones
- Es una condición lógica insertada en el código fuente que se asume cierta (según especificación). El sistema se encarga de comprobarlas y disparar excepciones en caso de no cumplirse
- útil para implementación y testeo.
- útil para debuging de un código en producción que está causando problemas.