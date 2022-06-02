## API Documentation

-   [Child](child/README.md)
-   [User](user/README.md)
-   [Behaviors](behaviors/README.md)
-   [Events](events/README.md)
-   [Treatments](treatments/README.md)
-   [Exercises](exercises/README.md)

# Exercises

  - Parent mood before and after each exercise is logged
  - Unique audio content will ask the user 7 questions [see exercises](https://github.com/BondingHealth/documentation/blob/main/README-exercises.md)
  - version 1: Audio only **MVP**
  - version 2: Audio & Text **post** mvp
  - version 3: Audio/Text, & Interactive Data Aggregation **post** mvp

## Interactive Data Aggregation **post mvp**

Users will be asked each question individually and their response will be stored in the database.
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
