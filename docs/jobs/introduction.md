# Jobs

There are currently four standalone jobs running on the server.

1. Birthday Notifications
2. Expiry Notifications
3. Renewal Reminders
4. Database Backup

## **Schedule**

| Job Name               | Time     | Frequency |
| ---------------------- | -------- | --------- |
| Birthday Notifications | 1 AM     | Daily     |
| Expiry Notifications   | 12:30 AM | Daily     |
| Renewal Reminders      | 12:15 AM | Daily     |
| Database Backup        | 12:15 AM | Daily     |

:fontawesome-solid-hand-point-right:{ .main } Times are local to the server

The **Database Backup** job runs under the `postgres` user. The remaining jobs run under the `sudo` user. All the jobs are currently setup as cron jobs on the server.

## **Checking the job status**

The last run date of the jobs is updated in the `jobs` table.

The status of all jobs is visible in the **Admin Panel**.

![Job status](https://ik.imagekit.io/pwxm960evbp/MES-AA/Docs/job_status_SbsEeBQ0-G.jpg?updatedAt=1631703708188)
