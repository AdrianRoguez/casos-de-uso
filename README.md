# Sistema de Biblioteca

## Actores

### Actor 1: Usuario

| **Actor** | Usuario (Lector) |
|-----------|------------------|
| **Descripción**  | El usuario que accede al sistema para buscar libros, pedir prestado un libro y devolverlo cuando haya terminado de usarlo. |
| **Características**  | El usuario debe estar registrado en el sistema. Puede acceder al catálogo de libros disponibles para su consulta. |
| **Relaciones**  | Interactúa con los casos de uso: Buscar libro, Pedir prestado un libro, Devolver libro. |
| **Referencias** | Buscar libro, Pedir prestado un libro, Devolver libro |
| **Notas** |  |
| **Autor**  | Adrián |
| **Fecha** | 05/11/2024 |

|  Atributo |||
|---|---|---|
| _Nombre_  | _Descripción_  | _Tipo_ |
| _ID Usuario_  | Identificador único del usuario  | String |
| _Nombre_ | Nombre completo del usuario | String |
| _Email_ | Correo electrónico del usuario | String |
| _Fecha de registro_ | Fecha en que el usuario se registró en el sistema | Fecha |

### Actor 2: Bibliotecario

| **Actor** | Bibliotecario |
|-----------|------------------|
| **Descripción**  | El bibliotecario es el encargado de gestionar el inventario de libros, registrar los préstamos y devoluciones. |
| **Características**  | Debe contar con acceso administrativo para realizar operaciones sobre los libros, préstamos y devoluciones. |
| **Relaciones**  | Interactúa con los casos de uso: Gestionar inventario de libros, Registrar préstamos. |
| **Referencias** | Gestionar inventario de libros, Registrar préstamos |
| **Notas** | El bibliotecario debe asegurar que el inventario esté actualizado. |
| **Autor**  | Adrián |
| **Fecha** | 05/11/2024 |

|  Atributo |||
|---|---|---|
| _Nombre_  | _Descripción_  | _Tipo_ |
| _ID Bibliotecario_  | Identificador único del bibliotecario | String |
| _Nombre_ | Nombre completo del bibliotecario | String |
| _Cargo_ | Cargo del bibliotecario (ej: Jefe de Biblioteca) | String |

## Casos de uso

### Caso de Uso 1: Buscar libro

