## API Documentation

-   [Child](child/README.md)
-   [User](user/README.md)
-   [Behaviors](behaviors/README.md)
-   [Events](events/README.md)
-   [Treatments](treatments/README.md)
-   [Exercises](exercises/README.md)

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
