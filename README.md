# Module 3 JS Code Challenge

## Objectives

- DOM Manipulation
- Events and Event Handlers
- Callbacks
- ES6 Classes
- Fetching from APIs

## Instructions

For this code challenge, you will be building a Workout Tracker. In the end you should have a list of workouts with their names, images, reps, and a rep-increase button.

-- As a user, when the page loads, I should see a list of workouts retrieved from an API.

-- As a user, when I click the increase reps button of a workout the reps should increase for that particular workout.

## The API

For this challenge, your backend will be a json-server:

1 - Run the command `npm install -g json-server` in the command line from this directory

2 - Run `json-server --watch db.json`

You will have a server running on `localhost:3000` that serves the JSON data contained in the `db.json` file.

### Step 1 - Display All Workouts

When the page loads, I should see a list of all of the workouts retrieved from the API. The API endpoint we need for that is:

- **Route:** GET `http://localhost:3000/workouts`

#### Styling

[Bootstrap](https://getbootstrap.com/docs/3.3/components/#list-group) is loaded into this project via a link tag in the head of the html. Generally, do not worry about styling in this application.

**One important point** is that for the workouts to show up correctly, the html should have the following class names:

```html
<ul class="list-group">
  <li class="list-group-item">
    <h1>Workout Name</h1>
    <img src="<add workout img url here>" />
    <button class="btn">Increase Reps</button>
    <span>add number of reps here</span>
  </li>
  <li class="list-group-item">
    /* etc... */
  </li>
</ul>
```

### Step 2 - Increase Reps

When clicking on the increase reps button next to a workout, I can increase the reps for that workout. This click should update the DOM, as well as the reps for that workout in the database.

For this you'll need to make a PATCH request

- **Route:** PATCH `http://localhost:3000/workouts/:id`
- **Body:**

```js
{
  reps: "your new reps";
}
```

- **Headers:**

```js
  {
    'Content-Type': 'application/json',
    'Accept': 'application/json'
  }
```

**Important Notes:**

- For all intents and purposes, PATCH behaves the same as POST. If you know how to POST, you know how to PATCH
- When using `fetch` to make a PATCH request, be sure to capitalize method: 'PATCH'
