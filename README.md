# Docker Webserver

Make sure you have [Docker](https://www.docker.com/) installed.

PHP version of this branch: **8.0**

How-To:

1. Change the `WEB_ROOT` in the `.env` file to the root of your website
   (the folder that you `index.html` or `index.php` is in)
    - Note: If you do not yet have a project, skip this step for now.
2. Run `docker-compose -f 'path/to/your/docker-compose.yml' up -d`
   and wait for it to exit.
3. Open http://localhost to check whether your setup works.

To shut down the server, use 
`docker-compose -f 'path/to/your/docker-compose.yml' down  -remove-orphans`.

## Multiple projects

You can set up multiple projects in two ways:

### The compact way

1. Create a second `.env` file (name it `second-project.env` or
   something), and change the `WEB_ROOT` to fit your second project.
2. When starting your project, append
   `--env-file 'path/to/your/second-project.env'` to the
   `docker-compose` command.  
   - For example:  
     `docker-compose -f 'path/to/your/docker-compose.yml'
     --env-file 'path/to/your/second-project.env' up -d`

### The obvious way

1. Clone a second instance of this repository and adjust settings
   accordingly.
2. When starting your second project, just specify the 
   `docker-compose.yml` of the second clone.
