![Bonding Health Logo](https://user-images.githubusercontent.com/146778/150411981-a07f26ad-93e7-45e0-91dc-48eb3296fd73.png)

# Bonding Health - backend

-   NodeJS
-   Google Cloud Platform (GCP) Functions
-   Google Cloud Platform (GCP) Firestore

## Installation

At repository root directory

-   `$ yarn backend-install`

## Local Development

At repository root directory

1. Set correct node version globally: `$ nvm use 14.16.0`
2. Start backend emulators: `$ yarn backend-start`
3. navigate to the [local dev development api playground](http://localhost:5001/bondinghealth/us-central1/api)

## Deployment

Sends files to Google Cloud Functions and Firestore:

-   `$ firebase deploy`

# GraphQL API playgrounds

-   [dev api playground](http://localhost:5001/bondinghealth/us-central1/api)
-   [production api playground](https://us-central1-bondinghealth.cloudfunctions.net/api)
-   [production (apollo studio)](https://studio.apollographql.com/graph/BondingHealth/explorer?variant=current)

useful doc: https://codeburst.io/graphql-on-cloud-functions-for-firebase-153fe7b02ea5

## Cloud Functions

### Deployment

```
$ cd packages/backend
$ firebase deploy --only functions
```

### List of Functions

#### 1. api

This is where the GraphQL server is hosted.

#### 2. processSignUp

When a new user is created, we need to update the Firestore database with user credentials. This _appears_ to be the only way to store the `uid` from the "authentication" tab in Firebase console.

#### 3. storageOnChange

This function only logs a statement that an object on storage has changed. The callback includes a reference to the object.

# API Documentation & Endpoints

Most of the below features are being built. This documentation outlines how the backend data structures will be designed. 

-   [Child](child/README.md)
-   [User](user/README.md)
-   [Behaviors](behaviors/README.md)
-   [Events](events/README.md)
-   [Treatments](treatments/README.md)
-   [Exercises](exercises/README.md)