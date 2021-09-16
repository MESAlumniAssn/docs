# Developer Workflow

Until the site went live, all changes were checked directly into the `main` branch of the respective projects. Now that we are live, the following is the recommended approach for making changes in the `site`, `api` and `jobs` projects.

:fontawesome-solid-hand-point-right:{ .main } Changes to `docs` can be pushed directly to the `main` branch. The below processes do not apply to the `docs` project. See [documentation changes](documentation.md) for details to update the project documentation.

## **Getting access**

It is preferred that developers use their personal Github accounts and request access to all the repos under **MESAlumniAssn**.

All passwords are stored in a **LastPass...** vault. The developers who require access to any specific service should contact the association for specific passwords.

## **Github workflow**

Whenever there is a new feature request or a potential bug fix, the first step is to open an issue in Github using the pre-configured template. All the repositories contain the _new feature_ and _bug fix_ issue templates.

Next, create a local branch - `git checkout -b <branch_name>`

The naming convention for branches should be as follows -

- Bug fix - **mes-aa-bug-issue_number** Ex: `mes-aa-bug-#10`
- New feature - **mes-aa-feature-issue_number** Ex: `mes-aa-feature-#11`
- Composite (includes both a bux fix and new feature) - **mes-aa-hybrid-issue_number_1-issue_number_2** Ex: `mes-aa-hybrid-#12-#13`

Once the changes are complete and tested, commit the changes and push the changes to the remote repo - `git push origin <branch_name>`.

Next, create a pull request, check for merge conflicts (if any) and merge the changes with the `main` branch and close the pull request. This will automatically close the issue as well.

## **The CI/CD pipeline**

Once the changes are merged with the `main` branch, the CI/CD pipeline kicks off on Travis CI (the **Build pushed branches** option is checked for all the repo's on Travis CI).

Each project includes a `travis.yml` file with the build configuration. At the moment, tests are only included for the `mes-aa-site` repository. These tests were added merely to serve as a smoke test before deployment. There is an opportunity to add tests for the `api` and `jobs` projects as well.

During the initial phase of the project, the developer received continuous feedback from the website committee. Due to this, the addition of tests was low on the priority list. This needs to be eventually addressed.

The final step of the build executes a shell script, `deploy.sh`. This deploys the code from the latest build on the server.

:fontawesome-solid-hand-point-right:{ .main } The Python api backend uses `gunicorn` which is run as a daemon process using the `supervisor` package. Once any change is deployed for the `api` project, `supervisor` must be restarted when logged in as the `sudo` user on the server, using the command `sudo supervisorctl reload`<br />
:fontawesome-solid-hand-point-right:{ .main } No separate restarts are needed for the `site` project. This is automatically handled in the `deploy.sh` script.

For details on the pipeline and server setup, please refer to these articles <br />
:fontawesome-solid-star:{ .main } [Initial setup on a Linux server](https://www.codedisciples.in/linux-vps-deployment1.html)<br />
:fontawesome-solid-star:{ .main } [Deploying a Python application](https://www.codedisciples.in/linux-vps-deployment1.html) - the article walks through a Flask app but the steps are the same<br />
:fontawesome-solid-star:{ .main } [Deploying a react application](https://www.codedisciples.in/react-deployment.html)<br />
:fontawesome-solid-star:{ .main } [Setting up the CD/Cd pipeline](https://www.codedisciples.in/travis-digitalocean.html)<br />
