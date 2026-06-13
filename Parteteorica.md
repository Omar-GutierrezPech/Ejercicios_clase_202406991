
1. El Límite de las Rotaciones Simples y Desbalanceo en "Zig-Zag"
El Problema Cruzado

Las rotaciones simples no son suficientes cuando ocurre un desbalanceo cruzado o "zig-zag". Por ejemplo, al insertar los valores:

30
|
10
 \
  20

El nodo 30 queda desbalanceado hacia la izquierda, pero el nodo 10 tiene su crecimiento hacia la derecha.

Si se aplica únicamente una rotación simple a la derecha, el árbol sigue desbalanceado porque solamente cambia la inclinación del problema.

Una Rotación Izquierda-Derecha (RID) se ejecuta cuando:

El nodo padre tiene FE = -2 (muy cargado a la izquierda).
El hijo izquierdo tiene FE = +1 (cargado a la derecha).

Matemáticamente:

FE(Padre) = -2
FE(Hijo Izquierdo) = +1

En este caso se realiza:

Rotación simple izquierda sobre el hijo.
Rotación simple derecha sobre el padre.

Con ello el árbol recupera el equilibrio.

Principio DRY (Don't Repeat Yourself)

El principio DRY indica que no se debe duplicar lógica innecesariamente.

Implementar las rotaciones dobles reutilizando las rotaciones simples ofrece varias ventajas:

Menor cantidad de código.
Más fácil mantenimiento.
Menos errores de programación.
Mayor reutilización de funciones.
Mejor legibilidad del proyecto.

Por ejemplo:

RotacionIzquierda(hijo);
RotacionDerecha(padre);

Es más seguro que volver a reasignar todos los punteros manualmente.

2. Fundamentos de Arquitectura Web y Protocolo HTTP
Modelo Cliente-Servidor

En una arquitectura web participan principalmente:

Cliente (navegador o aplicación).
Servidor (API o aplicación web).
Red mediante HTTP.

Proceso:

Cliente
   |
Request HTTP
   |
Servidor
   |
Response HTTP
   |
Cliente

El cliente envía una petición (Request) solicitando información o realizando una acción.

El servidor procesa la solicitud y devuelve una respuesta (Response) con datos, estados HTTP o mensajes.

Semántica de Operaciones HTTP
GET

Se utiliza para recuperar información.

Características:

No modifica datos.
Es seguro.
Puede repetirse sin efectos secundarios.

Ejemplo:

GET /api/arbol

Obtiene la estructura actual del árbol.

POST

Se utiliza para crear o insertar información.

Características:

Modifica el estado del servidor.
Envía datos en el cuerpo de la petición.
Puede generar nuevos recursos.

Ejemplo:

POST /api/arbol/insertar

Inserta un nuevo nodo.

Diferencia Principal
Método	Función
GET	Recuperar información
POST	Insertar o modificar información

Por lo tanto:

GET → Recuperación de la estructura de datos.
POST → Inserción o mutación de elementos.