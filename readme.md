# PreEntrega 1 - Juan Ignacio Armas

## Programación Backend I: Desarrollo Avanzado de Backend - Comisión 70365

### E-commerce Endpoints y Servicios

## Descripción del Proyecto

Se desarrollará un servidor que contenga los endpoints y servicios necesarios para gestionar los productos y carritos de compra en el e-commerce. Desarrollar el servidor basado en Node.JS y express, que escuche en el puerto 8080 y disponga de dos grupos de rutas: /products y /carts. Dichos endpoints estarán implementados con el router de express.

## Se debe entregar

Para el manejo de productos, el cual tendrá su router en /api/products/ , configurar las siguientes rutas:
- La ruta raíz GET / deberá listar todos los productos de la base.
- La ruta GET /:id deberá traer sólo el producto con el id proporcionado
- La ruta raíz POST / deberá agregar un nuevo producto con los campos:
    - id: Number/String
    - title:String
    - description:String
    - code:String
    - price:Number
    - status:Boolean
    - stock:Number
    - category:String
    - thumbnails: Array de Strings que contenga las rutas donde están almacenadas las imágenes referentes a dicho producto
    - Status es true por defecto        
- La ruta PUT /:id deberá tomar un producto y actualizarlo por los campos enviados desde body. NUNCA se debe actualizar o eliminar el id al momento de hacer dicha actualización.
- La ruta DELETE /:id deberá eliminar el producto con el pid indicado.

Para el carrito, el cual tendrá su router en /api/carts/, configurar dos rutas:
- La ruta raíz POST / deberá crear un nuevo carrito con la siguiente estructura:
    - Id:Number/String
    - products: Array que contendrá objetos que representen cada producto
- La ruta GET /:id deberá listar los productos que pertenezcan al carrito con el parámetro cid proporcionados.
- La ruta POST /:id/product/:id deberá agregar el producto al arreglo “products” del carrito seleccionado, agregándose como un objeto bajo el siguiente formato:
    - product: SÓLO DEBE CONTENER EL ID DEL PRODUCTO (Es crucial que no agregues el producto completo)
    - quantity: debe contener el número de ejemplares de dicho producto. El producto, de momento, se agregará de uno en uno. Además, si un producto ya existente intenta agregarse al producto, incrementar el campo quantity de dicho producto. 

La persistencia de la información se implementará utilizando el file system, donde los archivos “productos,json” y “carrito.json”, respaldan la información.
No es necesario realizar ninguna implementación visual, todo el flujo se puede realizar por Postman o por el cliente de tu preferencia

##  Formato
 - Link al repositorio de Github con el proyecto completo, sin la carpeta de Node_modules.

**Sugerencias**
 - No olvides app.use(express.json())
 - No es necesario implementar multer
