---
icon: markdown
---

# Modulos

En JavaScript, un módulo es un archivo que contiene funciones, clases o bibliotecas para un objetivo específico. Los módulos permiten organizar el código en partes reutilizables, lo que facilita su mantenimiento y mejora la legibilidad.

<figure><img src="../.gitbook/assets/modules.png" alt=""><figcaption></figcaption></figure>

Ten en cuenta que, según el concepto de un módulo, trabajarás con ellos a lo largo del desarrollo del proyecto, ya sea implementando nuevos módulos o añadiendo funcionalidades. Esto te permitirá estructurar y reutilizar el código de manera más eficiente y ordenada.

```javascript
/* ../modules/file.js */

// encapsula las variables para no ocasionar errores en otros módulos
(function () {
    // ... Inicializa la funcion principal
    
    /* 
        ... Crea las funciones de acuerdo a tu lógica
    */
    
})();
```

{% hint style="info" %}
Si cuentas con mas módulos, puedes crear nuevos e importarlos al módulo que tu requieras.\
Toma en cuenta que debes llamar correctamente el modulo en la vista que lo requieras y configurar el script tipo "**module**".
{% endhint %}
