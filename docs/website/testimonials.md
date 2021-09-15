# Testimonials

All the testimonials are stored in the `testimonials` table. Alumni can submit a testimonial using the **WRITE A TESTIMONIAL** option on either the `/` or the `/testimonials` routes.

## **What happens when a testimonial is submitted?**

1. A record is created in the `testimonials` table with the `approved` attribute set to `false`
2. An email is sent to the Association with the testimonial details and a link to approve the testimonial
3. Once the testimonial is approved, the `approved` attribute is set to `true` for that testimonial
4. Testimonial is added to the website
