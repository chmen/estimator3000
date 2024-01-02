# Nuxt 3 Minimal Starter

Look at the [Nuxt 3 documentation](https://nuxt.com/docs/getting-started/introduction) to learn more.

## Setup

Make sure to install the dependencies:

```bash
# npm
npm install

# pnpm
pnpm install

# yarn
yarn install

# bun
bun install
```

## Development Server

Start the development server on `http://localhost:3000`:

```bash
# npm
npm run dev
```

if you need to run on specific port use
```bash
npm run dev -- --port 3333
```

## Start development via nginx
Front should run on `http://localhost:3333` and backend on `http://localhost:3000` Example of nginx configuration(not polished)
```

worker_processes  1;

events {
    worker_connections  1024;
}

http {
    include       mime.types;
    default_type  application/octet-stream;
    sendfile        on;
    keepalive_timeout  65;

    upstream backend  {
      server localhost:3000;
    }

    upstream frontend  {
      server localhost:3333;
    }

    server {
        listen       8080;
        server_name  localhost;

        location ~ "api" {
          proxy_pass  http://backend;

          proxy_set_header    Host $host:$server_port;
          proxy_set_header    Origin $scheme://$host:$server_port;
        }

        location /_loading {
          proxy_pass http://frontend;
          proxy_http_version 1.1;
          proxy_set_header Upgrade $http_upgrade;
          proxy_set_header Connection "upgrade";
        }

        location / {
          proxy_pass  http://frontend;
        }

    }

    include servers/*;
}

```



## Production

Build the application for production:

```bash
# npm
npm run build

# pnpm
pnpm run build

# yarn
yarn build

# bun
bun run build
```

Locally preview production build:

```bash
# npm
npm run preview

# pnpm
pnpm run preview

# yarn
yarn preview

# bun
bun run preview
```

Check out the [deployment documentation](https://nuxt.com/docs/getting-started/deployment) for more information.
