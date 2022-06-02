## API Documentation

-   [Child](child/README.md)
-   [User](user/README.md)
-   [Behaviors](behaviors/README.md)
-   [Events](events/README.md)
-   [Treatments](treatments/README.md)
-   [Exercises](exercises/README.md)

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
