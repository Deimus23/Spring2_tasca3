# Sistema de Gestió d'Una Òptica amb MongoDB

Aquest projecte consisteix en el disseny i implementació d'una base de dades per a l'optimització de la gestió d'una òptica anomenada “Cul d'Ampolla”, utilitzant MongoDB com a sistema de gestió de bases de dades NoSQL. Es tenen en compte diversos aspectes relacionats amb clients/es, ulleres, proveïdors/es i vendes.

## Objectiu
L'objectiu principal és crear una estructura de base de dades flexible i escalable que permeti gestionar la informació d'una manera eficient i adequada a les necessitats de l'òptica. S'han definit dues perspectives per al disseny de la base de dades: des del punt de vista dels clients/es i des del punt de vista de les ulleres.

---

## Informació Emmagatzemada

### Proveïdors/es
De cada proveïdor/a, es desa:
- **Nom**
- **Adreça completa** (carrer, número, pis, porta, ciutat, codi postal i país)
- **Telèfon**
- **Fax**
- **NIF**

### Ulleres
Per a les ulleres, s'emmagatzema:
- **Marca**
- **Graduació de cada vidre**
- **Tipus de muntura** (flotant, pasta o metàl·lica)
- **Color de la muntura**
- **Color de cada vidre**
- **Preu**

### Clients/es
De cada client/a, es desa:
- **Nom**
- **Adreça postal**
- **Telèfon**
- **Correu electrònic**
- **Data de registre**
- **Referència al client/a que els ha recomanat**, si escau

### Vendes
Cada venda registra:
- **Ullera venuda**
- **Empleat/da responsable de la venda**
- **Data i hora de la venda**

---

## Exercicis de Disseny

### Exercici 1: Disseny des del punt de vista del client
Quan la interfície gràfica està enfocada al client, la base de dades ha de permetre:
- Consultar quines ulleres ha comprat un client.
- Saber quina és la història de recomanacions entre clients.
- Obtenir dades detallades sobre un client, incloent la seva informació de contacte i registre.

**Estructura suggerida:**
Els clients es representen com a documents independents, amb referències a les ulleres comprades i al client recomanador (si n'hi ha).

### Exercici 2: Disseny des del punt de vista de les ulleres
Quan la interfície està enfocada a les ulleres, la base de dades ha de permetre:
- Consultar quines ulleres estan disponibles segons la marca, tipus de muntura o graduació.
- Identificar el proveïdor de cada model d'ullera.
- Saber a quin client s'ha venut cada ullera i per quin empleat.

**Estructura suggerida:**
Les ulleres es representen com a documents independents amb referències al proveïdor, al client que les ha comprat i a l'empleat responsable de la venda.

---

## Avantatges d'Utilitzar MongoDB
- **Flexibilitat:** MongoDB permet estructurar els documents segons les necessitats de cada cas d'ús.
- **Escalabilitat:** El sistema és ideal per a manejar grans quantitats de dades.
- **Consultes dinàmiques:** Amb MongoDB, es poden realitzar consultes complexes i adaptades als diferents punts de vista del sistema.

## Autor
Creat per **Antonio Carrasco**.

## Llicència
Aquest projecte està sota la llicència MIT. Consulta el fitxer `LICENSE` per a més detalls.

