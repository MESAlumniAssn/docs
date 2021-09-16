# How to update email templates?

All the email templates used are designed in **SendGrid**. The dynamic templates feature was one of the reasons why **SendGrid** was chosen as the cloud email provider. The static text and images in a template can be easily changed with zero coding.

1. Log in to the Association's [**SendGrid account**](https://app.sendgrid.com/login/)
2. Expand **Email API** and click on the **Dynamic Templates** link<br /><br />
   ![Dynamic Templates](https://ik.imagekit.io/pwxm960evbp/MES-AA/Docs/sg1_1__VgZOlb87O.jpg?updatedAt=1631782906577)
3. Next, select a template to update<br /><br />
   ![Update Template](https://ik.imagekit.io/pwxm960evbp/MES-AA/Docs/sg2_1__PyOhrINoBJl.jpg?updatedAt=1631782906663)
4. The template will open in a designer window where the text and images can be changed easily<br /><br />
   ![Designer](https://ik.imagekit.io/pwxm960evbp/MES-AA/Docs/sg3_1__ga4WE2FR04.jpg?updatedAt=1631782906692)

:fontawesome-solid-hand-point-right:{ .main } Do not add or update any field that is enclosed by `{{ }}`. These fields are populated dynamically and should therefore be added by developers only.
