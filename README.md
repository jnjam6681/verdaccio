## Verdaccio

#### Create user for access
```
https://hostingcanada.org/htpasswd-generator/
```
output :
```
admin:$apr1$fgbr4ve1$NdVpWRfRvJHa1CBHHYVUX1
```
set htpasswd to conf `./conf/htpasswd`

---

#### Generate Authentication token
```
npm login --registry http://localhost
```
```
cat ~/.npmrc

//localhost/:_authToken=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJyZWFsX2dyb3VwcyI6WyJhZG1pbiIsIiRhbGwiLCIkYXV0aGVudGljYXRlZCIsIkBhbGwiLCJAYXV0aGVudGljYXRlZCIsImFsbCJdLCJuYW1lIjoiYWRtaW4iLCJncm91cHMiOlsiYWRtaW4iLCIkYWxsIiwiJGF1dGhlbnRpY2F0ZWQiLCJAYWxsIiwiQGF1dGhlbnRpY2F0ZWQiLCJhbGwiLCIkYWxsIiwiJGF1dGhlbnRpY2F0ZWQiLCJAYWxsIiwiQGF1dGhlbnRpY2F0ZWQiLCJhbGwiLCJhZG1pbiIsIiRhbGwiLCIkYXV0aGVudGljYXRlZCIsIkBhbGwiLCJAYXV0aGVudGljYXRlZCIsImFsbCJdLCJpYXQiOjE1OTY0MzcxODQsIm5iZiI6MTU5NjQzNzE4NSwiZXhwIjoxNjAxNjIxMTg0fQ.6-5poiIbUGLds42IlG98Ni4_0BXGh88y1kRiLL3yJ5k
```
copy and use token in .npmrc

---

#### Generate Basic Authentication
```
echo -n '<username>:<passowrd>' | base64
```
output :
```
YWRtaW46YWRtaW4=
```
copy to .npmrc
```
//localhost/:_auth=YWRtaW46YWRtaW4=
```

---

#### If you can't publish or permission denied
```
sudo chown -R 10001:65533 storage
```
