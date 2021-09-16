# Project Structure

The javascript portion of the frontend is built with **Next.js** and **React**. To the extent possible, components have been placed in folders named after the page that they are rendered into.

## **Directories**

:fontawesome-solid-hand-point-right:{ .main } The `pages` directory contains all the page routes. This is a directory created by **Next.js** for file-based routing. The `index.js` file is required and it resolves to `/`. `about.js` resolves to `/about`, `contact.js` resolves to `/contact` and so on.

:fontawesome-solid-hand-point-right:{ .main } The `components` directory contains all the UI components. The `components/forms` directory contains all the form components, `components/layout` includes all the common layout components like the navbar and the footer in addition to the markup that goes into `<head>` on each page. `components/utils` contain the UI components that are rendered on different web pages. `components/utils/generic` contains shared components.

:fontawesome-solid-hand-point-right:{ .main } The `context` directory contains the context api logic which is used to fetch data from the **Python** api and add it to the state

:fontawesome-solid-hand-point-right:{ .main } The `public` directory contains all the public assets like the various site icons, the favicon and the loader. Although most of the images on the website are rendered from **Imagekit.io**, some background images, social media icons etc are present in `public/images`

:fontawesome-solid-hand-point-right:{ .main } The `utils` directory in the project root contains **JavaScript** files with helper functions, data for drop-down lists and some generic data that is shared across different components

:fontawesome-solid-hand-point-right:{ .main } The `styles` directory contains the **CSS** files used by the site. More information about the styling of the website can be found [here](site_style.md)

## **Tests**

For tests, the project uses the **React Testing Library** and **Jest**. All the tests are included in the `__tests__` directory. Other **Jest** related configuration is included in the `jest.config.js` and the `jest.setup.js` files.

## **Error Tracking and Logging**

**Sentry** is used for tracking and logging errors from the website. **Sentry** related configuration is included in the `next.config.js`, `sentry.client.config.js`, `sentry.server.config.js` and `sentry.properties` files.
