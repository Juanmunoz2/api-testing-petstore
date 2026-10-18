# api-testing-petstore
Proyecto de pruebas de API REST para PetStore con Postman y documentación QA

### **INFORMACIÓN GENERAL**

- **NOMBRE DEL PROYECTO:** Pruebas de API y documentación de pruebas PetStore (REST API)
- **ESPECIALIDAD:** Prueba de API y documentación de pruebas
- **FUENTE DEL PROYECTO:** API pública de práctica
- **LINK DE LA FUENTE UTILIZADA:** https://petstore.swagger.io/
- **LINK AL PROYECTO:** https://docs.google.com/spreadsheets/d/1X59cEuuPAhNt9OeKQ2Pw4Y--AlkRQFuW-0uQ5LvxAf0/edit?usp=sharing

### MÉTRICAS DEL PROYECTO ###
* Endpoints cubiertos: 3 módulos principales (/pet, /store, /user).
* Casos de prueba diseñados: 6 casos (combinando pruebas positivas y negativas).
* Casos ejecutados: 100% de ejecución (5 pasados con éxito, 1 detectado como incidencia).

### **PLAN DE TRABAJO**

1. **Exploración (Análisis de requisitos):** Revisión de la especificación OpenAPI/Swagger para analizar los endpoints que disponen (/pet, /store, /user), los métodos HTTP(GET, POST, PUT, DELETE) y el payload de solicitud y respuesta
2. **Preparación(Diseño de casos de prueba):** Creación de casos de prueba para endpoints de mascotas (por ejemplo /pet), definiendo situaciones con datos válidos, vacíos y incorrectos
3. **Construcción(Ejecución de pruebas):** Configuración en Postman para ejecutar las peticiones HTTP de forma ordenada
4. **Evaluación(Respuestas y bugs recibidos):** Verificación de los códigos de respuesta(200 OK, 400 Bad Request, 400 Not Found etc.) y revisión de los cuerpos de respuesta, en este caso JSON
5. Resultado final: Documentación de los casos de prueba

### QUÉ SE HIZO Y CÓMO?

- **Tipos de prueba**
    
    Pruebas funcionales de API, validaciones en JSON y codigos de estado HTTP
    
- **Herramientas utilizadas**
    - Postman: Programa para la ejecucion y diseño de las peticiones HTTP
    - Github: Almacenamiento del repositorio exportada en JSON
    - Google Sheets: Hoja de cálculo en donde se documenta los casos de prueba
- **Criterios**
    - Las peticiones POST/pet devuelven un código 200 ok y el objeto creado en la respuesta
    - Las peticiones GET/pet/{petid} que no existan devuelven un código 404

### HISTORIA STAR BASADA EN PROBAR UNA API ###

"Diseñé una suite de pruebas de API REST en Postman cubriendo múltiples endpoints, donde demostré pensamiento crítico al identificar fallas en el manejo de códigos de error HTTP y estructuré los resultados bajo criterios profesionales de QA."

* Situación: Estaba realizando pruebas de caja negra y validación de límites en la API de PetStore, específicamente en el endpoint de consulta por ID (GET /pet/{petId}).
  
* Tarea: Mi objetivo era verificar que el sistema manejara correctamente los escenarios negativos, como buscar registros que no existen o enviar formatos de datos inválidos.
  
* Acción: Al ejecutar una petición consultando un ID negativo (GET /pet/-1), analicé detalladamente el código de estado HTTP devuelto y el cuerpo de la respuesta en el formato JSON.
  
* Resultado: Descubrí que la API no devolvía un código estandarizado 404 Not Found con un mensaje claro, sino que lanzaba un error interno del servidor con una traza de Java (NumberFormatException). Documenté este hallazgo explicando que esto representa un riesgo de seguridad menor (por exponer información interna del backend) y mala experiencia para los desarrolladores que consumen la API. Este enfoque me permitió ir más allá de la ruta feliz y demostrar cómo un QA aporta valor preventivo.


### RESULTADOS

- Al enviar un ID de una mascota con una solicitud correcta ya sea creándola, consultándola, modificándola o tratando de eliminarla tiene que mostrarse el estado de la solicitud exitosa
- Al enviar un ID de mascota negativo en la consulta GET/pet/-2 por ejemplo, la API devuelve un mensaje de error complicado de entender en lugar de un error 404 común, siendo esta una severidad media


### CONCLUSION ###
Aprendí la importancia de no limitarme a probar el "camino feliz" (happy path), sino explorar los límites, los tipos de datos erróneos y los códigos de estado HTTP.



  
