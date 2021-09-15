# Renewal Reminders

This job is to send reminder emails to annual members whose membership is set to expire in -

1. 30 days
2. 1 day

## **Steps**

1. First, the list of annual members whose membership is set to expire in 30 days is fetched by calling the `/expiring_memberships/{30}`
2. Next, a renewal hash is added (`users.renewal_hash`) to all the records returned by the api call. The renewal hash is used to generate the renewal link
3. An email is sent out with the renewal link

The process is then repeated for members whose membership is expiring in 1 day. A new hash is generated and a new renewal link is emailed to the alumni.

Once the job runs, the `update_job_run_date()` function is called to update `jobs.job_last_runtime`. The function takes the job id as an argument. The `job_id` corresponding to each job can be found in the `jobs` table.
