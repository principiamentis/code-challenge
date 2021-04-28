## DB Frontend Code challenge

This challenge is designed to introduce you to making GraphQL queries and getting data from APIs. The aim is to create a basic UI utilizing the data from the DB Train Network. Fortunately, DB provides a public GraphQL API to make this easy.

<https://bahnql.herokuapp.com/graphql> (Source code: <https://github.com/dbsystel/1BahnQL> - note that downloading the source code is *not* required to run queries against the Heroku app).

You should aim to create a basic UI to display data from this API and display it using React. Beyond using React.js, it's 100% up to you: what your UI chooses to show, whether you use any other APIs to supplement this data and if you choose to use any other libraries to help you.

## Ideas to get started

We recommend taking a look at the GraphQL API before decided on a project to understand what is and isn't possible, but some examples to get you started may be:

- A UI that allows the user to search for a station, showing interesting details about each station.
- A UI that displays Station locations using the geo data from the API and plots this onto a map, with the ability to also show other nearby stations and station information.
- A UI that displays Journey segments between two stations chosen by the user, providing details on the trains and routes.

Again, these are simply ideas, you can take 1 or more of these ideas and combine them or come up with an entirely new concept based on the data available (You can even write a Game that battles the length of Train-station staircases against each other!).

## Using the GraphQL and the DB-API

If you're not already familiar with GraphQL it's a good idea to start here: <https://graphql.org/learn>, understand how a GraphQL API works, and mess around with the playground at <https://bahnql.herokuapp.com> which will allow you to quickly make some queries. Check the network tab in your browser and you'll likely quickly work out the general idea. 

## Some useful libraries

Probably instead of just running React in a code-pen, you'll want to use some additional npm libraries to make your life easier and run your code locally, if you haven't used React or GraphQL before the first 2 are highly recommended ways to get started, allowing you to make basic API queries easily.

- [create-react-app](https://create-react-app.dev) provides an out-of-the-box build system for writing a frontend react app, it comes with basic CSS and javascript bundling abilities and has a great getting started guide.
- [Apollo-client](https://www.apollographql.com/docs/react/get-started) Is one of the simpler libraries for making GraphQL API queries. (We use this at Principia Mentis) you'll probably want to use [useQuery hooks](https://www.apollographql.com/docs/react/api/react/hooks/#usequery) to make your API calls.
- A mapping UI like google maps or Mapbox if you want to plot coordinates.
- A [React UI Framework](https://dev.to/hasone/top-react-ui-libraries-and-frameworks-48k8) of your choice.


## Additional information

### Useful stations

Using the routing API you can find connections between two stations:

- 8000261 Munich Hbf
- 8000096 Stuttgart Hbf
- 8070004 Frankfurt (Main) Flughafen Regionalbahnhof

### Example queries

```gql
query routeFromMunichToStuttgart {
  routing(from: 8000261, to: 8000096) {
    parts {
      from {
        name
      }
      to {
        name
      }
    }
  }
}
```

```gql
query routeFromMunichToFrankfurtA {
  routing(from: 8000261, to: 8070004) {
    parts {
      product {
        name
        productCode
        productName
      }
      from {
        name
      }
      to {
        name
      }
    }
  }
}
```

```gql
query findStations {
  search(searchTerm: "Berlin"){
    stations {
      name
      primaryEvaId
    }
  }
}
```
