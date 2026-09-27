# 🧾 Calculadora de Propinas

Aplicación web desarrollada con **React y TypeScript** que permite seleccionar productos de un menú, gestionar un pedido y calcular una propina según el porcentaje elegido.

El proyecto utiliza un **reducer** para centralizar la gestión del estado del pedido y permite actualizar las cantidades, eliminar productos, seleccionar una propina y finalizar el pedido.

## ✨ Características

* Visualización de los productos disponibles en el menú.
* Agregar productos al pedido.
* Incrementar automáticamente la cantidad de un producto si ya fue agregado.
* Eliminar productos del pedido.
* Seleccionar diferentes porcentajes de propina.
* Cálculo del subtotal del pedido.
* Cálculo de la propina seleccionada.
* Cálculo del total a pagar.
* Finalizar el pedido y reiniciar el estado de la aplicación.
* Gestión del estado mediante `useReducer`.
* Componentes reutilizables desarrollados con React.
* Tipado estático mediante TypeScript.

## 🛠️ Tecnologías utilizadas

* **React** — Desarrollo de la interfaz de usuario.
* **TypeScript** — Tipado estático y definición de estructuras de datos.
* **Vite** — Herramienta de desarrollo y construcción del proyecto.
* **CSS** — Estilos y presentación de la interfaz.
* **useReducer** — Gestión del estado del pedido y las acciones de la aplicación.

## 📁 Estructura del proyecto

```text
src/
├── components/
│   ├── MenuItem.tsx
│   ├── OrderContents.tsx
│   ├── OrderTotals.tsx
│   └── TipPercentageForm.tsx
│
├── data/
│   └── db.ts
│
├── helpers/
│   └── index.ts
│
├── reducers/
│   └── order-reducer.ts
│
└── types/
    └── index.ts
```

### Components

Contiene los componentes principales de la interfaz:

* `MenuItem.tsx` — Muestra cada producto disponible en el menú y permite agregarlo al pedido.
* `OrderContents.tsx` — Muestra los productos seleccionados, sus cantidades y permite gestionar el contenido del pedido.
* `OrderTotals.tsx` — Muestra los cálculos relacionados con el subtotal, propina y total a pagar.
* `TipPercentageForm.tsx` — Permite seleccionar el porcentaje de propina que se aplicará al pedido.

### Data

* `db.ts` — Contiene la información de los productos disponibles en el menú.

### Helpers

* `index.ts` — Contiene funciones auxiliares utilizadas para realizar cálculos o transformar información dentro de la aplicación.

### Reducers

* `order-reducer.ts` — Contiene la lógica principal para administrar el estado del pedido y las diferentes acciones que puede realizar el usuario.

### Types

* `index.ts` — Contiene las definiciones de tipos utilizadas en la aplicación, como `MenuItem` y `OrderItem`.

## ⚙️ Funcionamiento

La aplicación obtiene los productos disponibles desde `data/db.ts` y los muestra mediante componentes de React.

El estado del pedido se administra mediante un **reducer**, utilizando diferentes acciones para modificar la información.

### Agregar productos

Cuando el usuario selecciona un producto:

* Si el producto no existe en el pedido, se agrega con una cantidad inicial de `1`.
* Si el producto ya existe, se incrementa su cantidad en `1`.

### Eliminar productos

La acción `remove-item` permite eliminar completamente un producto del pedido utilizando su identificador.

### Seleccionar propina

La acción `add-tip` actualiza el porcentaje de propina seleccionado por el usuario.

### Finalizar pedido

La acción `place-order` permite finalizar el pedido y restablece el estado inicial:

* El pedido queda vacío.
* La propina vuelve a `0`.

## 🔄 Gestión del estado

El reducer utiliza dos valores principales dentro de su estado:

```text
order → Productos seleccionados y sus cantidades
tip   → Porcentaje de propina seleccionado
```

Las acciones disponibles son:

| Acción        | Función                                     |
| ------------- | ------------------------------------------- |
| `add-item`    | Agrega un producto o incrementa su cantidad |
| `remove-item` | Elimina un producto del pedido              |
| `add-tip`     | Actualiza el porcentaje de propina          |
| `place-order` | Finaliza el pedido y reinicia el estado     |

Este enfoque permite mantener la lógica de negocio separada de los componentes visuales y facilita la administración del estado de la aplicación.

## 🚀 Instalación

Clona este repositorio:

```bash
git clone URL_DEL_REPOSITORIO
```

Ingresa al directorio del proyecto:

```bash
cd NOMBRE_DEL_PROYECTO
```

Instala las dependencias:

```bash
npm install
```

Inicia el servidor de desarrollo:

```bash
npm run dev
```

La aplicación estará disponible en la URL indicada por Vite en la terminal.

## 👨‍💻 Autor

**Luis**