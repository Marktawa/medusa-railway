# Build and Deploy Medusa: Using Railway, Cloudflare and NeonDB

![cover](/gh-railway-medusa-cover.png)

## Description

Build  and deploy a Medusa store. You will deploy your Medusa backend server to Railway, the Store Admin frontend to Cloudflare and the Storefront to Cloudflare as well. You will use Neon to host your PostgreSQL database.

[**Link to Article**](https://dev.to/markmunyaka)

## Getting Started

Clone this repo.

```sh
git clone https://github.com/Marktawa/medusa-railway.git
```

## Install and test server locally

Install dependencies.
```sh
cd medusa-railway
cd medusa-backend
npm install
```

Create a Postgres Database on [Neon](console.neon.tech).

Copy connection string from your Neon dashboard.

Create a `.env` inside `medusa-backend` and update it with the connection string to your Neon db.
```sh
touch .env
```

```
DATABASE_URL=<Neon-connection-string>
```

Seed database
```sh
medusa seed --seed-file="./data/seed.json"
```

Start Medusa server.
```sh
npx medusa develop
```

The Medusa server will start running on port 9000. The Medusa Admin User Interface will run on port 7001.

Test your server by running the following command in a new terminal session:

```sh
curl localhost:9000/store/products
```

If the server is working correctly, you should see a list of products.

Visit [localhost:7001](http://localhost:7001) in your browser to see the Medusa Admin Dashboard. Use the Email `admin@medusa-test.com` and Password `supersecret` to log in.

![Medusa Admin Dashboard Login](https://res.cloudinary.com/craigsims808/image/upload/v1722860520/articles/railway-medusa/medusa-admin-login_yyrbq8.png)

In the **Products** section of your dashboard you should see a list of products. This is the dummy data you seeded into your database in the previous step.

![Medusa Admin Dashboard - Products Section](https://res.cloudinary.com/craigsims808/image/upload/v1722860625/articles/railway-medusa/medusa-admin-products_zdplb4.png)

## Install and test storefront locally

Install dependencies
```sh
cd medusa-railway
cd medusa-storefront
npm install
```

Copy environment variables
```sh
cp .env.template .env.local
```

Run the storefront server.
```sh
npm run dev
```
Your Next.js Starter Storefront will start running on port `8000`. Visit [localhost:8000](http://localhost:8000) in your browser to see the storefront.

![Medusa Storefront Home Page](https://res.cloudinary.com/craigsims808/image/upload/v1722861405/articles/railway-medusa/medusa-storefront_ghfhzn.png)

If all is working you should see the storefront with products from your backend displayed.

## Author

[Mark Munyaka](https://markmunyaka.com)

GitHub: [@Marktawa](https://github.com/Marktawa)  
Twitter: [@McMunyaka](https://twitter.com/McMunyaka)

## Sponsor

Support my passion for sharing development knowledge by making a donation to my [**Buy Me a Coffee**](https://www.buymeacoffee.com/markmunyaka) account. Your contribution helps me create valuable content and resources. Thank you for your support!

[![Buy Me A Coffee Banner](https://res.cloudinary.com/craigsims808/image/upload/v1708089939/articles/test/buymeacoffee_lqmwjn.png)](https://www.buymeacoffee.com/markmunyaka)

[Buy Me A Coffee](https://www.buymeacoffee.com/markmunyaka)
