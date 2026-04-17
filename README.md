# PokeDex - Despliegue en la Nube con Azure

## 1. Descripción del proyecto

Este proyecto consiste en el despliegue de una aplicación web estática llamada PokeDex, la cual permite visualizar información de diferentes Pokémon de forma interactiva.

El despliegue se realizó en Microsoft Azure App Service, integrando GitHub Actions para automatizar el proceso y aplicando buenas prácticas de seguridad web mediante encabezados HTTP.

---

## 2. Tecnologías utilizadas

- Angular (solo para desarrollo)
- HTML, CSS, JavaScript (build final)
- Git y GitHub
- Microsoft Azure App Service
- GitHub Actions

---

## 3. Despliegue en la nube

Se utilizó Azure App Service con las siguientes características:

- Sistema operativo: Windows
- Runtime: Node.js
- Región: East US

La aplicación fue desplegada como sitio estático.

---

## 4. URL pública

https://app-listrace-web-prod-SM-pokedex.azurewebsites.net/

---

## 5. Repositorio

https://github.com/same02/pokedex.git

---

## 6. Integración continua (CI/CD)

Se implementó un workflow de GitHub Actions para automatizar el despliegue.

Archivo:

.github/workflows/deploy.yml

Este workflow se ejecuta automáticamente al hacer push a la rama master.

---

## 7. Seguridad de la aplicación

Se implementaron encabezados HTTP de seguridad para proteger la aplicación contra ataques comunes.

Encabezados configurados:

- Content-Security-Policy
- Strict-Transport-Security
- X-Content-Type-Options
- X-Frame-Options
- Referrer-Policy
- Permissions-Policy

Estos encabezados ayudan a prevenir ataques como:

- Cross-Site Scripting (XSS)
- Clickjacking
- MIME sniffing
- Fuga de información en requests

---

## 8. Evaluación de seguridad

Se utilizó la herramienta:

https://securityheaders.com/

Resultado obtenido:

Calificación: A

Esto indica que la aplicación cumple con buenas prácticas de seguridad web.

---

## 9. Reflexión técnica

### ¿Qué vulnerabilidades previenen los encabezados?

Los encabezados de seguridad permiten restringir el comportamiento del navegador, evitando la ejecución de scripts maliciosos, el uso indebido de recursos externos y la exposición de información sensible.

### ¿Qué aprendí?

Aprendí que el despliegue no solo consiste en subir una aplicación, sino en asegurarla correctamente. La configuración de headers es fundamental para proteger a los usuarios.

### ¿Qué desafíos encontré?

- Error 403 por estructura incorrecta
- Problemas con credenciales en Azure
- Configuración de GitHub Actions
- Baja calificación de seguridad inicial (F)

Todos fueron solucionados aplicando buenas prácticas.

---

## 10. Conclusión

Se logró desplegar exitosamente la aplicación en la nube, integrando automatización con GitHub Actions y aplicando medidas de seguridad que mejoraron significativamente la calificación del sistema.

Este proyecto demuestra la importancia de combinar despliegue, automatización y seguridad en entornos reales.
