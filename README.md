![License](https://img.shields.io/github/license/jobsonita/rocketseat-nlw-heat-impulse-node?color=blue)
![Node version](https://img.shields.io/badge/node-v14.18.0-brightgreen)
![Yarn version](https://img.shields.io/badge/yarn-v1.22.15-brightgreen)
![Express version](https://img.shields.io/github/package-json/dependency-version/jobsonita/rocketseat-nlw-heat-impulse-node/express)
![Typescript version](https://img.shields.io/badge/typescript-^4.4.4-lightgrey)
![Prisma version](https://img.shields.io/badge/prisma-^3.3.0-lightgrey)

# :rocket::seat: NLW-Heat - Impulse Track - Node Backend :outbox_tray:

[NLW-Heat](https://nextlevelweek.com/inscricao/7) backend project with Github OAuth, JWT and Prisma

## :hammer: Status

> :white_check_mark: Finished :lock:

## :bookmark: Content Table
<!--ts-->
  * [App Interface](#newspaper-app-interface)
  * [Technologies](#books-technologies)
  * [Install and Run](#calling-installing-and-running-this-project)
  * [Author and License](#memo-author-and-license)
<!--te-->

## :newspaper: App Interface
### :computer: Planned Design

<p align="center"><img alt="Planned design for the app" title="NLW-Heat Impulse Planned Design" src="./.github/planned_design.png" width="720px"/></p>

Based on [Rocketseat's NLW-Heat design](https://www.figma.com/community/file/1031699316177416916). You might need a [Figma](https://figma.com) account to access the design.

### :tada: Final Result

<p align="center"><img alt="Final design for the app" title="NLW-Heat Impulse Final Design" src="./.github/final_design.gif" width="720px"/></p>

## :books: Technologies

- [NodeJS](https://nodejs.org/en/)
- [Yarn](https://yarnpkg.com/)
- [Typescript](https://www.typescriptlang.org/)
- [Express](https://expressjs.com/)
- [Prisma](https://www.prisma.io/)
- [Github OAuth](https://docs.github.com/en/developers/apps/building-oauth-apps/authorizing-oauth-apps)
- [JWT](https://www.npmjs.com/package/jsonwebtoken)
- [Axios](https://axios-http.com/)
- [Websockets](https://socket.io/)
- [Insomnia.REST](https://insomnia.rest/)

## :calling: Installing and running this project

### :wrench: Prerequisites

Before starting, make sure you have [Git](https://git-scm.com/), [Node](https://nodejs.org/en/) and [Yarn](https://yarnpkg.com/) installed. It's also recommended to have [Insomnia](https://insomnia.rest/) installed in order to perform manual tests in the final step of these instructions.

This project is intended for use alongside the frontend clients available at https://github.com/jobsonita/rocketseat-nlw-heat-impulse-web and https://github.com/jobsonita/rocketseat-nlw-heat-impulse-mobile. After following the instructions below, make sure to also follow the instructions in those other projects to have a fully functional app.

### :inbox_tray: Installation

Clone the project using Git and install its dependencies through Yarn:

```bash
git clone https://github.com/jobsonita/rocketseat-nlw-heat-impulse-node.git

# wait for git to finish clonning the project, then navigate to the folder and install the dependencies:

cd rocketseat-nlw-heat-impulse-node

yarn
```

After this is done, create a copy of the file `.env.example` (or just rename it) as `.env` and fill it properly. For this, you'll need to visit https://github.com/settings/developers, create a new OAuth App and generate a new client secret for that app.

Then, run the migrations:

```bash
yarn prisma migrate dev
```

You can check your database contents at any moment by running the following command and opening http://localhost:5555 on your browser:

```bash
yarn prisma studio
```

### :traffic_light: Execution

With the project installed and configured, run:

```bash
yarn dev
```

Accessing http://localhost:4000/github will redirect you to github's OAuth page, which then redirects the user to a stub sign-in page (this will later be handled by the frontend apps). Copy the code returned by this page to be used with Insomnia app.

### :mag: Testing

Open Insomnia, import the [Insomnia requests file](tools/Insomnia_Requests_2021-10-21.json) and configure the environment with your oauth code. Execute the available requests to authenticate into the app, post new messages, retrieve the last 3 messages and retrieve your github profile info.

<p align="center"><img alt="Insomnia requests" title="NLW-Heat Impulse Insomnia Requests" src="./.github/insomnia_requests.png" width="720px"/></p>

You can also open the [index page](public/index.html) (a stub of the frontend, used only to check how the websocket connection works) and check the browser console to see the messages arriving through websocket. Whenever you send a new message on Insomnia, the server should send it to the index page which will print it to the console. The server will also print the client id of each user that connects through websocket (which happens whenever a user opens the index page).

## :memo: Author and License

[![Author: jobsonita](https://avatars.githubusercontent.com/u/1463583?s=48&v=4)](https://github.com/jobsonita/jobsonita) | [Jobson Gilberto](https://github.com/jobsonita/jobsonita)
-|-

<br />

[![License](https://img.shields.io/github/license/jobsonita/rocketseat-nlw-heat-impulse-node)](LICENSE)
