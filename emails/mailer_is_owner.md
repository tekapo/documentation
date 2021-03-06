# Emails sent from owner email and name

It allows to automatically personalize emails sent to a user who has an owner (mautic user) assigned to it. This feature changes *from email*, *from name* and *signature* from the default setting to the user setting.

## Requirements

- Mautic 1.3.0+
- A none-tokenized mail transport such as Mandrill. This feature won't work with emails sent via API.

## How to enable the emails sent from lead owner

- Open the admin menu by clicking the cog icon in the top right corner.
- Select the *Configuration* menu item.
- Select the *Email Settings* tab.
- Switch the *Mailer is owner* to *Yes*.
- Save the configuration.

## Signature

Signature is also a new feature in the Mautic 1.3.0. There are 2 places where to configure the signature text:

1. The default signature is in the *Configuration*, *Email Settings* tab. The default text is `Best regards,<br/>|FROM_NAME|`. The `|FROM_NAME|` token will be replaced by *Name to send mail as* value also defined in the *Email Settings* tab. This signature will be used if the lead owner is not known.
2. Every user can configure his/hers own signature in the profile edit page. This signature will be used if the lead owner is known.

The signature can be placed into an email text by the `{signature}` token.

There is one exception where the lead owner's signature won't be used. When a user send an email directly from a lead detail, the currently logged in user's signature will be used. Doesn't matter if the lead has another owner assigned or if doesn't have owner at all.

## FAQ

### Does it work for all emails?

There are exceptions:
- The email has to be sent to a lead. If Mautic doesn't have a lead assigned with the email, it doesn't know its owner and therefore cannot know what user name, email and signature to choose. This happens when you send the test emails.
- If you send an email directly from the lead detail, the *from name* and *from email* will be used from the form, not from the user settings. Those values are pre-filled by currently logged in user name and email. 

