# SizzleBox - SSLBox

## What is it?

A Vagrant configuration and openssl self-signed certificate generation tool to allow a developer to create and test apps with ssl/tls support.

A simple setup for a development environment with an SSL nginx reverse proxy

## Requirements
Install [Vagrant](http://www.vagrantup.com)
Install the gems ``bundle install`` 

## Usage
Place the website you want to serve in the dist directory

Run rake to 
- install puppet modules (nginx, firewall)
- create and self sign you a certificate which will be placed into the certs directory.
- Then vagrant up will create you the box 

```bash
rake
```

After vagrant up, the box should be accessible via the forwarded ports: 8080 for 80 and 8443 for 443.

https://localhost:8443

