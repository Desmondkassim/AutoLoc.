
# AutoLoc - Fetch and Cascade Strategy

| Relationship | Fetch | Cascade | Reason |
|---|---|---|---|
| Contrat to Paiement | LAZY | ALL + orphanRemoval | Payments depend on their contract |
| Agence to Vehicule | LAZY | None | Vehicles survive agency deletion |
| Agence to Employe | LAZY | None | Employees are managed independently |
| Vehicule to Equipement | LAZY | None | Equipment can be shared |
| Client to Reservation | LAZY | PERSIST | New reservations can be saved with the client |
| Reservation to Vehicule | LAZY | None | Vehicles exist independently |
| Reservation to Contrat | LAZY | ALL | Contract lifecycle is managed by reservation |
| Vehicule to Maintenance | LAZY | PERSIST | New maintenance records can be saved with vehicles |

LAZY loading avoids retrieving unnecessary related data.

Cascade operations are selected according to whether
the related entity has an independent lifecycle.

The owning side stores the foreign key.
