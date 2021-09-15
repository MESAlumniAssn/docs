# Admin Dashboard

The admin dashboard provides a means for the Association to keep track of memberships, funds collected and to perform admin functions like updating the payment status and creating events.

## **Accessing the dashboard**

The route for the dashboard is `/dashboard/<admin_id>`. This admin id is stored as an environment variable `NEXT_PUBLIC_ADMIN_ID`. The route is protected and requires the user to login. The user id and password are stored in **LastPass...**.

Logging into this page will redirect the user to `/alumniassndashboard`. A successful login will return a JWT from the server which subsequently needs to be sent with every called made to a dashboard related endpoint exposed by the **Python** api.

The `/alumniassndashboard` route contains three tabs -

- Alumni
- Funds
- Admin Panel

The **Alumni** tab contains all the membership details like the counts and breakdown of the counts displayed in data grids that can be exported to `.csv` files. **Funds** shows the membership fees collected.

## **The Admin Panel**

The **Admin Panel** tab at present, contains three features.

1. **Update Payment Status** - this is used to updated the payment status of the alumni who opted for manual payments during registration or renewal. Once the manual payment is realized by the Association, the concerned member can then enter the membership id of the alumnus and update the payment status to **Paid**. This updates `users.payment_status` to `true`.

2. **Jobs** - this is used to display the status of all the jobs running on the server.

3. **Create Event** - this form is used to create an event. Once an event is created, an email is sent out to all the active members who have not unsubscribed from email notifications. In other words if `users.email_subscription_status` is `true`, the email is sent.

## **More on events**

When an event is created, a corresponding folder is created in **Imagekit.io** wherein images can be added. These images will show up in the gallery for that specific event. The gallery will be visible on the page for that event - `/events/<event_id>`.

If an event titled _Annual general body meeting_ is created using the **Create Event** form on the Admin Panel, then a folder named `Annual-general-body-meeting` will be created in **Imagekit.io** under `MES-AA/Events`.

:fontawesome-solid-hand-point-right:{ .main } There is no image uploader functionality from the website to add images to the event gallery. This needs to be done directly in **Imagekit.io**.
