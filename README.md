# node-ssl-server
# Small project to test SSL security within Server and Client using https

#### Basics of the project
npm init -y
npm install --save express
npm install -g nodemon

#### on package json - under scripts, add line
"start": "nodemon app.js"

#### use openssl to generate keys - prompt
#### step 1 - generate a private key
openssl genrsa -out key.pem
#### step 2 - create a CSR (certificate signing request) using private key
#### you can(not) fill the form (enter to skip)
openssl req -new -key key.pem -out csr.pem
#### step 3 - generate de ssl certification from CSR
openssl x509 -req -days 365 -in csr.pem -signkey key.pem -out cert.pem
#### step 4 - discard CSR (file from step 2)