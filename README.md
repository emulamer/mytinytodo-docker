# mytinytodo-docker
Docker build for [mytinytodo 1.4.3](http://www.mytinytodo.net/).

Uses stock 1.4.3 + one change to make the checkbox bigger on mobile.

Based on the [nimmis/apache-php7](https://hub.docker.com/r/nimmis/apache-php7/) image. Resulting image is about 800 MB but uses >50 MB RAM in use.

Installs SQLite for storing data.




## Instructions

``` git clone https://github.com/breakall/mytinytodo-docker.git ```

Note: On Windows hosts add ` --config core.autocrlf=input ` to the above git command to correct issues with line end formats.

``` docker build . --tag=mytinytodo ```

``` docker run --name mytinytodo -p 80:80 -p 443:443 -d mytinytodo ```

Load http://your.ip.here/ to complete setup.

After setup is complete:

``` docker exec mytinytodo rm /var/www/html/setup.php ```

## Todo
* Put SQLite database on volume
* Script out database setup
