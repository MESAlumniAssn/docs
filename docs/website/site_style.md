# Website Styling

A lot of the UI components of the website use **Material UI**. However, the decision to use **Material UI** was taken after some of the initial pages were built. As a result, the source of the styling is not consistent across the website (there is a refactoring opportunity here).

The `styles` directory contains the following files

- `globals.css` - common styles used across the website
- `Home.module.css` - styles specifically for the home route (`/`)
- `FamousAlumni.module.css` - styles specifically for the famous alumni page (`/famousalumni`)

Almost all the individual UI components use the `makeStyles()` method provided by **Material UI**.

## **How do I identify the source file of the style?**

- `<div className="myStyle">` -> `.myStyle` is defined in `globals.css`
- `<div className={styles.myStyle}>` -> `.myStyle` is defined in either `Home.module.css` or `FamousAlumni.module.css`. These will be found only in the components used by the home and famous alumni pages
- `<div className={classes.myStyle}>`-> `myStyle` is defined at the yop of the component using the `makeStyles()` method
