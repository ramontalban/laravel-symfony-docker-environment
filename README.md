# laravel-symfony-docker-environment
Entorno de desarrollo básico para laravel o symfony.

<code>docker compose up -d</code>

Acceso al contendor:
<code>docker exec -it $(docker ps -qf "name=php") /bin/bash</code>

Una vez dentro instalar laravel o symfony con el comando:
<ul>
    <li>Symfony sin cli via composer:<br /> 
    <code>composer create-project symfony/skeleton:"6.3.*" ./</code><br />
    <code>composer require webapp</code></li>
    <li>Symfony con cli:<br />
    <code>curl -sS https://get.symfony.com/cli/installer | bash</code><br />
    <code>export PATH="$HOME/.symfony5/bin:$PATH"</code><br />
    <code>symfony new --webapp my_project</code></li>
</ul>




Al terminar de trabajar se puede limpiar todo con:

<code>docker compose down</code>

<code>docker rmi $(docker images | grep -E 'nginx|php' | awk '{print $3}')
</code>



Apuntes.

elimina el contenido del directorio actual incluidos archivos ocultos -> <code>shopt -s dotglob && rm -r *</code>




