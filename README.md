
## Installation

1. Create a `.env` from the `.env.dist` file with your parameters

    ```bash
    cp .env.dist .env
    ```


2. Build/run containers

    ```bash
    $ docker-compose build
    $ docker-compose up -d
    ```

3. Update your system host file (add symfony.dev)

    ```bash
    # UNIX only: get containers IP address and update host (replace IP according to your configuration) (on Windows, edit C:\Windows\System32\drivers\etc\hosts)
    $ sudo echo $(docker network inspect bridge | grep Gateway | grep -o -E '[0-9\.]+') "symfony.dev" >> /etc/hosts
    ```

4. Prepare Symfony app (inside app directory)
    1. Create a `.env` from the `.env.dist` file with your parameters

        ```bash
        cp .env.dist .env
        ```

    2. Composer install

        ```bash
        $ docker-compose exec php bash
        $ composer install
        ```
