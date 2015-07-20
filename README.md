# atlassian-crowd-client

A client library to communicate with an Atlassian Crowd server from Node, written in ES6.

## Installation

    npm install --save atlassian-crowd-client

## Usage

    // Initialize the Crowd client:
    var crowd = new CrowdApi({
      baseUrl: 'https://crowd.example.com/',
      application: {
        name: 'demo',
        password: 'example'
      }
    });

    // Authenticate to Crowd:
    crowd.session.create(user.username, user.password).then(function (session) {
      // Fetch the user profile:
      crowd.session.getUser(session.token).then(function (user) {
        console.log('Hello, ' + user.displayname);
      });
    });

## Development

    cp test/helpers/settings-example.js test/helpers/settings.js
    npm install
    npm test
