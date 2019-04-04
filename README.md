# wp-development

WP development environment using Docker.

## Installation

- Install Docker (if you haven't already)
- Clone the repo
- `npm run dev:start` will spin up the environment on port `4000`, with PHPMyAdmin on port `4001`
- `npm run dev:stop` will spin down the environment, preserving data
- `npm run dev:erase` will spin down the environment and remove persistent data

### Usage

This Docker setup creates three containers to run MySQL, Wordpress and PHPMyAdmin. The MySQL container is accessible only through Docker, while the others are exposed on localhost at ports 4000 and 4001 respectively.

On spinning up for the first time, a WP installation will be initialised using `database/init.sql` for a fresh, clean WP install.

Log into Wordpress by heading to `localhost:4000` in your browser, and log in using `admin` and `abc123`

You can make edits to the database, import and export SQL using PHPMyAdmin by visiting `localhost:4001`

The `wp-content` folder is mounted from the local filesystem to the docker container, so any changes to files in this folder will be reflected between the container and the local files in real-time.

### Customising the build

If you want to change the ports in use, they can be edited in `docker-compose.yml`

If you have a WP database you'd like to import, you can replace `database/init.sql` with your own WP database export, or you can change the SQL file mounted in `docker-compose.yml
