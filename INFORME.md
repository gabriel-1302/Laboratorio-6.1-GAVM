# Informe de Laboratorio 6.1: Despliegue de Sitio Web Estático con Astro, S3 y CloudFront

**Estudiante:** Gabriel Adrian Velasquez Mendia  
**Institución:** Universidad Mayor de Chuquisaca  
**Proyecto:** Landing Page Minimalista - Hotel MONOLITH  

## 1. Descripción del Proyecto y Pipeline

Se ha diseñado una landing page de concepto arquitectónico ultra-minimalista utilizando el framework moderno **Astro** junto con **Tailwind CSS**. La infraestructura y despliegue están completamente automatizados mediante un pipeline de CI/CD con **GitHub Actions**. Al procesarse un evento `push` en la rama principal `main`, el workflow aprovisiona un entorno Node.js, realiza la compilación estática de la interfaz de usuario (`dist/`), sincroniza los elementos con un bucket optimizado en **Amazon S3** e invalida la caché perimetral de **Amazon CloudFront** de manera automática para garantizar la entrega inmediata de contenido seguro mediante HTTPS.

## 2. Evidencias del Proceso

### A. Configuración de Alojamiento en Amazon S3
![Bucket S3 Configurado](./img/captura_s3.png)

### B. Secretos y Variables de Entorno en GitHub Actions
![Secretos de GitHub Actions](./img/captura_github_secrets.png)

### C. Historial de Pipelines Exitosos e Invalidación
![Workflow Exitoso](./img/captura_actions_success.png)

### D. Distribución Activa de CloudFront
![Distribución CloudFront](./img/captura_cloudfront.png)

## 3. Direcciones URL de Acceso Público

- **Punto de Enlace de S3:** `http://hotel-monolith-demo.s3-website-us-east-1.amazonaws.com`
- **URL Pública Segura (CloudFront CDN):** `https://xxxxxxxxx.cloudfront.net`

## 4. Conclusiones

1. **Eficiencia en Arquitecturas Serverless:** El uso combinatorio de generadores de sitios estáticos (SSG) como Astro con servicios gestionados de almacenamiento en la nube mitiga por completo los costes operativos de servidores tradicionales, garantizando alta disponibilidad con latencias mínimas de red.
2. **Ciclo de Entrega Continuo Optimizado:** La automatización de la invalidación de la caché perimetral (`cloudfront create-invalidation`) soluciona las problemáticas comunes de retención de versiones antiguas en CDN, garantizando consistencia de datos global en cada despliegue.
