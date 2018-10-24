# API Blueprint Tutorial

Basic API Blueprint Tutorial with Polls API

## Resources
- https://apiary.io
- http://bit.ly/api-design-tutorial (this repo)
- https://apiblueprint.org/documentation/tutorial.html
- http://dredd.org/en/latest/

## Install Dredd

### npm

```
$ npm install -g dredd
$ dredd
```

### Docker

```
$ docker run -it -v $PWD:/api -w /api apiaryio/dredd dredd
```

## Tutorial

### 0. Create a new API Design

- Go into Apiary and “Create New API Project”
- Keep “API Blueprint” Selected and name the API
- You now have a working API using a template
- Optional: Sync the API to GitHub:
- Create a new repo in GitHub
- In Apiary “Link this Project to GitHub”
- On your Laptop: `$ git clone` your repo

### 1. Multiple Responses

- Find the `/questions` resource
- Copy the response and paste above existing one
- Change the `201` to a `200` - Save
- Optional:
1. Push to GitHub from Apiary
2. `$ git pull` on your Laptop
3. test with`$ dredd apiary.apib http://polls.apiblueprint.org/`

### 2. Add a query parameter

- Add an optional `{?page}` numeric parameter with default value 1 to the `/questions` resource - Save
- Optional:
1. Push to GitHub from Apiary
2. `$ git pull` on your Laptop
3. test with`$ dredd apiary.apib http://polls.apiblueprint.org/`

### 3. Add a resource with path param

- Add `/questions/{question_id}` as the first resource in your API. The parameter should be a number with default value 1 and is required
- A `GET` method retrieves the question’s detail. Give an example JSON response (hint: it should be the same as an element in the `/questions` response array)
- Optional:
1. Push to GitHub from Apiary
2. `$ git pull` on your Laptop
3. test with `$ dredd apiary.apib http://polls.apiblueprint.org/`

### 4. Multiple path params

- Add a resource to use as a voting mechanism on the choices of a question
- Nesting parameters will work here: `/questions/{question_id}/choices/{choice_id}`
- `POST` is a nice way to tell our service we are voting
Response should be a `201`, no response body needed
- Optional: push from Apiary, pull on your laptop and test

### 5. Scratch the surface of Hypermedia

- We want an easy way to discover what the API can do
- Easiest way is to add a top-level root “`/`“ resource that tells us what other resources are available in the API
- Response looks like: `{"questions_url": "/questions"}`
- Optional: push from Apiary, pull on your laptop and test 

### 6. Different way to query

- We want a quick way to list the choices to vote on
- Add a resource `/questions/{question_id}/choices`
- `GET` should return an array of choices (hint: look at the `POST /questions` request body)
- Optional: test with dredd

### Failing Tests

- What we specced out has not been implemented!
- `$ echo $?` gives exit code: 0=success, >1=failure
- Hard to detect by eyeballing
- Hard to write tests by hand and keep them in sync
- Important to have so you don’t break clients
- API Description + Dredd in your CI/CD

### Homework: Add missing functionality

- Fork https://github.com/apiaryio/polls-api

## Go further

- https://help.apiary.io/ more about Apiary
- http://bit.ly/learn-api full API Management tutorial
- https://apiary.io/how-to-build-api interactive guide