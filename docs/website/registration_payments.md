# Registration & Payments

The end to end workflow for registration.

### **Completing the registration form**

1. Once the alumni navigates to the `/register` route or clicks on the _Membership_ link in the navbar, they are routed to the `/pricing` page to select the membership option.
2. Once a membership is selected, it is saved in the browser's local storage and the alumni are routed to `/register`
3. Once the alumni fill up all the required fields in the first three steps of the registration form, they can navigate to the fourth step which includes a summary of the membership and payment details

### **Online payment**

The website integrates with **Razorpay** as the payment gateway.

1. When an alumni clicks on the **PAY ONLINE** button, the **Razorpay** modal is displayed
2. The alumni can choose from a wide variety of pre-configured payment options to pay the membership fee
3. If there is an issue with the payment, the payment times out and alumni is redirected to the last step of the registration process
4. If the payment is successful, the alumni is routed to the `/paymentverified/<id>` route

### **What happens when PAY ONLINE is clicked?**

By clicking **PAY ONLINE** we are submitting the form. One of the first things that happens is that all the registration related data is stored in the local storage. Next, a payment order is created by the `createOrder()` function which internally calls the `/orders` endpoint exposed by the **Python** api.

Once the order is successfully created and the order id is returned by the api, the `displayRazorPay()` function is called within a `useEffect()`. Next, the order id and other options are passed to the checkout (`https://checkout.razorpay.com/v1/checkout.js`) to display the modal. Once a payment is made successfully, **RazorPay** mandates that we validate the authenticity of the details that were sent to the checkout. This is done by calling the `verifyPayment()` method which internally calls the `/verification` endpoint exposed by the **Python** api. If the verification is successful, the api returns a `null`. At this point, we save all our data to the `users` table in our database and the alumni is redirected to the `/paymentverified/<id>`.

For such payments, the `payment_status` column in the `users` table is set to `true` and the `payment_mode` is set to `O` (online).

On successful registration, the alumni receive a welcome email from the President and the payment receipt.

![Verified Payment](https://ik.imagekit.io/pwxm960evbp/MES-AA/Docs/payment_verified_2ajevYv-i.png?updatedAt=1631681323801)

### **Alternate payment method**

The alumni can also opt for manual payments by means of cheques, demand drafts, or EFT's. When the **SEE ALTERNATE PAYMENT OPTION** button is clicked, a modal is displayed with details about the various manual payment options. Once the **CONFIRM** button is clicked, a record is created in the `users` table with the `payment_status` set to `false` and the `payment_mode` set to `M` (manual).

Once the record is created, the alumni will be redirected to `/paymentinfo/<email>`. An email is containing all the payment related information is sent to the alumni.

Once the payment is realized by the Association, an association member can use the [Admin Panel](https://mesalumniassn.github.io/docs/website/admin_dashboard/#the-admin-panel) to updated the payment status.

![Alternate Payment](https://ik.imagekit.io/pwxm960evbp/MES-AA/Docs/payment_info_p3-XUkXlIl.png?updatedAt=1631681323764)

### **Id Card and Certificate**

Irrespective of whether the alumni has chosen to pay online or manually, links for their id cards and certificates are generated automatically as soon as the record is inserted into the `users` table. The table contains an `alt_user_id` column which is a `uuid` generated whenever a record is inserted.

- Id cards for a user can be accessed at `/card/<alt_user_id>`
- Certificates can be accessed at `/certificate/<alt_user_id>`

Id cards and certificates contain a membership id. The format of this id is -

**MESAA-(type of membership: LM/OM)-(last two digits of an alumnus' year of passing)-(id in the `users` table)**

Ex 1: If a **L**ife **M**ember passed out in 1999 (`users.duration_end`) and has an id (`users.id`) of 10, then the membership id will be **MESAA-LM-99-10**

Ex 2: If an **O**rdinary **M**ember/Annual Member passed out in 2002 (`users.duration_end`) and has an id (`users.id`) of 9, then the membership id will be **MESAA-LM-02-09**
