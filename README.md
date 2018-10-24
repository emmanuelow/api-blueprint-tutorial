# api-blueprint-tutorial
Basic API Blueprint Tutorial with Polls API

## Links
https://apiary.io
https://github.com/emmanuelow/api-blueprint-tutorial (this repo)
https://apiblueprint.org/documentation/tutorial.html
https://help.apiary.io/
http://dredd.org/en/latest/

## Install Dredd
### npm
```$ npm install -g dredd
$ dredd```

### Docker
```$ docker run -it -v $PWD:/api -w /api apiaryio/dredd dredd```

## Tutorial
### 0. Create a new API Design
- Go into Apiary and “Create New API Project”
- Keep “API Blueprint” Selected and name the API
- You now have a working API using a template
- Optional: Sync the API to GitHub:
- Create a new repo in GitHub
- In Apiary “Link this Project to GitHub”
- On your Laptop: `$ git clone` your repo
