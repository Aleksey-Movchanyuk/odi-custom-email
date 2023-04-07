# odi-custom-email

This source code is an XML representation of an Oracle Data Integrator (ODI) procedure, specifically designed to send an email with optional attachments using the Python programming language (Jython, to be precise). The code is organized into a series of <Object> elements, each of which contains <Field> elements that store various pieces of information and code snippets.

The procedure leverages the smtplib, MimeWriter, base64, StringIO, and javax.activation.MimetypesFileTypeMap libraries to achieve its goal. Here's a high-level overview of the different sections of the code:

1. Initialize the SMTP server, using the provided host and port (25).
2. Define a list of MIME types for various file formats.
3. Encode the username and password for SMTP authentication.
4. Read the contents of the specified email file (body text) from the given file path.
5. Create a MIME-encoded message, including headers such as 'From', 'To', 'Subject', and 'X-Priority'.
6. Write the body of the email as plain text or HTML, depending on the specified settings.
7. Attach files (if any) to the email by encoding them in base64 and adding the appropriate MIME headers.
8. Finish the MIME-encoded message and send it.


The procedure uses ODI substitution methods ```(<%=snpRef.getOption("...")%>)``` to dynamically retrieve parameter values for the SMTP host, email sender and recipient, subject, and other settings.

This ODI procedure accepts the following parameters:

1. **Host**: IP address of the server through which the email will be sent
2. **Port**: Port on which the SMTP server is running
3. **SMTP Auth**: Is authentication required?
   - Yes
   - No
4. **User**: Username
5. **Password**: Password
6. **To**: Sender's email address
7. **From**: Recipient's email address
8. **Subject**: Email subject
9. **LoadfromFile**: Indicator to load text from a file:
   - Yes
   - No
10. **FilePath**: Path to the file from which the email text will be loaded
11. **MessageText**: Email text (if not loaded from a file)
12. **Is HTML**: Email format:
    - HTML
    - Plain Text
13. **Attachment**: Email attachment (list of files separated by commas)
14. **Charset**: Email encoding
15. **Priority**: Email importance:
    - 1 - Important email
    - 3 - Regular email
    - 5 - Low priority email
