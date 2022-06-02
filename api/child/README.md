## API Documentation

-   [Child](child/README.md)
-   [User](user/README.md)
-   [Behaviors](behaviors/README.md)
-   [Events](events/README.md)
-   [Treatments](treatments/README.md)
-   [Exercises](exercises/README.md)

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
