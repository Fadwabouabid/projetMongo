# Mongo
**pour la création de base contact
use contact
** Créer la collection contactlist et insérer les documents 
db.contactlist.insertMany([
  { nom: "Ben", prenom: "Moris", email: "ben@gmail.com", age: 26 },
  { nom: "Kefi", prenom: "Seif", email: "kefi@gmail.com", age: 15 },
  { nom: "Emilie", prenom: "brouge", email: "emilie.b@gmail.com", age: 40 },
  { nom: "Alex", prenom: "marron", age: 4 },
  { nom: "Denzel", prenom: "Washington", age: 3 }
])
**Afficher toute la liste des contacts
db.contactlist.find()
**Afficher les informations d’une seule personne par son ID
db.contactlist.find({ _id: ObjectId("ID_ICI") })
**Afficher tous les contacts ayant un âge > 18
db.contactlist.find({ age: { $gt: 18 } })
**Afficher les contacts avec âge > 18 et nom contenant "ah"
db.contactlist.find({
  age: { $gt: 18 },
  nom: { $regex: "ah", $options: "i" }
})
**Changer le prénom de "Kefi Seif" en "Kefi Anis"
db.contactlist.updateOne(
  { nom: "Kefi", prenom: "Seif" },
  { $set: { prenom: "Anis" } }
)
**Supprimer les contacts ayant moins de 5 ans
db.contactlist.deleteMany({ age: { $lt: 5 } })
**Afficher toute la liste des contacts (après suppression)lul
db.contactlist.find()


