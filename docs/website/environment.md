# Environment Variables

When developing locally, it is sufficient to include a `.env.local` file in the project root. However, when deploying, the build uses the environment variables from **Travis CI**.

Any new environment variable or any update to an existing environment variable must therefore be made in **Travis CI** before running the CI/CD pipeline. Environment variables can be added by accessing the settings of a repository in **Travis CI**.

![Env vars](https://ik.imagekit.io/pwxm960evbp/MES-AA/Docs/travis-env_rKPPitrvF.png?updatedAt=1631681570683)

:fontawesome-solid-hand-point-right:{ .main } The `.env.local` file must **not** be checked into source control
