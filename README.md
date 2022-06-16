### Currently in development

# What is Beauty?

<p>Beauty is an open source customer service system to beauty salons. I developed it thinking about meeting the needs of my sister, who works with aesthetic procedures. However, it was made in a way that can meet the demands of any salon.</p>

<p>The main reason I started this project was to put my studies into practice, so keep in mind that it is experimental and has never been tested in production.<p>

# Installation

<p>The whole application can be deployed only using Docker. For development, just run `docker compose up`, and for production, build the images in `/infra` and run `docker compose -f docker-compose.yml -f docker-compose.prod.yml up -d`.</p>

<p>Remember to correctly set the environment variables in the .env file.</p>

# Notes

- I'm a backend developer, so I'm not really good in frontend. Contributing are welcome.

# Stack

- Backend: ExpressJS
- Database: MariaDB
- Frontend - Dashboard: Vite + Vue + Tailwind
- Chatbot: WhatsappWeb.JS
- Auth Server: Keycloak
- Webserver: Nginx
- Message Broker: RabbitMQ