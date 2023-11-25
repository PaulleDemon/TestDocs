# TestDocs
A repo for testing docs


<p align="center">
  <img src="https://github.com/PaulleDemon/Email-automation/blob/master/logos/atmailwin-logo.svg" alt="CupidCues icon" width="200px" height="200px"/>
</p>

![another image](https://github.com/PaulleDemon/PaulleDemon/raw/main/images/buy-me-coffee.png?raw=true)

A free and open-source email automation tool. Schedule, personalize and send!
<br/>
<br/>
Have you ever meticulously crafted a personalized email to a potential employer or business and waited eagerly for a response that never arrived? It's a common scenario, and the disappointment is palpable. Creating highly personalized emails is time-consuming and often doesn't yield the desired results. AtMailWin offers a workaround - the ability to create semi-personalized emails, schedule them send them in bulk to multiple recipients.

You can use the site at [https://atmailwin.com](https://atmailwin.com) 


## Features

* Create dynamic `email templates`.
* Use variables, if statements in your email template.
* Schedule email.
* Schedule Follow-ups (follow-ups increases the chance of receiving response from recipient).
* Specify follow up rule. 
* Use existing [templates](https://atmailwin.com/email/templates/?public=True).

>**Note**: Don't use this service to send marketing emails or spams. It can result in your email's being sent to spam or locked.

Read this [article](https://atmailwin.com/blog/9/making-the-most-of-atmailwin-for-effective-cold-mailing/) 
to make most out of this tool

> This tool makes use if Jinja2 to render the emails, so any valid jinja syntax is acceptable


## Example Usage

Subject
```
Feedback on AtMailWin
```

Body
```
Hello {{name}},
Hope you are doing well. I am {{from_name}} reaching out to you to
inquire about your experience using this automation platform. It 
looks like your experience with us is {% if feedback == "positive" %} 
positive {% else %} negative {% endif %}. We would be grateful, if you 
could explain a little more about your feed back.

{{from_signature}}
```

<details>

<summary>Output</summary>
Hello Rob,

Hope you are doing well. I am Paul reaching out to you to inquire about your experience using this automation platform. It looks like your experience with us is positive . We would be grateful if you could explain a little more about your feedback.

Best regards, Paul

</details>

## How it works?

 1. Configure a email id by clicking on email configuration link.
 2. Create a email template. Use Variables within enclosed brackets `{{}}` to personalize the email.
 3. Schedule the email, create followups.


## Self hosting
If you want to self host it.

clone the repo
```
git clone https://github.com/PaulleDemon/Email-automation
```
Install python 3.8 or above

Install dependencies
```
pip install -r requirements.txt
```

add a .env file inside the email_automation folder with the following 
```
DEBUG=1
DOMAIN=""
SECRET_KEY=""
PORD_SECRET_KEY=""
REDIS_PROD_HOST=""

FIELD_ENCRYPTION_KEY=""
PROD_FIELD_ENCRYPTION_KEY=""

EMAIL_HOST=""
EMAIL_HOST_USER=""
EMAIL_HOST_PASSWORD=""

POSTGRES_DATABASE=""
POSTGRES_USER=""
PROD_DB_PASSWORD=""
POSTGRES_PASSWORD=""
POSTGRES_HOST=""

POSTGRES_URL=""

FIREBASE_CRED_PATH=""
```
> You must fill up the values required

> You can create encryption key using the following `python manage.py generate_encryption_key`

> To generate secret key use `from django.core.management.utils import get_random_secret_key` then `get_random_secret_key()` in your python shell

Run database creation queries using
```
python manage.py migrate
```

now run the website using 
```
python manage.py runserver
```
