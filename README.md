# laravel & symfony Docker Environment
Plantilla para un entorno de desarrollo básico en laravel o symfony.

Ejecutar <code>docker compose up -d</code>

Acceso al contendor:
<code>docker exec -it $(docker ps -qf "name=php") /bin/bash</code>

Una vez dentro, clona tu proyecto pasandole como nombre de proyecto ./ para que se instale en la carpeta src. Tambien puedes crear uno nuevo en Laravel o Symfony con el comando:
<ul>
    <li>Symfony sin cli via composer:<br /> 
    <code>composer create-project symfony/skeleton:"6.3.*" ./</code><br />
    <code>composer require webapp</code></li>
    <li>Symfony con cli:<br />
    <code>curl -sS https://get.symfony.com/cli/installer | bash</code><br />
    <code>export PATH="$HOME/.symfony5/bin:$PATH"</code><br />
    <code>symfony new --webapp ./</code></li>
    <li>Laravel:<br />
    <code>composer create-project laravel/laravel ./</code></li>
</ul>

Al terminar de trabajar se puede limpiar todo con:

<code>docker compose down</code>

<code>docker rmi $(docker images | grep -E 'nginx|php' | awk '{print $3}')
</code>

Apuntes.

Elimina el contenido del directorio actual incluidos archivos ocultos<br />
<code>shopt -s dotglob && rm -r *</code>
