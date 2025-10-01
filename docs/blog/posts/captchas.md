---
date: 2025-08-19
categories:
    - otherkin 
tags:
    - otherkin
comments: true
---
# Captchas for otherkin
Thanks wplace... All the captchas made me dysphoric.
<!-- more -->

## my CSS userstyle
!!! warning
    this does not work with cloudflare turnstile captchas sadly(doesn't work on wplace)

```css
/**
 * Override the text of CAPTCHAs. Don't be rude to protogens.
 * Originally by mavica: https://maple.pet/
 * Updated by beeps: https://beeps.website/
 * modified by Flare https://flare-proto.github.io
 * 
 * Covers:
 * (1) Google reCAPTCHA
 * (2) hCaptcha
 * (3) Cloudflare Turnstile
 * (4) Microsoft CAPTCHA
 * (5) Friendly Captcha
 * (6) ALTCHA
 */
 
 
/* 1 */ #recaptcha-anchor-label,
/* 2 */ body > div#anchor > div.label-container > label-td > label-tc > div#label,
/* 3 */ div#content div#challenge-stage div.cb-c label.cb-lb span.cb-lb-t,
/* 4 */ #root > .box > .box > p[data-theme="home.instructions"],
/* 5 */ .text:is([data-loc="t_ready"], [data-loc="t_completed"]),
/* 6 */ label[for="altcha_checkbox"] {
  font-size: 0 !important;
  line-height: 0 !important;
}

/* 1 */ #recaptcha-anchor-label::before,
/* 2 */ body > div#anchor > div.label-container > label-td > label-tc > div#label::before,
/* 3 */ div#content div#challenge-stage div.cb-c label.cb-lb span.cb-lb-t::before,
/* 4 */ #root > .box > .box > p[data-theme="home.instructions"]::before,
/* 5 */ .text:is([data-loc="t_ready"], [data-loc="t_completed"])::before,
/* 6 */ label[for="altcha_checkbox"]::before {
  font-size: 14px;
  line-height: 1.2;
}

/* 1 */ #recaptcha-anchor-label::before,
/* 2 */ body > div#anchor > div.label-container > label-td > label-tc > div#label::before,
/* 3 */ div#content div#challenge-stage div.cb-c label.cb-lb span.cb-lb-t::before,
/* 5 */ .text[data-loc="t_ready"]::before,
/* 6 */ label[for="altcha_checkbox"]::before {
  /* Message that usually appears next to a challenge. */
  content: "I'm a protogen";
}

/* 4 */ #root > .box > .box > p[data-theme="home.instructions"]::before {
  /* Message that usually appears before a challenge. */
  content: "Prove you are a protogen.";
}

/* 5 */ .text[data-loc="t_completed"]::before {
  /* Message that usually appears after completing a challenge. */
  content: "You're a protogen!";
 }
```

## Credit 
[https://beeps.website/blog/2023-04-27-otherkin-friendly-captchas-revisited/](https://beeps.website/blog/2023-04-27-otherkin-friendly-captchas-revisited/)
