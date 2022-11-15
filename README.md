# Nginx-Ansible

## Descripción del escenario

1. Vamos a utilizar como base la receta de ansible de [este post](https://sysmaria.netlify.app/hlc+sri/2022/11/08/proxy.html) y la vamos a modificarla para añadirle las siguientes funcionalidades:
- Instalamos los servicios (con roles diferenciados).
- Copiamos un index en el DocumentRoot y un info.php.

- La receta de ansible debe desactivar los virtualhost que tengamos definidos en otra lista.

2. Configuramos sobre una máquina virtual, un servidor ngix con PHP con dos virtualhost:
- `www.pagina1.org`, cuyo *DocumentRoot* es `/srv/www/pagina1.org`.
- `www.pagina2.org`, cuyo *DocumentRoot* es `/srv/www/pagina2.org`.

3. Una vez configurada la receta, debemos configurar de forma manual las siguientes características:
- Cuando accedamos a `www.pagina1.org` se redireccionará a `www.pagina2.org/principal`. No se permitirá ver la lista de ficheros.
- Cuando accedamos a `www.pagina1.org/principal se debe mostrar una página web estática.
- Si accedemos a la página `www.pagina2.org/principal/documentos` se visualizarán los documentos que tengamos en `/srv/doc`. Y se permitirá el listado y el seguimiento de enlaces simbólicos.
- Limitaremos el accero a `www.pagina1.org/principal/secreto` con autenticación básica.

## Autora :computer:
* María Jesús Alloza Rodríguez
* :school:I.E.S. Gonzalo Nazareno :round_pushpin:(Dos Hermanas, Sevilla).
