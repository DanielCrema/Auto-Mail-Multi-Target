Auto-Mail Multi-Target
Designed by programmer Daniel Crema

This software sends e-mails automatically to multiple addresses
It uses JSON objects to ensure security

How to use it:

-> Create an archive named secrets.json
-> Paste this form inside the archive secrets.json as follows:

{
    "user": "youremail@yourserver.com",
    "pass": "yourpassword",
    "from": "Your Name <youremail@yourserver.com>",

    "subject": "Your E-Mail Subject",
    "text": "Your e-mail content",
    "html": "Your html content",

    "emailList": {
        "email1": "emailadress@server.com",
        "email2": "otheremailadress@server.com"
    }
}

-> Fill your information as in the examples. Pay attention not to delete any quote or code part
=> To run the code, go on your terminal and input 'node index.js'


* NOTE: This code is designed to send e-mails from a gmail account.
If you use another e-mail service, you will need to find the code below at index.js and edit it
with your e-mail service host, port, and SSL security information.

async function sendEmails(emailsArray) {
    let transporter = nodemailer.createTransport({
        host: "smtp.gmail.com",
        port: 465, // Gmail port
        secure: true,
        auth: {
            user: user,
            pass: pass,
        }
    });

}

Do notice that your e-mail service may ask for security checks and
other procedures in order to give access to your script.