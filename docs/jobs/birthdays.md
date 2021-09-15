# Birthday Notifications

This job checks the `birthday` column in the `users` table and sends out an email via **SendGrid** if it is the alumni's birthday.

Once the job runs, the `update_job_run_date()` function is called to update `jobs.job_last_runtime`. The function takes the job id as an argument. The `job_id` corresponding to each job can be found in the `jobs` table.
