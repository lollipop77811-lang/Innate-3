# The Innate Bliss

React + Next.js App Router funnel. Run `npm ci` and `npm run dev`. For production use `npm run build` and `npm start`, or deploy to a Next.js host with server routes enabled.

## Before launch

- Edit `app/content.ts` with the VSL, Payal’s portrait, and approved testimonials. Each testimonial can include `avatar`, `video`, and `result` URLs or text as appropriate. Remove the visible Placeholder label from the testimonial template once the sample entries are replaced.
- Copy `.env.example` to `.env.local` and set the deployed origin, Meta Pixel ID and embeddable application form URL. Replace the temporary social image in `app/layout.tsx` if needed.
- Create a ₹299 Razorpay Payment Link with partial payments disabled. Configure its callback method as GET and URL as `https://YOUR_DOMAIN/api/payment/callback`. Set its public URL, link ID, and corresponding API key secret in the environment. Never prefix the secret with `NEXT_PUBLIC_`.
- The callback checks the signature, expected link ID and paid status before redirecting to `/application` and issuing the Purchase event marker. The application page itself is a public placeholder, not an entitlement gate. Cancellations occur on the hosted checkout; invalid callback returns show a retry message on `/book`.
- Test a real or Razorpay test-mode purchase, a canceled payment, the form embed, and the funnel inside Instagram and Facebook before sending ad traffic. No Lighthouse score has been measured.
