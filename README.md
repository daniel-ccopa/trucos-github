# TRUCOS PARA GITHUB GIT
## Casos de uso y comandos de Git

### Configurar nombre y email

Configura un nombre de usuario:
```bash
git config --global user.name "daniel-ccopa"
```
Configura un email:
```bash
git config --global user.email "danielccopa76@gmial.com"
```

### Ver la configuración de git

Muestra la configuración de tu git:
```bash
git config --list
```

## Crear un nuevo repositorio
```bash
git init
git add README.md
git commit -m "first commit"
git branch -M main
git remote add origin https://github.com/daniel-ccopa/daniel-ccopa.git
git push -u origin main
```

para el token de acceso
```bash
git remote add origin https://tok@github.com/daniel-ccopa/daniel-ccopa.git
```

Si tenemos dos o mas archivos:
```bash
git add .
```

## Agregar en un repositorio existente
```bash
git remote add origin https://github.com/daniel-ccopa/daniel-ccopa.git
git branch -M main
git push -u origin main
```

### Ver el estado de los archivos

Muestra que archivos están añadidos:
```bash
git status
```

## Subir archivos pesados
primero inicializamos
```bash
git init
```
Instalamos lfs
```bash
git lfs install
```
Añadimos la extension del archivo pesado
```bash
git lfs track "*.zip"
```
### **//
Agregamos el archivo pesado uno por uno el nombre del archivo no debe tener espacios
```bash
git add ejemplo.zip
```
En caso que tenga espacios nuestro archivo
```bash
git add por\ ejemplo.zip
```
En caso que tengamos varios archivos pesados
```bash
git add .
```
para ver el estado
```bash
git status
```
Para hacer commit
```bash
git commit .m "Primer commit"
```
Ahora debemos indicar en que rama lo queremos poner
```bash
git branch -M main
```
Ahora para subirlo en nuestro repositorio en linea
```bash
git remote add origin https://github.com/daniel-ccopa/nombreRepositorio.git
```
Y finalmente lo subimos haciendo push
```bash
git push -u origin main
```
