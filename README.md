# SafeHostel

A website for finding safe, verified student hostels near campus in Kampala.
Built with **HTML and CSS only**: no JavaScript, no backend, no database.

Open `index.html` in a browser to view it, or upload the whole folder to any static host
(GitHub Pages, Netlify, cPanel hosting, etc.).

## Pages (sitemap)

| No. | Page | File |
|-----|------|------|
| 1.0 | Home | `index.html` |
| 2.0 | Find a Hostel | `find-a-hostel.html` |
| 2.1 | Search results (with filters) | `results.html` |
| 2.2 | Hostel profile | `hostel-*.html` (one per hostel) |
| 2.3 | Viewing confirmation | `viewing-confirmation.html` |
| 3.0 | List Your Hostel | `list-your-hostel.html` |
| 3.1 | Registration form | `register.html` → `registration-received.html` |
| 3.2 | Verification rules | `verification-rules.html` |
| 4.0 | Safety & Tips | `safety.html` |
| 4.1 | Checklist before paying | `checklist.html` |
| 4.2 | Your rights as a tenant | `tenant-rights.html` |
| 5.0 | About Us | `about.html` |
| 5.1 | How we verify hostels | `how-we-verify.html` |
| 6.0 | Contact | `contact.html` → `message-sent.html` |
| 6.1 | Report a scam | `report-scam.html` → `report-received.html` |
| 6.2 | FAQs | `faqs.html` |
| –   | Privacy notice, 404, review received | `privacy.html`, `404.html`, `review-received.html` |

All styling is in `css/style.css`. Fonts (Unbounded and Bricolage Grotesque, SIL Open Font Licence) are in `fonts/`.

## How the interactive parts work without JavaScript

- **Mobile menu**: a hidden checkbox and its `<label>` (the "Menu" button) show and hide the menu.
- **Home slider and photo gallery**: hidden radio buttons; the arrows and thumbnails are `<label>`s.
- **Search filters**: the radio buttons on `results.html` hide hostel cards using CSS `:has()`.
  Each card carries classes such as `u900` (price under 900k), `w1` (within 1 km), `gf` (open to female students).
  A CSS counter shows how many hostels match.
- **Home quick search**: links like `results.html#female` use CSS `:target` to apply a filter.
- **FAQs**: `<details>` and `<summary>`.
- **Form checks**: HTML `required`, `pattern`, `min` and `type="email"` checks, styled with `:user-invalid`.

## Before you launch

1. **Hostel listings are examples.** The six hostels, their prices and reviews are made up to show the layout.
   Replace them with real hostels your group has verified, and remove any you don't have.
   To add a hostel: copy a `hostel-*.html` file, edit it, and add a card for it to `results.html`.
2. **Replace the contact details**: phone number `+256 700 000 000` and email `hello@safehostel.ug`,
   which appear in every page footer and on `contact.html`. Also update the social media links (`href="#"`).
3. **Team names** on `about.html` are placeholders ("Team member 1" and so on).
4. **Real photos**: the buildings and rooms are drawn in CSS. Swap them for `<img>` tags of your own photos
   when you have them.
5. **Receiving form submissions.** A site with only HTML and CSS cannot store or send what visitors type.
   At the moment each form takes the visitor to its confirmation page, but the information goes nowhere.
   To receive it by email without writing code, sign up for a free form service such as Formspree,
   then change each form's opening tag. For example, change
   `<form ... action="viewing-confirmation.html" method="get">`
   to `<form ... action="https://formspree.io/f/YOUR_ID" method="post">`.
   File uploads on the registration form also need `enctype="multipart/form-data"`
   and a service plan that supports files.
