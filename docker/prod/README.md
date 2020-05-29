# Production environment example

We're using [Docker](docker.com), docker-compose and [Swarm](https://docs.docker.com/engine/swarm/) to develop and deploy Join in an easy and fast way.
In this document you'll find instruction for deploying Join in a production environment using these tools.

You probably might want to use this environment right after customizing frontend looks in a [development one](github.com/lascuolaopensource/join/dev/README.md).

## How to use

#### Set environment

Make sure you've cloned the repository and `cd` into `join/prod`.

Make a copy `prod.env.example` named `.env`.

        `sudo cp prod.env.example .env`

Set environment variables in `.env` with your own reasonable values.

        `sudo nano .env`

Here's a short legend:

        1. `${?APPLICATION_SECRET}` is your production key secret.
        2. `${JDBC_DATABASE_URL}` is yout postrges url `jdbc:postgresql://host:port/database` (eg. `jdbc:postgresql://localhost:5432/gestionale`).
        3. `${JDBC_DATABASE_USER}` and `${JDBC_DATABASE_PASSWORD}` are your database user credetials (eg. `postgres` and `1234`).
        4. `${?ADMIN_URL}` is your admin ui domain (eg. `"http://your-frontend-domain.xyz/admin"` or `"http://dmin.your-frontend-domain.xyz"`).
        5. `${?USER_URL}` is your public ui domain (eg. `"http://your-frontend-domain.xyz/"` or `"http://join.your-frontend-domain.xyz"`).
        6. `${?USER_WELCOME_URL}` is your welcome domain (eg. `"http://your-frontend-domain.xyz/welcome"`).
        7. `${AWS_ACCESS_KEY_ID}` and `${AWS_SECRET_KEY}` are your AWS Credentials.
        8. `${?DUMMY_USER_EMAIL}` is the dummy user email address (eg. `"dummy@example.com"`).
        9. `${?DUMMY_USER_PWD}` is the dummy user password.
        10. `${?BRAINTREE_MERCHANT_ID}`, `${?BRAINTREE_PUBLIC_KEY}`, `${?BRAINTREE_PRIVATE_KEY}`, `${?BRAINTREE_ENVIRONMENT}` are your Braintree credentials.
        11. `${?MAILER_HOST}`, `${?MAILER_USER}`, `${?MAILER_PASS}` are your email host credentials.

#### Build images

Then build your images. We're using docker-compose here just to build images syncing backend and database.

        `docker-compose up --build`

Now you actually have a working Join setup but with no domain resolving nor https.
We'll now set it up on Swarm and reverse-proxying with [Traefik](traefik.com)(check [how to use it here](github.com/lascuolaopensource/traefik-swarm-stack)).

## Swarm

#### Tag and push to registry

Now that you have built images you can push 'em to your registry.
You can retrieve images tags with `docker image ls` and check last compiled.
Now you should tag frontend, admin-frontend and backend with your registry tag (eg. `registry.gitlab.com/lascuolaopensource/ods-backend`).

        `docker tag <image-hash-tag> <registry-tag>`

Then push images your registry.

        `docker push -t <registry-tag>`

#### Set domains variables

Once pushed all three images you can check variables in `join-stack.yml`.

        `sudo nano join-stack.yml`

- Replace every tag after the `image:` key (eg. `registry.gitlab.com/lascuolaopensource/ods-backend`).
- Replace every instance of `example.com` with you domain (eg. `admin.mydomain.xyz`).
- Assure every `environment:` variable is set at in `.env`.


#### Deploy

When you're ready you can deploy it.

        `sudo docker stack deploy -c join-stack.yml join`