# Acrobatiq Email Templates

<img src="https://github.com/blakeperdue/acro-email-template/blob/acro/preview2.png?raw=true" alt="preview" width="500">

This is a really simple and easy to create and maintain HTML email template system. It should make creating and managing our email templates easier, while also providing modern, responsive emails that will render and perform better across devices.

# Tested on all email clients
[Litmus test results](https://litmus.com/checklist/emails/public/233ded7)

# How to create a new template

Copy the `email.html` master template and name it as a new file, such as `email-password-reset.html` for example.

Next, replace the template variables, which can be found in `{{ }}` variables inside the code. You can load the HTML file in your browser to test how it looks and functions. 

<img src="https://github.com/blakeperdue/acro-email-template/blob/acro/preview-vars.png?raw=true" alt="preview of variables" width="500">

**Remember** to update the first variable in the template `{{email text preview goes here}}` with a short sentence. This is what will appear in email clients as the text preview of the email. This should be similar to the email subject but provide more details.

## Inline your CSS before sending

Once you have finalized your template, you need to inline the CSS styles. The master `email.html` file has styles in the head of the document. To make the template work in email clients, you need to process the template to inline the styles.

I prefer [Juice](http://automattic.github.io/juice/) but there are [many available](https://htmlemail.io/inline/). They key is to inline the styles and create a new file and append the `__inlined` to the file name. So, `email-password-reset.html` would become `email-password-reset__inlined.html`. This way, you can be clear about which file is the template, and which file has been inlined and is ready for use.

We do it this way because it's way easier to update the styles and content in the master template before the styles have been inlined.

## Images in email

When inserting images remember to include the following attributes or risk them breaking in different clients:

* `src`
* `alt`
* `width`
* `height`
* `border`

Example:

`<img src="https://absolute-path-to-image.jpg" alt="Useful alt text" width="500" height="300" border="0" style="border:0; outline:none; text-decoration:none; display:block;">`

[More information here](https://www.smashingmagazine.com/2017/01/introduction-building-sending-html-email-for-web-developers/)

# Original Source

This repo is a clone of [responsive-html-email-template](https://github.com/leemunroe/responsive-html-email-template). You can visit that repo to learn more about the templates and how to update them.
