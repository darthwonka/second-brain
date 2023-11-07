# Accessing shared mailbox with imap

Created: 2021-01-23 21:43:14 -0700

Modified: 2021-01-27 00:02:57 -0700

---

michael@salusigroup.com <-- user account

support@salusitgroup.com <--shared mailbox

IMAP settings:

address: support@salusitgroup.com

username: michael@salusitgroup.com/support

password: <user's password>

IMAP server: outlook.office365.com

security type: SSL

port: 993

SMTP settings:

SMTP server: outlook.office365.com

security type: TLS

port: 587

smtp

UN: user@contoso.comsmtp

PW: <user's password>

Note that the SMTP server is outlook.office365.com not smtp.office365.com as suggested on the MS site. When you setup a normal office365 IMAP account you'd use smtp.office365.com for the SMTP server but when you setup a shared mailbox you use the above procedure. What I'm told is that because shared mailboxes don't have their own IMAP and SMTP credentials, you have to tell MS on your way in (IMAP) that you are accessing the shared mailbox using the user account and on the way out (SMTP) using the user account without reference to the shared mailbox.

Alternate host: {outlook.office365.com:993/imap/ssl/authuser=michael@salusitgroup.com/user=support@salusitgroup.com}

{outlook.office365.com:993/imap/ssl}INBOX

*From < <https://stackoverflow.com/questions/39224039/php-imap-with-office365-mail>>*
