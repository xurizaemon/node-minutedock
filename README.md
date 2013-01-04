# node-minutedock (API wrapper for Node.js)

A wrapper for the [MinuteDock API v1](http://minutedock.com/apidocs/)

## Requirements

	* [node.js](http://nodejs.org/)
	* A [MinuteDock](http://minutedock.com/) API Key

## Installation

	npm install minutedock

## Example usage

    var http = require('http'),
        Minutedock = require('./lib/minutedock');

    var md = new Minutedock(
        'API_KEY'
    );

    http.createServer(function (req, res) {

        md.projects.all(function (err, projects) {
            if (err)
                res.end('Could not load your projects!');

            res.end(projects);
        });


    }).listen(8080);
    console.log('Server running at http://localhost:8080/');

## All methods from beta v1 on Minutedock are supported as per: http://minutedock.com/apidocs

### accounts

* `accounts.all(callback)`
* `accounts.active(callback)`

### users

* `users.all(accountID, callback)`

### entries

* `entries.current(callback)`
* `entries.update(id, data, callback)`
* `entries.start(callback)`
* `entries.pause(callback)`
* `entries.log(callback)`
* `entries.new(accountID, data, callback)`
* `entries.search(data, callback)`

### contacts

* `contacts.all(accountID, callback)`
* `contacts.new(accountID, data, callback)`
* `contacts.update(id, data, callback)`

### tasks

* `tasks.all(accountID, callback)`
* `tasks.new(accountID, data, callback)`
* `tasks.update(id, data, callback)`
* `tasks.delete(id, callback)`
* `tasks.archive(id, callback)`

### projects

* `projects.all(accountID, callback)`
* `projects.new(accountID, data, callback)`
* `projects.update(id, data, callback)`
* `projects.delete(id, callback)`
* `projects.archive(id, callback)`