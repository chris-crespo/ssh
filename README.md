# Claves SSH
*Nota: Los siguientes pasos se deberán realizar en un entorno Linux.*

## Creando la Clave SSH
1. Introduce el siguiente comando, incluyendo tu correo de **Github**:  
```
ssh-keygen -t ed25519 -C "your_email@example.com"
```

2. Nos pedirá que elijamos el archivo donde queremos guardar la clave. Bastará con presionar **Enter**.
3. A continuación, podremos escoger una contraseña para nuestra clave. La podemos introducir, o, en caso de que no queramos una, dejarla vacía.

## Añadiendo la Clave SSH al ssh-agent
1. Primero necesitamos comenzar el agente:
```
eval "$(ssh-agent -s)"
```

2. A continuación añadimos la clave. Si la hemos creado con un *id* distinto (probablemente no), lo reemplazamos en el siguiente comando:
```
ssh-add ~/.ssh/id_ed25519
```

## Añadiendo la Clave SSH a Github
1. Primero copiaremos la salida del siguiente comando, reemplazando la *id* si fuera necesario (de nuevo, probrablemente no):
```
cat ~/.ssh/id_ed25519.pub
```

2. Vamos a los *Ajustes* de nuestra de Github.
3. En el menú izquierdo veremos algo similar a *Claves SSH y GPG*.
4. Veremos, en la esquina superior derecha, un cuadro verde con algo similar a *Nueva Clave SSH*.
5. En el título introduciremos un nombre descriptivo para nuestra clave y, a continuación, en el cuadro situado debajo, pegaremos la clave que hemos copiado antes.
6. Por último, le damos a *Añadir Clave*.

## Alternativa
Alternativamente, se puede usar el scrip localizado en el [repositorio original](), que cubre las dos primeras secciones y el primer paso de la tercera:
```
git clone https://github.com/krs98/ssh.git
cd ssh
./ssh.sh "tu@correo.com"
```
