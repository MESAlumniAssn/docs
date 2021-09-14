# Adding links to the navbar

The navbar on each page contains different links. The links for each page are specified in `/utils/navLinks.js`.

Let's say for instance we are adding a new route to the website called `/donations`. To add links to `/donations` in the navbar, we will first create an object called`donations` (can be named anything) in `navLinks.js`.

```
const donations = {
  path: "Donations",
  url: "/donations",
  icon: <FontAwesomeIcon icon={faHandHolding} style={{ fontSize: "1.5rem" }} />,
}
```

Now, to add a link to `/donations` on the about page, we can simply update the `navlinks` object.

```
const navLinks = {
    ...
     "/about": [home, pricing, contact, donations],
    ...
}
```

To add nav links that will be visible on the `/donations` page, we can update the same `navLinks` object.

```js hl_lines="4"
const navLinks = {
    ...
     "/about": [home, pricing, contact, donations],
     "/donations": [home, pricing, contact, about]
    ...
}
```
