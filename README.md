# Pixi.js Game-Boilerplate

![pixi.js logo](https://pixijs.download/pixijs-banner-no-version.png?v=1)

## Description
This is a simple template/boilerplate for implementing a slot game using TypeScript 5.7 , Pixi 7.3 and GSAP 3.12.

## How it works
1. install Node.JS 22 (LTS)
2. clone this repo
3. run these scripts (defined in package.json)
   1. `npm run clean-setup`
   2. `npm run build`
   3. `npm run start`
4. now you should see the preset on your default-browser

### Screenshot
![screenshot of application](./assets/screenshot_game.jpg)

### Possible symbol-assets
![Ten](./assets/T.png)![J](./assets/J.png)![Q](./assets/Q.png)![K](./assets/K.png)![A](./assets/A.png)![P](./assets/P.png)

## Documentations
- TypeScript https://www.typescriptlang.org/docs/
- PIXIJS - https://pixijs.download/v7.x/docs/index.html
- GSAP - https://gsap.com/docs/v3/GSAP/

## Commands

- `npm run setup` - install all npm libraries/dependencies
- `npm run clean-setup` - remove the node_modules-folder (if available) & install all npm libraries/dependencies
- `npm run build` - starts build procedure
- `npm run start` - start watching for files and open's server on localhost:8081
- `npm run lint` - generate code coverage report


# Docker as alternative
Here are the steps to set up a docker-container.

First, from the shell (bash) build the container:
`docker build --tag 'pixi-test' # from the directory with the Dockerfile`
(this step is only needed once)

Then run the container and map the directory with the git-repo into the docker-container under /home/development.
`docker run -it -p <desired localhost-port>:8080 -v "$(pwd)":/home/developer pixi-test`
Any changes in the files will be reflected in the computers filesystem and also in the containers filesystem:

Now the user should be in a bash-shell within the container in the working-directory "/home/development".

Here you can run the npm-steps to set the game up:
* `npm run clean-setup`
* `npm run build`
* `npm run start` - after that, npm monitors the files, any external changes will trigger a new build, which can be (re)loaded into the game under http://localhost:8080
