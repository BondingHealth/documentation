## Read Me

- [Root](https://github.com/BondingHealth/app#readme)
- [Native](https://github.com/BondingHealth/app/tree/main/packages/native#readme)
- [Backend](https://github.com/BondingHealth/app/tree/main/packages/backend#readme)
- [CMS](https://github.com/BondingHealth/app/tree/main/packages/frontend#readme)

## API Documentation

- [Child](https://github.com/BondingHealth/app/blob/main/packages/backend/src/domains/child/README.md)
- [User](https://github.com/BondingHealth/app/blob/main/packages/backend/src/domains/user/README.md)
- [Behaviors](https://github.com/BondingHealth/app/blob/main/packages/backend/src/domains/behaviors/README.md)
- [Events](https://github.com/BondingHealth/app/blob/main/packages/backend/src/domains/events/README.md)
- [Exercises](https://github.com/BondingHealth/app/blob/main/packages/backend/src/domains/exercises/README.md)
- [GraphQL Schema](https://github.com/BondingHealth/app/blob/main/packages/backend/src/schema.js)

# Treatments

Treatments are various medicines or activities (exercises) that are applied by a parent to a child.

## API Endpoints

- **_createTreatment_** `(admin)` creates a new Treatment
- **_readTreatment_** `(admin)` returns a single Treatment from the available Treatments
- **_updateTreatment_** `(admin)` updates an existing Treatment
- **_deleteTreatment_** `(admin)` remove an existing Treatment
- **_readTreatments_** `(admin & user)` returns all Treatments that are available
- **_createTreatmentEvent_** `(admin & user)` applies a Treatment to a child: `dosage, frequency`
- **_readTreatmentsByChild_** `(admin & user)` returns all Treatments for an individual child
- **_deleteTreatmentByChild_** `(admin & user)` delete a Treatment from a child
- **_updateTreatmentByChild_** `(admin & user)` updates a Treatment for a child

## Model

```
Treatment
{
    id
    title
    weight
    defaultDosage
}
```

```
TreatmentEvent
{
    childId: ID!
    treatment: ID!
    dose: Int!
    dates: [String]!
    time: String
}
```
