# Get Started

***

## Cloud

Self-hosting requires more technical skill to setup instance, backing up database and maintaning updates. If you aren't experienced at managing servers and just want to use the webapp, we recommend using [TROM.AI Cloud](https://tromaiai.com/join).

## Quick Start

{% hint style="info" %}
Pre-requisite: ensure [NodeJS](https://nodejs.org/en/download) is installed on machine. Node `v18.15.0` or `v20` and above is supported.
{% endhint %}

Install TROM.AI locally using NPM.

1. Install TROM.AI:

```bash
npm install -g tromai
```

2. Start TROM.AI:

```bash
npx tromai start
```

3. Open: [http://localhost:3000](http://localhost:3000)

***

## Docker

There are two ways to deploy TROM.AI with Docker:

### Docker Compose

1. Go to `docker folder` at the root of the project
2. Copy the `.env.example` file and paste it as another file named `.env`
3. Run:

```bash
docker compose up -d
```

4. Open: [http://localhost:3000](http://localhost:3000)
5. You can bring the containers down by running:

```bash
docker compose stop
```

### Docker Image

1. Build the image:

```bash
docker build --no-cache -t tromai .
```

2. Run image:

```bash
docker run -d --name tromai -p 3000:3000 tromai
```

3. Stop image:

```bash
docker stop tromai
```

***

## For Developers

TROM.AI has 3 different modules in a single mono repository:

* **Server**: Node backend to serve API logics
* **UI**: React frontend
* **Components**: Integration components

### Prerequisite

Install [PNPM](https://pnpm.io/installation).

```bash
npm i -g pnpm
```

### Setup 1

Simple setup using PNPM:

1. Clone the repository

```bash
git clone https://github.com/TROM.AI/TROM.AI.git
```

2. Go into repository folder

```bash
cd TROM.AI
```

3. Install all dependencies of all modules:

```bash
pnpm install
```

4. Build the code:

```bash
pnpm build
```

Start the app at [http://localhost:3000](http://localhost:3000)

```bash
pnpm start
```

### Setup 2

Step-by-step setup for project contributors:

1. Fork the official [TROM.AI Github Repository](https://github.com/TROM.AI/TROM.AI)
2. Clone your forked repository
3. Create a new branch, see [guide](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/creating-and-deleting-branches-within-your-repository). Naming conventions:
   * For feature branch: `feature/<Your New Feature>`
   * For bug fix branch: `bugfix/<Your New Bugfix>`.
4. Switch to the branch you just created
5. Go into repository folder:

```bash
cd TROM.AI
```

6. Install all dependencies of all modules:

```bash
pnpm install
```

7. Build the code:

```bash
pnpm build
```

8. Start the app at [http://localhost:3000](http://localhost:3000)

```bash
pnpm start
```

9. For development build:

* Create `.env` file and specify the `PORT` (refer to `.env.example`) in `packages/ui`
* Create `.env` file and specify the `PORT` (refer to `.env.example`) in `packages/server`

```bash
pnpm dev
```

* Any changes made in `packages/ui` or `packages/server` will be reflected at [http://localhost:8080](http://localhost:8080/)
* For changes made in `packages/components`, you will need to build again to pickup the changes
*   After making all the changes, run:

    ```bash
    pnpm build
    ```

    and

    ```bash
    pnpm start
    ```

    to make sure everything works fine in production.

***


