
# flixme

![flixme-movies](https://i.ibb.co/KWPSjyW/Screenshot-2019-08-28-at-16-42-55.png)

FLIXME allows you to browse movies either by "infinitely" scrolling popular movies or performing a title search.

If you sign up (it's fine to use a fictitious email!) you are also able to rate movies or simply mark them as watched.

You can look for others and add them as friends in the "people" section. This allows you to follow their recent activity.

[Watch a YouTube demo here](https://youtu.be/Aq7SuDTrT0M)!

## Test-drive flixme

To run FLIXME, please follow these commands on Mac OSX. Ruby (2.4.0+) and npm must be installed in your environment.

### Rails back-end

Clone this repo: https://github.com/industriousparadigm/flixme-backend

Run `bundle install` and `rails s` to get the server running.

### React front-end

Clone this repo: https://github.com/industriousparadigm/flixme-frontend

Run `npm i` and `npm start` to start the React app. FLIXME will open automatically in your browser.

### Troubleshooting + more info

If you are unable to run it, I invite you to check out the [YouTube demo](https://youtu.be/Aq7SuDTrT0M), and don't hesitate to peek into the repos and inspect the code.

## Why am I proud of this?

FLIXME was made in 2 weeks, barely a month or two after I first learned to use React and Rails (or to make full stack web apps at all). It was the final project of my Flatiron School bootcamp and I reckon it's a fantastic achievement for this context.

My main goal was that people could play with the app without it crashing - I did not want to demo FLIXME by using it myself, but rather by letting users explore it.

### Back-end (Rails)

I had some interesting choices to make because I was using an external API (The Movie DataBase, or TMDb) which gets updated every day, combined with my own generated data (users' ratings of movies they have seen).

Eventually my Rails/Postgresql server combined all the data and is storing and serving movies, users, genres and their respective join tables. I used serializing to be able to include a "movies" field in User objects, among other tweaks to make the api simpler to use.

To ensure movie data is up to date, my back-end always queries TMDb before serving the scrollable list of popular movies that FLIXME presents as its (almost) landing page.

### Front-end (React)

I learned a lot by doing this. Some notable challenges:

- ensuring components don't break when rendering with asynchronous functions

- passing state around as props instead of repeating logic

- learning to use React Hooks

- maintaining parity between front-end data and server data

### What would I change?

Today I would implement FLIXME with:

- a Node backend

- a MongoDB database

- a GraphQL endpoint

- Redux for state management

MongoDB would be more efficient, because the SQL/serializing format caused slowdowns when trying to fetch a user's rated movies, or a user's friends and their respective movies. GraphQL would help keep the app fast when fetching dozens of movies without needing to query their 20 or so fields.

And then of course add functionalities, like better user authentication, friend requests + acceptance, filters, displaying full lists of a user's rated movies, etc.
