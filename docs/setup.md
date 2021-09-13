# Setting up the projects

Following github repositories contain all the projects -

1. `mes-aa-site` - the Next.js/React website
2. `mes-aa-api` - the Python based api
3. `mes-aa-jobs` - the helper jobs running on the server
4. `docs` - the documentation site

## **Install dependencies**

1. Python v3.8
2. Node.js v14.17.6 or higher

## **Setting up the `mes-aa-api` project locally**

[![Build Status](https://app.travis-ci.com/MESAlumniAssn/mes-aa-api.svg?branch=main)](https://app.travis-ci.com/MESAlumniAssn/mes-aa-api)

1. Clone the repository - `git clone https://github.com/MESAlumniAssn/mes-aa-api`
2. Create a virtual environment - `python -m venv venv`
3. Activate the virtual environment - `venv\Scripts\activate` (windows) or `source venv/bin/activate` (Linux/MacOS)
4. Install the project dependencies - `pip install -r requirements.txt`
5. Create the environment variables in a `.env` file. Refer to the `.env.example` file for the list of variables
6. Run the project - `uvicorn app.main:app --reload`
   <br />

:fontawesome-solid-hand-point-right:{ .main } This project should be run before starting the website (`mes-aa-site`)<br />
:fontawesome-solid-hand-point-right:{ .main } The `requirements.txt` on the server contains additional dependencies like `gunicorn` which are not needed locally to run the project in the present setup

## **Setting up the `mes-aa-site` project locally**

[![Build Status](https://app.travis-ci.com/MESAlumniAssn/mes-aa-site.svg?branch=main)](https://app.travis-ci.com/MESAlumniAssn/mes-aa-site)

1. Clone the repository - `https://github.com/MESAlumniAssn/mes-aa-site`
2. Install the project dependencies - `npm i`
3. Create the environment variables in a `.env.local` file. Refer to the `.env.local.example` file for the lit of variables
4. Run the project - `npm run dev`

## **Setting up the `mes-aa-jobs` project locally**

[![Build Status](https://app.travis-ci.com/MESAlumniAssn/mes-aa-jobs.svg?branch=main)](https://app.travis-ci.com/MESAlumniAssn/mes-aa-jobs)

1. Clone the repository - `https://github.com/MESAlumniAssn/mes-aa-jobs`
2. Create a virtual environment - `python -m venv venv`
3. Activate the virtual environment - `venv\Scripts\activate` (windows) or `source venv/bin/activate` (Linux/MacOS)
4. Install the project dependencies - `pip install -r requirements.txt`
5. Create the environment variables in a `.env` file. Refer to the `.env.example` file for the list of variables
6. Run a specific job -<br />
   :fontawesome-solid-chevron-right:{ .main } Birthday notifications - `python birthday.py`<br />
   :fontawesome-solid-chevron-right:{ .main } Membership expiry notifications - `python expiry_notifications.py`<br />
   :fontawesome-solid-chevron-right:{ .main } Renewal notifications - `python renewal_notifications.py`

## **Setting up the `docs` project locally**

1. Clone the repository - `https://github.com/MESAlumniAssn/mes-aa-jobs`
2. Create a virtual environment - `python -m venv venv`
3. Activate the virtual environment - `venv\Scripts\activate` (windows) or `source venv/bin/activate` (Linux/MacOS)
4. Install the project dependencies - `pip install -r requirements.txt`
5. Run the project - `mk docs serve`
