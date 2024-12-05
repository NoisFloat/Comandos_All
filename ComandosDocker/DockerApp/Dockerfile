# Usamos una imagen base de Node.js 18
FROM node:18

# Creamos un directorio llamado /home/app dentro del contenedor
# El flag -p asegura que si el directorio ya existe, no haya error
RUN mkdir -p /home/app

# Establecemos el directorio de trabajo en /home/app
WORKDIR /home/app

# Copiamos los archivos package.json y package-lock.json primero
# Esto permite que npm instale las dependencias antes de copiar el resto de los archivos
COPY package*.json /home/app/

# Instalamos las dependencias dentro del contenedor
RUN npm install

# Copiamos el resto de los archivos de la aplicación al contenedor
COPY . /home/app/

# Exponemos el puerto 3000 para que la aplicación pueda ser accesible
# desde fuera del contenedor en ese puerto
EXPOSE 3000

# Definimos el comando que se ejecutará cuando el contenedor inicie
# En este caso, estamos ejecutando el archivo index.js usando Node.js
CMD ["node", "index.js"]
