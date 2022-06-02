## Read Me

- [Root](https://github.com/BondingHealth/app#readme)
- [Native](https://github.com/BondingHealth/app/tree/main/packages/native#readme)
- [Backend](https://github.com/BondingHealth/app/tree/main/packages/backend#readme)
- [CMS](https://github.com/BondingHealth/app/tree/main/packages/frontend#readme)

## API Documentation

- [Child](https://github.com/BondingHealth/app/blob/main/packages/backend/src/domains/child/README.md)
- [User](https://github.com/BondingHealth/app/blob/main/packages/backend/src/domains/user/README.md)
- [Behaviors](https://github.com/BondingHealth/app/blob/main/packages/backend/src/domains/behaviors/README.md)
- [Treatments](https://github.com/BondingHealth/app/blob/main/packages/backend/src/domains/treatments/README.md)
- [Exercises](https://github.com/BondingHealth/app/blob/main/packages/backend/src/domains/exercises/README.md)
- [GraphQL Schema](https://github.com/BondingHealth/app/blob/main/packages/backend/src/schema.js)

# Events

Events are scheduled community building, audio discussion groups for parents, teachers, and therapists. Events are mediated and monitored by Bonding Health staff.

## API Endpoints

- **_createEvent_** `(admin)` create a unique event
- **_updateEvent_** `(admin)` update a unique event
- **_deleteEvent_** `(admin)` delete a unique event
- **_readAllEvents_** `(admin & user)` return list of all events
- **_readEvent_** `(admin & user)` return details about a single event

## Model

```
BondingEvent
{
    id: ID
    when: Timestamp
    who: ID // leading therapist
    title: String
    attendees: [ID] // list of users attending the event
}
```
