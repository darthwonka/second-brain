# Google Captcha Registration

Created: 2018-06-26 15:27:25 -0600

Modified: 2018-06-26 15:27:56 -0600

---

Site key

Use this in the HTML code your site serves to users.

6Ldj42AUAAAAAJuj3AsDU-iNVvT2IGKQ-PRzQ6Zz

Secret key

Use this for communication between your site and Google. Be sure to keep it a secret.

6Ldj42AUAAAAAMc8JUKKNeUIQEtSCd0yTZJt-t8X

Paste this snippet before the closing </head> tag on your HTML template:<script src='https://www.google.com/recaptcha/api.js'></script>Paste this snippet at the end of the <form> where you want the reCAPTCHA widget to appear:<div class="g-recaptcha" data-sitekey="6Ldj42AUAAAAAJuj3AsDU-iNVvT2IGKQ-PRzQ6Zz"></div>[The reCAPTCHA documentation site](https://developers.google.com/recaptcha/) describes more details and advanced configurations.

When your users submit the form where you integrated reCAPTCHA, you'll get as part of the payload a string with the name "g-recaptcha-response". In order to check whether Google has verified that user, send a POST request with these parameters:

**URL**: <https://www.google.com/recaptcha/api/siteverify>

| **secret** (required)   | 6Ldj42AUAAAAAMc8JUKKNeUIQEtSCd0yTZJt-t8X |
|-------------------------|------------------------------------------|
| **response** (required) | The value of 'g-recaptcha-response'.   |
| **remoteip**            | The end user's ip address.              |

[The reCAPTCHA documentation site](https://developers.google.com/recaptcha/docs/verify) describes more details and advanced configurations.

**Key Settings**

Label(reCAPTCHA v2)

Domains(one per line)

Owners(one per line)

Send alerts to owners?
