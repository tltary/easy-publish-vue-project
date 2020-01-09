# Easy way to deploy Vue.js project on github pages

To get started, create the repository you need on github

Next create a Vue project

Then create the deploy.sh file in the root of the project

```sh

set -e

npm run build

cd dist

git init
git add -A
git commit -m 'deploy'

git remote add origin https://github.com/<your-login>/<your-repository-name>.git
git push -u -f origin master

cd -

```

Next go to the package.json file and add the following line in scripts

```json

"publish": "sh deploy.sh"

```

Now, going to the project folder and writing npm run publish in the console, your project will be loaded into the repository you specified, you can go to github pages and see the result


## Important

If you deploy the project for the first time, after the script runs, you need to go to the settings on github, find there GitHub Pages and specify as source your master branch
