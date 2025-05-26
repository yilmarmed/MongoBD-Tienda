# MongoBD-Tienda
// creación de la BD Tienda

use tienda
switched to db tienda

// Creacion de la tabla

[text](<Creacion Tabla Productos>)


// Generar 100 productos de prueba
let productos = [];
for (let i = 1; i <= 100; i++) {
  productos.push({
    nombre: `Producto ${i}`,
    precio: Math.floor(Math.random() * 500) + 50, // Precio entre 50 y 550
    stock: Math.floor(Math.random() * 100) + 1,    // Stock entre 1 y 100
    categoria: `Categoria ${Math.ceil(i / 10)}`,   // 10 categorías distintas
    descripcion: `Este es el producto número ${i}`
  });
}

// Resultado del registro de los datos en producto

[text](<productos.json>)

// Insertar en la colección
db.productos.insertMany(productos);

//Filtro precio mayores que 300
db.productos.find({ precio: { $gt: 300 } })

// filtro precio entre 200 y 400
db.productos.find({
  precio: { $gte: 200, $lte: 400 }
  })

  // Insertar información
  db.productos.insertOne({
  nombre: "Producto Especial",
  precio: 399,
  stock: 25,
  categoria: "Categoria 11",
  descripcion: "Este es un producto especial agregado manualmente."
})

//Buscar producto
db.productos.findOne({ nombre: "Producto 25" })

//Contar categoria 3
db.productos.countDocuments({ categoria: "Categoria 3" })