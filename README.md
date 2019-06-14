<h1 align="center">Gatsby + Contentful + GitLab</h1>
Roll out a static site quickly and cheaply.

- Gatsby - Build your site
- Contentful - Manage your content
- GitLab - Deploy and host your static site
## Setup
1. Clone the repo
2. Start a Contentful space and add the id to `gatsby-config.js`
3. Create a `.env` file at the root of your project with the following line: `CONTENTFUL_ACCESS_TOKEN=yourAccessTokenHere`

    _(The `.env` is ignored and should not be commited for security reasons!)_
4. Run `docker-compose up` to build the site on `http://localhost:5000` (If you don't have Docker grab it [here](https://www.docker.com/))
5. You will need to enable various settings in GitLab in order to automatically deploy the site. More info can be found [here](https://docs.gitlab.com/ce/ci/quick_start/README.html). It is important to note you will need to include your Contentful token in your GitLab settings.

## Deploying
To deploy the site simple commit to the master branch of your GitLab repo. If you'd rather it deploy using another branch change the last line of the `.gitlab-ci.yml` file.

This project is setup assuming you want this to be your root GitLab page. (Your repo name is the same as your username.) If that is not the case you'll need to modify two files:

1. `gatsby-config.js` add this to your `module.exports`: ```pathPrefix: `/example-repo-name` ```
2. `.gitlab-ci.yml` add ```--prefix-paths``` after `npm run-script build`

## What's included?
- A barebones Gatsby project with a couple useful plugins
- A Docker container to make development and delployment easier
- ESLint and Prettifier to keep your code sharp

### License
gatsby-contentful-gitlab-starter is licensed under the MIT license

_Copyright 2019 Ivo Ilić_

_Based on [gatsby-starter-hello-world](https://github.com/gatsbyjs/gatsby-starter-hello-world) - Copyright 2018 gatsbyjs_

