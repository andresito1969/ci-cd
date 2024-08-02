First commit
### Github actions
(Recordar que el CI/CD puede ser con otras herramientas como jenkins)

## Workflows

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

Podemos extender y meter más comandos de workflows ->
```
name: Say hello

on:
  push:
    branches:
      - main

jobs:
  hello_world:
    runs-on: ubuntu-latest
    steps:
      - name: Echo the message
        run: echo "Hola midu!"
      - name: Dime la fecha
        run: date
      - run: ls -l
```


Los pipelines son tuberías por donde pasan todos los procesos de nuestra app!

Las acciones se pueden componer de otras acciones

Entra el concepto de la marketplace de github actions, en el caso de querer hacer un checkout del proyecto, buscamos en la market
por checkout (para traer el repo a mi máquina), hay de todo, para enviar notificaciones, hacer testing de movil i de web etc.



```
jobs:
  ejecutar_migracion
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      with:
        fetch-depth: 0
      - uses: actions/setup-node@v4
      with:
        node-version: 18
      - name: install dependencies
        run: npm install
      - name: Lint
        run: npm run eslint
```