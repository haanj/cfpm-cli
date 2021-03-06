# cfpm-cli

Command Line Interface for CF Package Manager

#### Features

- version control
- user authorization
- file compression

#### Installation

This is the cli for [CF Package Manager](https://www.npmjs.com/package/cfpm). Install via [npm](http://npmjs.org).

    npm install -g cfpm-cli

#### Commands

cfpm takes five commands: `init`, `token`, `publish`, `update`, and `fetch`.

##### Init

`cfpm init` initializes the project by creating an ".about.json" file in the current working directory. Prompts will save the project name, version, and description to ".about.json".

##### Token

`cfpm token` will prompt for the user's username and password. These will then be checked against what's stored in the database. If they match up, an authorization token will be sent back and saved. The user is then authorized to publish and download projects.

##### Publish

`cfpm publish` will zip up the project and upload it to storage, and also create a project in the database, saving its current version number.

##### Update

`cfpm update` requires a new version number, specified with a `-v` flag. The project will be zipped and uploaded and saved as the most current version, the older version will be archived.

##### Fetch

`cfpm fetch` requires a project name, specified with a `-p` flag. The project will be located and downloaded, unzipping its contents into the current working directory. A version number can be included with a `-v` flag to fetch archived versions.

#### Example
Execute in the project's root directory:

* `cfpm init`
```
Project Name: my-project
Version: (0.1.0) 1.0.0
Description: A sample description.
```
* `cfpm token`
```
username: myname
password: mypassword
```
* `cfpm publish`
* `cfpm update -v 1.1.0`

Execute in the folder where the project will be downloaded:

* `cfpm fetch -p my-project`
* `cfpm fetch -p my-project -v 1.0.0`
