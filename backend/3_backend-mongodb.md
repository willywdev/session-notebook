# Backend MongoDB

- Daten immer verfügbar machen, localStorage hat eine maximale Menge an Daten
- Bisher waren Daten immer nur temporär verfügbar
- Arten von Datenbanken: Relational vs Non-Relational (SQL vs noSQL (Not Only SQL)
  - Relational = Daten werden in Tabellen gespeichert (wie bei Excel), Tabellen können untereinander verknüpft sein, werden in den meisten Projekten verwendet, Nachteil: Neue Informationskategorien nachtragen gestaltet sich schwierig, nicht gut skalierbar & nicht sehr flexibel
  - SQL: `SELECT PRODUCT_NAME, PRICE FROM PRODUCT WHERE PRODUCT _ID = 23;`
  - Non-Relational = Daten werden wie in json gespeichert (Key-Value-Pairs), es wird auf eine Art Dokumentenbasis gearbeitet (z.B. jeder Customer ist ein Dokument), besser skalierbar
  - mongoDB: `db.product.find({"_id": 23}, {productName: 1, price: 1})`
- MongoDB = noSQL Datenbank
- CRUD Operationen (Create, Read, Update, Delete)

## MongoDB

- Mongo von "Humongous"
- Wir nutzen MongoDB Atlas (kostenfreie Cloud Datenbank)
- Database -> Build a database
- Server egal (AWS, Google Cloud, Azure)
- Region so nah wie möglich wählen (Frankfurt)
- Authenticate with username and password (Zugriff zur Datenbank)
- Connect from local environment and give current ip adress (ip adress from server which the site is running from)
  - Another IP: 0.0.0/0 - Global: Zugriff von allen IP Adressen
- Daten werden in Collections gespeichert
  - Collection von Dokumenten
- IDs werden automatisch erzeugt
