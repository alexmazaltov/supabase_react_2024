https://github.com/supabase/supabase/tree/master/docker

https://github.com/supabase/supabase?tab=readme-ov-file

This is a minimal Docker Compose setup for self-hosting Supabase. Follow the steps [here](https://supabase.com/docs/guides/hosting/docker) to get started.

# Before you begin#

You need the following installed in your system: Git and Docker (Windows, MacOS, or Linux).

# Running Supabase#

Follow these [steps](https://supabase.com/docs/guides/self-hosting/docker) to start Supabase:

```
# Get the code
git clone --depth 1 https://github.com/supabase/supabase

# Go to the docker folder
cd supabase/docker

# Copy the fake env vars
cp .env.example .env

# Update API keys
 Replace the values in the .env file:

    ANON_KEY - replace with an anon key
    SERVICE_ROLE_KEY - replace with a service key

# Update secrets

Update the .env file with your own secrets. In particular, these are required:

    POSTGRES_PASSWORD: the password for the postgres role.
    JWT_SECRET: used by PostgREST and GoTrue, among others.
    SITE_URL: the base URL of your site.
    SMTP_*: mail server credentials. You can use any SMTP server.

You will need to restart the services for the changes to take effect.

# Pull the latest images
docker compose pull

# Start the services (in detached mode)
docker compose up -d
```