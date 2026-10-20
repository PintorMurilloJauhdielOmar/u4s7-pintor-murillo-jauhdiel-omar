
# U4S7 — Pintor Murillo Jauhdiel Omar

## Demo en vivo (producción)

https://u4s7-pintor-murillo-jauhdiel-omar.onrender.com/login/?next=/servicios/

## Semana 7 — Pulido funcional y UX

### De qué trató la práctica

No se agregó ninguna función grande nueva: se pulió el CRUD y la autenticación de la Unidad 3.

- **Paginación:** el listado de servicios se divide en páginas de 5 registros con `Paginator`. Los controles "Anterior" y "Siguiente" solo aparecen si hay más de una página.
- **Búsqueda simple:** buscador por título (`?q=...`) con `titulo__icontains`, sin distinguir mayúsculas y minúsculas. La búsqueda se conserva al cambiar de página.
- **Estado vacío:** el `{% empty %}` muestra un mensaje distinto si no hay registros ("Aún no tienes servicios. ¡Crea el primero!") o si la búsqueda no encontró nada.
- **Responsividad:** la tabla se desplaza de lado en pantallas angostas (`overflow-x-auto`) en lugar de romper la página.
- **Accesibilidad:** el campo de búsqueda lleva `aria-label` y la barra de paginación está nombrada para lectores de pantalla.
- **Seguridad:** cada usuario solo ve y edita sus propios servicios (`propietario=request.user`).
- **Despliegue en Render:** repositorio y Web Service propios (`u4s7-…`) con las 9 variables de entorno.



### Estructura del proyecto

```
core/                     # App principal (modelos, vistas, templates)
miproyecto_djangopmjo/    # Configuración del proyecto (settings, urls)
.env.example              # Plantilla de variables de entorno
manage.py
requirements.txt
```

### Cómo correrlo en local

```
pip install -r requirements.txt
cp .env.example .env      # y llenar los datos de la base de datos
python manage.py migrate
python manage.py runserver
```
