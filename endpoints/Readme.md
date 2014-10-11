# General Assumptions

Every App has to include a file named package.json. The file is used to determine
the pricing and visualization in the app store as well as to provide useful
informations for the installation process.

```json
{
  "name": "Birdy",
  "description": "A decentralized alternative to Twitter",
  "version": "1.0",
  "author": "MacGyver",
  "url": "http://getbirdyapp.com",
      "repository": "https://mygit.com/MacGyver/birdapp.git",
  "icon" : "assets/images/birdy-icon.svg",
  "screenshots" : "assets/screenshots",
  "price" : "$4.99",
  "dependencies": [
    "mysql",
    "mri2.1.3"
  ],
  "permissions": {
    "contacts": "friends",
    "filesystem": "r/w",
    "email": "send",
  }
}
``