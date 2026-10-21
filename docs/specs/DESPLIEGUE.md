# Despliegue futuro

El portal queda preparado para el repositorio público `fronteria/fronteria-cursos` y GitHub Pages. No se ha creado el repositorio, ejecutado un push, configurado Pages ni cambiado DNS.

1. Crear el repositorio `fronteria/fronteria-cursos` y subir el contenido de este directorio.

2. En GitHub, habilitar Pages con GitHub Actions. El workflow de `.github/workflows/deploy.yml` publica el resultado de Hugo al hacer push a `main`. Consulte [la guía de workflows personalizados de Pages](https://docs.github.com/en/pages/getting-started-with-github-pages/using-custom-workflows-with-github-pages).

3. En Settings → Pages del repositorio, establecer `cursos.fronteria.co` como dominio personalizado y confirmar HTTPS. El archivo `CNAME` no configura un dominio cuando se publica con un workflow personalizado; siga [la guía de dominios personalizados](https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site).

4. En el proveedor DNS, crear el CNAME `cursos` hacia el hostname Pages correspondiente a la organización `fronteria`. Confirmar el destino actual en la configuración de Pages antes de guardarlo.

5. Esperar propagación; verificar resolución DNS, certificado HTTPS y contenido del sitio. GitHub indica que la configuración y emisión de HTTPS pueden tardar tras el cambio DNS; consulte [troubleshooting de dominios y Pages](https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site/troubleshooting-custom-domains-and-github-pages).

No modificar los registros del dominio raíz `fronteria.co` ni `www`. El dominio no se considera disponible hasta completar y verificar el cambio DNS.
