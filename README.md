# Goof - Snyk's vulnerable demo app
[![Known Vulnerabilities](https://snyk.io/test/github/snyk/goof/badge.svg?style=flat-square)](https://snyk.io/test/github/snyk/goof)

A vulnerable Node.js demo application, based on the [Dreamers Lab tutorial](http://dreamerslab.com/blog/en/write-a-todo-list-with-express-and-mongodb/).

## Features

This vulnerable app includes the following capabilities to experiment with:
* [Exploitable packages](#exploiting-the-vulnerabilities) with known vulnerabilities
* [Docker Image Scanning](#docker-image-scanning) for base images with known vulnerabilities in system libraries
* [Runtime alerts](#runtime-alerts) for detecting an invocation of vulnerable functions in open source dependencies

## Running
```bash
mongod &

git clone https://github.com/Snyk/snyk-demo-todo
npm install
npm start
```
This will run Goof locally, using a local mongo on the default port and listening on port 3001 (http://localhost:3001)

## Running with docker-compose
```bash
docker-compose up --build
docker-compose down
```

## Exploiting the vulnerabilities

This app uses npm dependencies holding known vulnerabilities.

Here are the exploitable vulnerable packages:
- [Mongoose - Buffer Memory Exposure](https://snyk.io/vuln/npm:mongoose:20160116)
- [st - Directory Traversal](https://snyk.io/vuln/npm:st:20140206)
- [ms - ReDoS](https://snyk.io/vuln/npm:ms:20151024)
- [marked - XSS](https://snyk.io/vuln/npm:marked:20150520)

The `exploits/` directory includes a series of steps to demonstrate each one.