|  Caso de Uso  CU.1 | Buscar Libro |
|---|---|
| **Fuentes**  | Este caso de uso se sustenta gracias al [documento de especificación](#) |
| **Actor**  | Usuario, Bibliotecario |
| **Descripción** | El usuario o bibliotecario puede buscar libros dentro del sistema a partir de criterios como el título, autor o categoría. |
| **Flujo básico** | 1. El usuario ingresa un criterio de búsqueda (por ejemplo, título).<br>2. El sistema muestra los resultados coincidentes.<br>3. El usuario selecciona el libro deseado para más detalles. |
| **Pre-condiciones** | El usuario debe estar registrado en el sistema y tener acceso al catálogo de libros. |
| **Post-condiciones** | El sistema muestra los resultados de búsqueda y permite al usuario seleccionar un libro. |
| **Requerimientos** | Acceso a Internet, base de datos actualizada de libros. |
| **Notas** | Este caso de uso es fundamental para el funcionamiento del sistema, ya que permite a los usuarios localizar los libros disponibles. |
| **Autor**  | AdriánRoguez |
| **Fecha** | 05/11/2024 |

### Caso de Uso 2: Pedir prestado un libro

|  Caso de Uso  CU.2 | Pedir Prestado un Libro |
|---|---|
| **Fuentes**  | Este caso de uso se sustenta gracias al [documento de especificación](#) |
| **Actor**  | Usuario |
| **Descripción** | El usuario puede solicitar un libro prestado, siempre y cuando el libro esté disponible y el usuario tenga una cuenta activa en el sistema. |
| **Flujo básico** | 1. El usuario selecciona el libro que desea pedir prestado.<br>2. El sistema verifica la disponibilidad del libro.<br>3. Si el libro está disponible, el sistema registra el préstamo.<br>4. El sistema informa al usuario que el libro ha sido prestado correctamente. |
| **Pre-condiciones** | El libro debe estar disponible en el inventario. El usuario debe estar registrado y no tener préstamos pendientes. |
| **Post-condiciones** | El préstamo se registra en el sistema y el libro queda marcado como "prestado". |
| **Requerimientos** | El libro debe estar disponible, el usuario debe tener un límite de préstamos no excedido. |
| **Notas** | Este caso de uso puede incluir la opción de reservar un libro si no está disponible. |
| **Autor**  | AdriánRoguez |
| **Fecha** | 05/11/2024 |

### Caso de Uso 3: Devolver libro

|  Caso de Uso  CU.3 | Devolver Libro |
|---|---|
| **Fuentes**  | Este caso de uso se sustenta gracias al [documento de especificación](#) |
| **Actor**  | Usuario |
| **Descripción** | El usuario puede devolver un libro que ha sido prestado, liberando así el recurso para otros usuarios. |
| **Flujo básico** | 1. El usuario selecciona el libro a devolver.<br>2. El sistema verifica si el libro está registrado como prestado.<br>3. El sistema actualiza el inventario y marca el libro como disponible.<br>4. El sistema confirma la devolución al usuario. |
| **Pre-condiciones** | El libro debe estar en el sistema como "prestado". El usuario debe haber recibido previamente el libro. |
| **Post-condiciones** | El libro es devuelto al inventario y el estado de préstamo es actualizado. |
| **Requerimientos** | El libro debe estar físicamente disponible para su devolución. |
| **Notas** | Se podría incluir un cálculo de multa por retraso en la devolución. |
| **Autor**  | AdriánRoguez |
| **Fecha** | 05/11/2024 |

### Caso de Uso 4: Gestionar inventario de libros

|  Caso de Uso  CU.4 | Gestionar Inventario de Libros |
|---|---|
| **Fuentes**  | Este caso de uso se sustenta gracias al [documento de especificación](#) |
| **Actor**  | Bibliotecario |
| **Descripción** | El bibliotecario tiene la capacidad de agregar, eliminar o actualizar la información sobre los libros en el inventario del sistema. |
| **Flujo básico** | 1. El bibliotecario ingresa al sistema con privilegios administrativos.<br>2. El bibliotecario selecciona la opción para gestionar inventario.<br>3. El bibliotecario agrega, elimina o modifica la información de los libros.<br>4. El sistema confirma la actualización del inventario. |
| **Pre-condiciones** | El bibliotecario debe estar autenticado y tener permisos administrativos. |
| **Post-condiciones** | El inventario se actualiza con los cambios realizados. |
| **Requerimientos** | El sistema debe permitir a los bibliotecarios gestionar el inventario de manera eficiente. |
| **Notas** | Es importante que las actualizaciones sean registradas para mantener un historial de cambios. |
| **Autor**  | AdriánRoguez |
| **Fecha** | 05/11/2024 |

### Caso de Uso 5: Registrar préstamos

|  Caso de Uso  CU.5 | Registrar Préstamos |
|---|---|
| **Fuentes**  | Este caso de uso se sustenta gracias al [documento de especificación](#) |
| **Actor**  | Bibliotecario |
| **Descripción** | El bibliotecario registra los préstamos de libros a los usuarios, marcando la fecha de préstamo y la fecha de devolución esperada. |
| **Flujo básico** | 1. El bibliotecario selecciona el libro que se va a prestar.<br>2. El bibliotecario selecciona al usuario que pide el libro.<br>3. El bibliotecario registra la fecha de préstamo y establece la fecha de devolución.<br>4. El sistema confirma el préstamo y actualiza el inventario. |
| **Pre-condiciones** | El bibliotecario debe tener acceso al sistema y el libro debe estar disponible para su préstamo. |
| **Post-condiciones** | El préstamo queda registrado y el libro se marca como prestado en el inventario. |
| **Requerimientos** | El bibliotecario debe tener acceso completo al sistema de gestión de préstamos. |
| **Notas** | Este caso de uso es crucial para el control de los libros prestados y la gestión del inventario. |
| **Autor**  | AdriánRoguez |
| **Fecha** | 05/11/2024 |


# Sistema de Compras en Línea

## Actores

### Actor 1: Cliente

| **Actor** | Cliente |
|-----------|---------|
| **Descripción**  | El cliente navega por el catálogo de productos, agrega productos al carrito, realiza el pedido y efectúa el pago. |
| **Características**  | El cliente puede ser un usuario registrado o anónimo. Puede navegar por los productos, agregar productos al carrito y proceder al pago. |
| **Relaciones**  | Interactúa con los casos de uso: Buscar productos, Añadir productos al carrito, Realizar pedido, Realizar pago. |
| **Referencias** | Buscar productos, Añadir productos al carrito, Realizar pedido, Realizar pago |
| **Notas** |  |
| **Autor**  | Adrián |
| **Fecha** | 05/11/2024 |

|  Atributo |||
|---|---|---|
| _Nombre_  | _Descripción_  | _Tipo_ |
| _ID Cliente_  | Identificador único del cliente | String |
| _Nombre_ | Nombre completo del cliente | String |
| _Email_ | Correo electrónico del cliente | String |
| _Fecha de registro_ | Fecha en que el cliente se registró en el sistema | Fecha |

### Actor 2: Administrador

| **Actor** | Administrador |
|-----------|---------------|
| **Descripción**  | El administrador es responsable de gestionar el catálogo de productos y sus precios. |
| **Características**  | Tiene acceso administrativo para agregar, eliminar o modificar productos en el catálogo y actualizar precios. |
| **Relaciones**  | Interactúa con el caso de uso: Gestionar catálogo de productos. |
| **Referencias** | Gestionar catálogo de productos |
| **Notas** | El administrador asegura que el catálogo esté actualizado y bien organizado. |
| **Autor**  | Adrián |
| **Fecha** | 05/11/2024 |

|  Atributo |||
|---|---|---|
| _Nombre_  | _Descripción_  | _Tipo_ |
| _ID Administrador_  | Identificador único del administrador | String |
| _Nombre_ | Nombre completo del administrador | String |
| _Cargo_ | Cargo del administrador (ej: Jefe de Catálogo) | String |

## Casos de uso

### Caso de Uso 1: Buscar productos

|  Caso de Uso  CU.1 | Buscar Productos |
|---|---|
| **Fuentes**  | Este caso de uso se sustenta gracias al [documento de especificación](#) |
| **Actor**  | Cliente, Administrador |
| **Descripción** | El cliente o administrador puede buscar productos en el catálogo en línea usando filtros como categoría, precio o nombre del producto. |
| **Flujo básico** | 1. El cliente ingresa un criterio de búsqueda (por ejemplo, nombre o categoría).<br>2. El sistema muestra los productos que coinciden con el criterio.<br>3. El cliente selecciona un producto para ver más detalles. |
| **Pre-condiciones** | El sistema debe tener productos en el catálogo, y el cliente debe tener acceso al catálogo. |
| **Post-condiciones** | El sistema muestra los resultados de la búsqueda de productos. |
| **Requerimientos** | Base de datos actualizada de productos, interfaz de búsqueda funcional. |
| **Notas** | El administrador también puede usar esta funcionalidad para verificar la disponibilidad de productos. |
| **Autor**  | AdriánRoguez |
| **Fecha** | 05/11/2024 |

### Caso de Uso 2: Añadir productos al carrito

|  Caso de Uso  CU.2 | Añadir Productos al Carrito |
|---|---|
| **Fuentes**  | Este caso de uso se sustenta gracias al [documento de especificación](#) |
| **Actor**  | Cliente |
| **Descripción** | El cliente puede añadir productos a su carrito de compras para proceder con la compra más tarde. |
| **Flujo básico** | 1. El cliente selecciona el producto que desea comprar.<br>2. El cliente hace clic en el botón "Añadir al carrito".<br>3. El sistema agrega el producto al carrito de compras del cliente. |
| **Pre-condiciones** | El cliente debe haber iniciado sesión o continuar como invitado para agregar productos al carrito. |
| **Post-condiciones** | El producto se agrega al carrito de compras del cliente. |
| **Requerimientos** | El sistema debe tener un carrito de compras funcional para cada cliente. |
| **Notas** | El cliente puede agregar varios productos al carrito antes de proceder al pago. |
| **Autor**  | AdriánRoguez |
| **Fecha** | 05/11/2024 |

### Caso de Uso 3: Realizar pedido

|  Caso de Uso  CU.3 | Realizar Pedido |
|---|---|
| **Fuentes**  | Este caso de uso se sustenta gracias al [documento de especificación](#) |
| **Actor**  | Cliente |
| **Descripción** | El cliente finaliza su compra seleccionando los productos del carrito y proporcionando los detalles de envío. |
| **Flujo básico** | 1. El cliente revisa los productos en su carr



# Sistema de Gestión de Cursos en Línea

## Actores

### Actor 1: Estudiante

| **Actor** | Estudiante |
|-----------|------------|
| **Descripción**  | El estudiante se inscribe en cursos, visualiza el material del curso y realiza las evaluaciones. |
| **Características**  | El estudiante debe estar registrado en la plataforma y tener acceso a los cursos en los que se ha inscrito. |
| **Relaciones**  | Interactúa con los casos de uso: Inscribirse en curso, Ver material del curso, Realizar evaluaciones. |
| **Referencias** | Inscribirse en curso, Ver material del curso, Realizar evaluaciones |
| **Notas** |  |
| **Autor**  | Adrián |
| **Fecha** | 05/11/2024 |

|  Atributo |||
|---|---|---|
| _Nombre_  | _Descripción_  | _Tipo_ |
| _ID Estudiante_  | Identificador único del estudiante | String |
| _Nombre_ | Nombre completo del estudiante | String |
| _Email_ | Correo electrónico del estudiante | String |
| _Fecha de inscripción_ | Fecha en que el estudiante se registró en el sistema | Fecha |

### Actor 2: Profesor

| **Actor** | Profesor |
|-----------|----------|
| **Descripción**  | El profesor crea cursos, actualiza el contenido y califica las evaluaciones de los estudiantes. |
| **Características**  | El profesor tiene acceso administrativo para gestionar los cursos y las evaluaciones. |
| **Relaciones**  | Interactúa con los casos de uso: Crear curso, Calificar evaluaciones, Actualizar contenido del curso. |
| **Referencias** | Crear curso, Calificar evaluaciones, Actualizar contenido del curso |
| **Notas** | El profesor puede acceder a los materiales de todos los cursos que gestiona. |
| **Autor**  | Adrián |
| **Fecha** | 05/11/2024 |

|  Atributo |||
|---|---|---|
| _Nombre_  | _Descripción_  | _Tipo_ |
| _ID Profesor_  | Identificador único del profesor | String |
| _Nombre_ | Nombre completo del profesor | String |
| _Email_ | Correo electrónico del profesor | String |
| _Materia_ | Materia o área que imparte el profesor | String |

## Casos de uso

### Caso de Uso 1: Inscribirse en curso

|  Caso de Uso  CU.1 | Inscribirse en Curso |
|---|---|
| **Fuentes**  | Este caso de uso se sustenta gracias al [documento de especificación](#) |
| **Actor**  | Estudiante |
| **Descripción** | El estudiante se inscribe en un curso disponible en la plataforma para poder acceder al contenido y realizar evaluaciones. |
| **Flujo básico** | 1. El estudiante ingresa a la plataforma.<br>2. El estudiante busca un curso disponible.<br>3. El estudiante se inscribe en el curso elegido.<br>4. El sistema confirma la inscripción y agrega el curso a su lista de cursos. |
| **Pre-condiciones** | El estudiante debe estar registrado en la plataforma. |
| **Post-condiciones** | El estudiante está inscrito en el curso y tiene acceso al material. |
| **Requerimientos** | Acceso a la plataforma, cursos disponibles en el catálogo. |
| **Notas** | El estudiante puede inscribirse en varios cursos si así lo desea. |
| **Autor**  | AdriánRoguez |
| **Fecha** | 05/11/2024 |

### Caso de Uso 2: Ver material del curso

|  Caso de Uso  CU.2 | Ver Material del Curso |
|---|---|
| **Fuentes**  | Este caso de uso se sustenta gracias al [documento de especificación](#) |
| **Actor**  | Estudiante |
| **Descripción** | El estudiante visualiza los materiales proporcionados en el curso, como videos, lecturas o tareas. |
| **Flujo básico** | 1. El estudiante ingresa al curso en el que está inscrito.<br>2. El sistema muestra el listado de materiales disponibles (videos, documentos, tareas).<br>3. El estudiante selecciona el material que desea ver.<br>4. El sistema presenta el material elegido al estudiante. |
| **Pre-condiciones** | El estudiante debe estar inscrito en el curso y tener acceso al contenido. |
| **Post-condiciones** | El estudiante puede ver el material del curso seleccionado. |
| **Requerimientos** | El curso debe tener materiales cargados en el sistema. |
| **Notas** | El sistema debe garantizar que los materiales estén accesibles en todo momento. |
| **Autor**  | AdriánRoguez |
| **Fecha** | 05/11/2024 |

### Caso de Uso 3: Realizar evaluaciones

|  Caso de Uso  CU.3 | Realizar Evaluaciones |
|---|---|
| **Fuentes**  | Este caso de uso se sustenta gracias al [documento de especificación](#) |
| **Actor**  | Estudiante |
| **Descripción** | El estudiante realiza evaluaciones (exámenes, tareas) dentro del curso, según lo requerido por el profesor. |
| **Flujo básico** | 1. El estudiante ingresa al curso en el que está inscrito.<br>2. El estudiante selecciona la evaluación que debe completar.<br>3. El sistema presenta las preguntas o tareas de la evaluación.<br>4. El estudiante responde o realiza la tarea.<br>5. El sistema envía la evaluación para su calificación. |
| **Pre-condiciones** | El estudiante debe haber iniciado sesión y tener acceso a las evaluaciones del curso. |
| **Post-condiciones** | El sistema registra las respuestas del estudiante y las envía para calificación. |
| **Requerimientos** | El curso debe tener evaluaciones disponibles y el sistema debe aceptar respuestas. |
| **Notas** | Las evaluaciones pueden ser exámenes, proyectos o tareas. |
| **Autor**  | AdriánRoguez |
| **Fecha** | 05/11/2024 |

### Caso de Uso 4: Crear curso

|  Caso de Uso  CU.4 | Crear Curso |
|---|---|
| **Fuentes**  | Este caso de uso se sustenta gracias al [documento de especificación](#) |
| **Actor**  | Profesor |
| **Descripción** | El profesor crea un curso nuevo, añadiendo detalles como nombre, descripción, materiales y evaluaciones. |
| **Flujo básico** | 1. El profesor accede a la plataforma con privilegios administrativos.<br>2. El profesor selecciona la opción de crear un nuevo curso.<br>3. El profesor ingresa los detalles del curso (nombre, descripción, etc.).<br>4. El sistema guarda el curso en la plataforma. |
| **Pre-condiciones** | El profesor debe estar autenticado y tener permisos para crear cursos. |
| **Post-condiciones** | El nuevo curso se agrega al catálogo de cursos disponibles para los estudiantes. |
| **Requerimientos** | Acceso administrativo, base de datos de cursos. |
| **Notas** | El profesor puede agregar varios materiales y tareas durante la creación del curso. |
| **Autor**  | AdriánRoguez |
| **Fecha** | 05/11/2024 |

### Caso de Uso 5: Calificar evaluaciones

|  Caso de Uso  CU.5 | Calificar Evaluaciones |
|---|---|
| **Fuentes**  | Este caso de uso se sustenta gracias al [documento de especificación](#) |
| **Actor**  | Profesor |
| **Descripción** | El profesor califica las evaluaciones completadas por los estudiantes. |
| **Flujo básico** | 1. El profesor accede al sistema de calificaciones.<br>2. El profesor selecciona una evaluación completada por un estudiante.<br>3. El profesor asigna una calificación.<br>4. El sistema guarda la calificación y actualiza el historial del estudiante. |
| **Pre-condiciones** | El estudiante debe haber completado y enviado la evaluación. |
| **Post-condiciones** | La calificación se guarda en el sistema y se refleja en el expediente del estudiante. |
| **Requerimientos** | El profesor debe tener acceso al sistema de calificación y al resultado de las evaluaciones. |
| **Notas** | El profesor puede asignar calificaciones manualmente o automáticamente si el sistema lo permite. |
| **Autor**  | AdriánRoguez |
| **Fecha** | 05/11/2024 |

### Caso de Uso 6: Actualizar contenido del curso

|  Caso de Uso  CU.6 | Actualizar Contenido del Curso |
|---|---|
| **Fuentes**  | Este caso de uso se sustenta gracias al [documento de especificación](#) |
| **Actor**  | Profesor |
| **Descripción** | El profesor actualiza o modifica el contenido del curso, como materiales, evaluaciones o tareas. |
| **Flujo básico** | 1. El profesor accede al curso que desea modificar.<br>2. El profesor realiza los cambios necesarios (añadir/eliminar materiales, modificar evaluaciones).<br>3. El sistema guarda los cambios y actual