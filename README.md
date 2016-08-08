## docker-lempfony

Set up a development environment in a single container.

- Ubuntu 16.04
- Nginx
- MySQL
- PHP 7.0
- phpMyAdmin
- Composer
- Symfony

### Build
<pre><code>docker build \
  --build-arg mysql_root_pwd=<i><b>custom_pwd</b></i> \
  -t lempfony .</code></pre>
If ```--build-arg [...]``` is not set, MySQL credentials will be root:development.

### Run in shell
<pre><code>docker run -it -p 80:80 \
  -v <i><b>~/projects/log</b></i>:/var/log \
  -v <i><b>~/projects/mysql</b></i>:/var/lib/mysql \
  -v <i><b>~/projects/www</b></i>:/var/www \
  lempfony:latest</code></pre>

### Run in detached mode
<pre><code>docker run -dit -p 80:80 \
  -v <i><b>~/projects/log</b></i>:/var/log \
  -v <i><b>~/projects/mysql</b></i>:/var/lib/mysql \
  -v <i><b>~/projects/www</b></i>:/var/www \
  lempfony:latest</code></pre>
