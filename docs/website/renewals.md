# Annual Membership Renewals

Alumni whose memberships are due to expire or have already expired are sent a renewal link via email. This link redirects the alumni to the `/renewal` route.

Here, the alumni can either renew their annual memberships for a year or can upgrade to a life membership. The alumni can choose to pay online or manually. The payment logic is exactly same as that used for the registration process.

If annual members upgrade to a lifetime membership, the renewal process automatically generates the url for their certificate and nullifies the valid up to date (`users.membership_valid_upto`).
