---
icon: pen-to-square
---

# Colecciones

En nuestro ámbito como desarrolladores es primordial el uso de colecciones ya que nos ayudan a manipular, almacenar y recuperar datos de manera eficiente.\
Además que pueden mejorar la legibilidad y la capacidad de mantenimiento del código. Al agrupar datos relacionados, las colecciones pueden hacer que el código sea mas fácil de entender y modificar.\
En conclusión en el proyecto encontrarás colecciones diseñadas para que puedas hacer uso de ellas y acceder rápidamente a sus elementos.

<figure><img src="../.gitbook/assets/Captura de pantalla 2024-12-12 135850.png" alt=""><figcaption></figcaption></figure>

### Datos geográficos (locations)

Esta colección es para recopilar información geográfica de un usuario durante el registro en un sistema. Y para acceder a sus elementos, realiza lo siguiente:

{% stepper %}
{% step %}
### Importar la función

```javascript
import { nationality } from "../locations/locations_v1.js";
```

Si tienes dudas de como funciona un _import_ puedes dirigirte a la pagina MDN Web Docs y leer la [<mark style="color:orange;">documentación</mark> ](https://developer.mozilla.org/es/docs/Web/JavaScript/Reference/Statements/import)de como se integra a un modulo externo.
{% endstep %}

{% step %}
### Invocar al elemento exportado&#x20;

Al momento de estar invocando al elemento nationality podrás manipular la información que contiene y en el siguiente ejemplo se muestra como acceder a dicha información.

```javascript
// Modulo externo para manipular la colección
async function example(){
    try{
        // almacenar los datos en un array
        const arrayNacionalidades = await nationality();
        // Verificar si los datos se obtuvieron correctamente
        
        if (!Array.isArray(arrayNacionalidades)) {
            throw new Error("La respuesta no es un arreglo.");
        }
        
        //procesar las nacionalidades
        const resultado = arrayNacionalidades.map(nacionalidad => {
            // manipular el objeto
            return {
                codigo: nacionalidad.codigo_pais, // suponiendo que tiene un campo 'codigo'
                pais: nacionalidad.pais // suponiendo que tiene un campo 'pais'
            };
        });
        
        console.log("listado de nacionalidades ", resultado);
        
        return resultado;
    } catch (error) {
        console.error("Error al procesar las nacionalidades:", error);
    }
}

example();
```
{% endstep %}

{% step %}
### Insert and edit your block

Click or press Enter to insert your block. From here, you’ll be able to edit it as needed.
{% endstep %}
{% endstepper %}
