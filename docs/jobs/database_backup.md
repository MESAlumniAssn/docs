# Database Backup

The PostgreSQL database is backed up daily. A shell script is used to create the backup by leveraging the `pg_dump` utility. This script is present in the `/home` directory of the `postgres` user.

Once the job runs, the `/jobs` endpoint is called to update `jobs.job_last_runtime`. The job id is passed in the request payload. The `job_id` corresponding to each job can be found in the `jobs` table.
