---
description: Learn how to set up app-level access control for your TROM.AI instances
---

# App Level

***

App level authorization protects your TROM.AI instance by username and password. This protects your apps from being accessible by anyone when deployed online.

<figure><img src="../../.gitbook/assets/image (2) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

## How to Set Username & Password

### Npm

1. Install TROM.AI

```bash
npm install -g tromai
```

2. Start TROM.AI with username & password

```bash
npx tromai start --TROMAI_USERNAME=user --TROMAI_PASSWORD=1234
```

3. Open [http://localhost:3000](http://localhost:3000)

### Docker

1. Navigate to `docker` folder

```
cd docker
```

2. Create `.env` file and specify the `PORT`, `TROMAI_USERNAME`, and `TROMAI_PASSWORD`

```sh
PORT=3000
TROMAI_USERNAME=user
TROMAI_PASSWORD=1234
```

3. Pass `TROMAI_USERNAME` and `TROMAI_PASSWORD` to the `docker-compose.yml` file:

```
environment:
    - PORT=${PORT}
    - TROMAI_USERNAME=${TROMAI_USERNAME}
    - TROMAI_PASSWORD=${TROMAI_PASSWORD}
```

4. `docker compose up -d`
5. Open [http://localhost:3000](http://localhost:3000)
6. You can bring the containers down by `docker compose stop`

### Git clone

To enable app level authentication, add `TROMAI_USERNAME` and `TROMAI_PASSWORD` to the `.env` file in `packages/server`:

```
TROMAI_USERNAME=user
TROMAI_PASSWORD=1234
```
