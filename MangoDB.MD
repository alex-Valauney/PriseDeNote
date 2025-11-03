# Liste de commande

## MangoDB

lancer mongo :
``sudo systemctl start mongod``

vérifié qu'il tourne :
``sudo systemctl status mongod``

ouvrir mango :
``mongosh``

rentrée dans la DB :
``use letsplay``

trouver utilissateur :
``db.users.find().pretty()``

insérer un utilisateur :
``db.users.insertOne({
  name: "Admin",
  email: "admin@letsplay.com",
  password: "$2a$10$h8ZgZ9W2D7TdyzvXWmJ.xuZyo9JsyWcKmxDqkR9X12T1NH7HHmZtG", // correspond à "admin123"
  role: "ADMIN"
})
``
