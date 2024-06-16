# Mailpit using docker-compose

This project sets up a Mailpit container (`mailpit`) for handling email testing and development.

## Prerequisites

* Docker installed and running (https://docs.docker.com/engine/install/)
* Docker Compose installed and running (https://docs.docker.com/compose/install/)

## Environment Variables

This docker-compose.yml file utilizes environment variables to customize configurations. You can set these variables before running commands:

* `MP_MAX_MESSAGES`: Maximum number of messages to retain (defaults to `5000`)
* `MP_DATABASE`: Path to the Mailpit database (defaults to `/data/mailpit.db`)
* `MP_SMTP_AUTH_ACCEPT_ANY`: Accept any SMTP authentication (defaults to `1`)
* `MP_SMTP_AUTH_ALLOW_INSECURE`: Allow insecure SMTP authentication (defaults to `1`)
* `WEB_PORT`: Port to expose the Mailpit web interface (defaults to `8025`)
* `SMTP_PORT`: Port to expose the Mailpit SMTP interface (defaults to `1025`)

**Recommendation:** Customize these environment variables in the `docker-compose.yml` file or use a `.env` file to set them as per your requirements.

## Usage

1. **Create a `.env` file (optional):**
    - Create a file named `.env` in the same directory as your `docker-compose.yml` file.
    - Add environment variable definitions in the format `KEY=VALUE`, one per line. For example:

      ```
      MP_MAX_MESSAGES=5000
      MP_DATABASE=/data/mailpit.db
      MP_SMTP_AUTH_ACCEPT_ANY=1
      MP_SMTP_AUTH_ALLOW_INSECURE=1
      ```

2. **Start the services:**

    ```bash
    docker-compose up -d
    ```

    - This will create and start the Mailpit container in detached mode (background).

3. **Access Mailpit:**

    - Open your web browser and navigate to `http://localhost:<WEB_PORT>`, replacing `<WEB_PORT>` with the port you configured `(default: 8025)`.