# ![RealWorld Example App](logo.png)

> ### [Svelte](https://github.com/sveltejs/svelte) codebase containing real world examples (CRUD, auth, advanced patterns, etc) that adheres to the [RealWorld](https://github.com/gothinkster/realworld) spec and API.

### [Demo](https://realworld.svelte.dev)&nbsp;&nbsp;&nbsp;&nbsp;[RealWorld](https://github.com/gothinkster/realworld)

This code use teh application real word but with some modification since we choose to display some movies location and other details. We used a back end created by our tutor. 
we worked within the locations, locationDetails login and register files. The first step was to connect the back and the frontend. In teh backend we create a .env file where we define 
a jwt which is the token that will allow the authentication besides we add teh JSON file. Then, while the app is launch the user has to log in or register to access to the movies locations.
he cans use the more info button to get more details about the movie. 

## Running locally

```bash
npm install
npm run dev
```

To build and start in prod mode:

```bash
npm run build
npm run preview
```
