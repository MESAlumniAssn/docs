# Application Architecture

<p align="center"><img src="https://github.com/MESAlumniAssn/docs/blob/main/docs/assets/tech/architecture.png" alt="Architecture"/></p>

The website sits behind **Cloudflare** which acts as the content delivery network (CDN). We are using the free tier of the CDN as the current iteration of the website does not warrant an upgrade to a paid tier.

The CDN largely helps in improving the performance by serving the website from Cloudflare's 200 plus PoP's (points of presence). It also serves as a caching layer for static assets.

We use a single **DigitalOcean** droplet running **Ubuntu 20.04 LTS** which hosts the website, the backend api and the database. The website is developed in **Next.js**. The backend api endpoints, built with **FastAPI** talk to a **PostgreSQL** database.

**ImageKit.io** is our image store. In addition to storing images, we also use ImageKit's transformations while fetching images. All payments are processed via **Razorpay**'s api and emails to end users/the association are sent from **SendGrid**.

## Editing the architecture diagram

The diagram was created with **draw.io**. To edit the image, open the `architecture.drawio.png` file included in the `docs` repository on the draw.io website or download the **Draw.io Integration** plugin for VS Code and open the file in the VS Code editor itself.
