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
- [Treatments](https://github.com/BondingHealth/app/blob/main/packages/backend/src/domains/treatments/README.md)
- [GraphQL Schema](https://github.com/BondingHealth/app/blob/main/packages/backend/src/schema.js)

# Exercises

Recordings and transcripts of Exercises that users can listen to or read. Mood before and after exercise are both recorded.

## API Endpoints

- **_createExercise_** `(admin)` creates a new Exercise
- **_updateExercise_** `(admin)` updates an existing Exercise
- **_deleteExercise_** `(admin)` remove an existing Exercise
- **_readAllExercises_** `(admin & user)` returns all available Exercises
- **_readExercise_** `(admin & user)` returns a single Exercise from the available Exercises

## Model

```
Exercise
{
    id: ID
    tags: [string]
    title: string
    description: string
    duration: float
    audio: string
    relatedBehaviors: [ID]
}
```

```
ExerciseEvent
{
    userId: ID // user who took the exercise
    exerciseId: ID // the exercise being taken
    version: Int
    exerciseResponses: [
        value: Int||String
    }] // array of answers to the 7 questions - easy to perform a [where array-contains](https://firebase.google.com/docs/firestore/query-data/queries#array_membership) to filter
}
```
