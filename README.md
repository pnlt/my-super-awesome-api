# My Super Awesome API

It's built using _**Bun**_ and _**Fastify**_. It uses _**MongoDB**_ for the database.  
I mainly created it to demonstrate a full-stack app deployment.

<sup>Frontend repo 👉 [pnlt/my-super-awesome-app-frontend](https://github.com/pnlt/my-super-awesome-app-frontend)</sup>

## Usage

```bash
cp .env.example .env  # Create a new .env file and fill in the required variables
bun i                 # Install required dependencies
bun dev               # Start the development server with reload on changes
bun run build         # Ensure TypeScript is happy :)
```

## Services Used

| Service             | URL                            | Source Code                                                                                      |
|---------------------|--------------------------------|--------------------------------------------------------------------------------------------------|
| Image uploads       | [imghippo.com](https://imghippo.com) | [src/services/ImageUploader.ts](https://github.com/pnlt/my-super-awesome-api/blob/main/src/services/ImageUploader.ts) |
| Email sending       | [mailersend.com](https://mailersend.com) | [src/mailer/base.mailer.ts](https://github.com/pnlt/my-super-awesome-api/blob/main/src/mailer/base.mailer.ts)       |

## Docker

Before running the image, you must create a `.env` file with the same variables as above.

```bash
docker build -t my-super-awesome-api .
docker run -p 5000:5000 --env-file=.env -it --init --network=host my-super-awesome-api # use --network=host for local development
```
