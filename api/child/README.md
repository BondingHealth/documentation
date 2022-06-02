## Read Me

- [Root](https://github.com/BondingHealth/app#readme)
- [Native](https://github.com/BondingHealth/app/tree/main/packages/native#readme)
- [Backend](https://github.com/BondingHealth/app/tree/main/packages/backend#readme)
- [CMS](https://github.com/BondingHealth/app/tree/main/packages/frontend#readme)

## API Documentation

- [User](https://github.com/BondingHealth/app/blob/main/packages/backend/src/domains/user/README.md)
- [Behaviors](https://github.com/BondingHealth/app/blob/main/packages/backend/src/domains/behaviors/README.md)
- [Events](https://github.com/BondingHealth/app/blob/main/packages/backend/src/domains/events/README.md)
- [Treatments](https://github.com/BondingHealth/app/blob/main/packages/backend/src/domains/treatments/README.md)
- [Exercises](https://github.com/BondingHealth/app/blob/main/packages/backend/src/domains/exercises/README.md)
- [GraphQL Schema](https://github.com/BondingHealth/app/blob/main/packages/backend/src/schema.js)

# Child

## API Endpoints

- **_createChild_** `(admin & user)` creates a new Child
- **_readChild_** `(admin & user)` returns a single Child from the available Childs
- **_readChildren_** `(admin & user)` returns all Child objects
- **_updateChild_** `(admin & user)` updates an existing Child
- **_deleteChild_** `(admin & user)` remove an existing Child

## Model

```
Child
{
    id: ID
    parent: string
    name: string
    age: number
    image {
        url: string
        title: string
    }
    gender: string
    behaviors: [BehaviorEvent] (see [Behaviors](https://github.com/BondingHealth/app/blob/main/packages/backend/src/domains/behaviors/README.md))
    treatments: [ID]
    createdDate: string
    updateDate: string
}
```
