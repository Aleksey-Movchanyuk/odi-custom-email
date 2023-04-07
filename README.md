# odi-custom-email

This source code is an XML representation of an Oracle Data Integrator (ODI) procedure, specifically designed to send an email with optional attachments using the Python programming language (Jython, to be precise). The code is organized into a series of <Object> elements, each of which contains <Field> elements that store various pieces of information and code snippets.

The procedure leverages the smtplib, MimeWriter, base64, StringIO, and javax.activation.MimetypesFileTypeMap libraries to achieve its goal. Here's a high-level overview of the different sections of the code:

1. Initialize the SMTP server, using the provided host and port (25).
1. Define a list of MIME types for various file formats.
1. Encode the username and password for SMTP authentication.
1. Read the contents of the specified email file (body text) from the given file path.
1. Create a MIME-encoded message, including headers such as 'From', 'To', 'Subject', and 'X-Priority'.
1. Write the body of the email as plain text or HTML, depending on the specified settings.
1. Attach files (if any) to the email by encoding them in base64 and adding the appropriate MIME headers.
1. Finish the MIME-encoded message and send it.


The procedure uses ODI substitution methods ```(<%=snpRef.getOption("...")%>)``` to dynamically retrieve parameter values for the SMTP host, email sender and recipient, subject, and other settings.
