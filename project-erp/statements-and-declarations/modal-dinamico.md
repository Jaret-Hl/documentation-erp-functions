---
description: 📌 Descripción general del código
icon: image-landscape
---

# Modal Dinámico

Este código define un **Web Component** personalizado llamado `<modal-dinamico>`, que genera automáticamente un modal de Bootstrap 5. Es completamente reutilizable y configurable a través de atributos HTML. Su propósito es ayudarte a crear modales dinámicos sin repetir código HTML en cada vista.

```javascript
customElements.define(
    "modal-dinamico",
    class extends HTMLElement {
        constructor() {
            super();

            const modalId = this.getAttribute("data-id") || "modal";
            const modalTitle = this.getAttribute("data-title") || "Modal Title";
            const modalBody = this.getAttribute("data-body") || "Modal Body";
            const modalFooter = this.getAttribute("data-footer") || "";
            const modalSize = this.getAttribute("data-size") || "xl";
            const modal = document.createElement("div");
            modal.innerHTML = `
        <div class="modal fade" id="${modalId}" tabindex="-1" role="dialog" aria-labelledby="exampleModalLabel" aria-hidden="true">
          <div class="modal-dialog modal-dialog-centered modal-${modalSize}" role="document">
            <div class="modal-content">
              <div class="modal-header">
                <h5 class="modal-title">${modalTitle}</h5>
                <button type="button" class="btn-close" data-bs-dismiss="modal" aria-label="Close"></button>
              </div>
              <div class="modal-body" id="${modalBody}">
              </div>
              <div class="modal-footer" id="${modalFooter}">
              </div>
            </div>
          </div>
        </div>
      `;
            this.appendChild(modal);
        }
    }
);
```

#### 🧠 **Explicación paso a paso**

1.  **`customElements.define(...)`**

    Registra un nuevo elemento personalizado llamado `<modal-dinamico>`. Cualquier vez que uses esa etiqueta en el HTML, se ejecutará la clase definida.\

2.  **Constructor de la clase**

    \
    Dentro del constructor:

    * Se leen los atributos HTML del componente:
      * `data-id`: ID del modal (para abrirlo con JavaScript).
      * `data-title`: Título que se mostrará en el encabezado.
      * `data-body`: ID del contenedor de contenido principal del modal.
      * `data-footer`: ID del pie del modal (por si quieres insertar botones).
      * `data-size`: Tamaño del modal (`sm`, `lg`, `xl`, etc.).
3.  **Creación dinámica del modal**

    Se crea un `div` que contiene el modal en formato Bootstrap 5 y se inyecta al DOM automáticamente.



{% hint style="info" %}
You can also add images simply by copying and pasting them directly into the editor — and GitBook will automatically add it to your file manager.
{% endhint %}
