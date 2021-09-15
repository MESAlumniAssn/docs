# Expiry Notifications

This job sends out an email to annual members on the day their membership has expired.

## **Steps**

1. The job first calls the `/recently_expired_memberships` endpoint to get the list of all annual members whose membership expired on the day prior to the current run date of the job
2. All memberships returned in the response are marked as expired by updating `users.payment_status` to `false` and `users.membership_expired` to `true`.
3. An email is then sent to all the members with a renewal link

Once the job runs, the `update_job_run_date()` function is called to update `jobs.job_last_runtime`. The function takes the job id as an argument. The `job_id` corresponding to each job can be found in the `jobs` table.
