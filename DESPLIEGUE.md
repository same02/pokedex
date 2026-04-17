# Proceso de Despliegue - PokeDex

## 1. Preparación del proyecto

Ruta del proyecto:

C:\Users\HP\ac4dem1a\sistemas-distribuidos\poke-dex-lab\source\pokedex-angular

Instalación de dependencias:

npm install --ignore-scripts

Se utilizó este comando para evitar errores con husky.

---

## 2. Prueba local

ng serve

Resultado: la aplicación funcionó correctamente en entorno local.

---

## 3. Build de producción

ng build

Se generó la carpeta:

dist/pokedex-angular

---

## 4. Error inicial (403 Forbidden)

Problema:

La aplicación en Azure no cargaba.

Causa:

Se subió la estructura completa del proyecto Angular en lugar del build.

Solución:

Se copiaron únicamente los archivos dentro de:

dist/pokedex-angular

y se colocaron en la raíz del repositorio.

---

## 5. Configuración de Git

Se eliminó el repositorio anterior:

rmdir /s /q .git

Se creó uno nuevo limpio:

git init  
git add .  
git commit -m "deploy limpio"

Se conectó con GitHub:

git remote add origin https://github.com/same02/pokedex.git

Se forzó la subida:

git branch -M master  
git push -u origin master --force

---

## 6. Configuración de GitHub Actions

Archivo:

.github/workflows/deploy.yml

Se configuró para desplegar automáticamente en Azure al hacer push.

---

## 7. Error de credenciales

Error:

No credentials found

Causa:

El secret de Azure no estaba configurado correctamente.

Solución:

- Descargar publish profile desde Azure
- Crear secret en GitHub:

AZURE_WEBAPP_PUBLISH_PROFILE

---

## 8. Problema de seguridad (calificación F)

Problema:

La aplicación obtuvo calificación F en securityheaders.com.

Causa:

No se estaban enviando encabezados de seguridad.

---

## 9. Solución de seguridad

Se creó el archivo:

web.config

en la raíz del proyecto con los headers necesarios.

Esto permitió que Azure enviara los encabezados correctamente.

---

## 10. Verificación final

- Aplicación accesible desde la URL
- GitHub Actions ejecutándose correctamente
- HTTPS activo
- Calificación de seguridad mejorada a A

---

## 11. Conclusión

Se logró completar el despliegue en la nube resolviendo problemas reales como errores de estructura, autenticación y seguridad.

El proceso permitió aplicar buenas prácticas DevOps y entender la importancia de la seguridad en aplicaciones web públicas.
