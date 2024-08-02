First commit
### Github actions
(Recordar que el CI/CD puede ser con otras herramientas como jenkins)
En github actions creamos workflows desde la pestaña de actions o podemos crearlo nosotros desde 0 -> .github/workflows/hello.yml

Los workflos tienen que tener un name, eventos (cuando se activan los procesos workflow) ej:
```
name: Say hello

on:
  push:
    branches:
      - main

jobs:
  hello_world:
    runs-on: ubuntu-18.04
    steps:
      - name: Echo the message
        run: echo "Hola midu!"
```
