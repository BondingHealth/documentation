## Read Me

- [Root](https://github.com/BondingHealth/app#readme)
- [Native](https://github.com/BondingHealth/app/tree/main/packages/native#readme)
- [Backend](https://github.com/BondingHealth/app/tree/main/packages/backend#readme)
- [CMS](https://github.com/BondingHealth/app/tree/main/packages/frontend#readme)

## API Documentation

- [Child](https://github.com/BondingHealth/app/blob/main/packages/backend/src/domains/child/README.md)
- [Behaviors](https://github.com/BondingHealth/app/blob/main/packages/backend/src/domains/behaviors/README.md)
- [Events](https://github.com/BondingHealth/app/blob/main/packages/backend/src/domains/events/README.md)
- [Treatments](https://github.com/BondingHealth/app/blob/main/packages/backend/src/domains/treatments/README.md)
- [Exercises](https://github.com/BondingHealth/app/blob/main/packages/backend/src/domains/exercises/README.md)
- [GraphQL Schema](https://github.com/BondingHealth/app/blob/main/packages/backend/src/schema.js)

# User

A parent, doctor, nanny, co-parent (aka a friend whose children is friends with the user's child) ...

## API Endpoints

- **_createUser_** `(admin & user)` creates a new User
- **_readUser_** `(admin & user)` returns the current User
- **_updateUser_** `(admin & user)` updates the current User
- **_deleteUser_** `(admin & user)` remove the current User
- **_createMoodEvent_** `(admin & user)` stores an event related to the user's mood

## Model

```
User
{
    email
    id
    image
        title
        url
    name
    phoneNumber
    privacyAccepted
    privacyAcceptedDate
    createdDate
    updateDate
    location: Lat&Long //  useful for suggesting distance to a provider and data analysis of user location
}
```

```
MoodEvent
{
    userId: ID
    moodBefore: Int
    moodAfter: Int
    action: String // what "Action" was being performed when the mood was being input ie: interact/listen to educational content, input a behavior, etc.
    createdDate: Timestamp // when the mood rating was made
    screen: String
    version: String
}
```
