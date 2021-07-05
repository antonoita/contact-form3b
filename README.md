# contact-form3b
<form method="POST" action="kuileyshi-contact-form-namecheap-php45.php" id="contact-form">
<h2>Contact us</h2>
<p><label>First Name:</label> <input name="name" type="text" /></p>
<p><label>Email Address:</label> <input style="cursor: pointer;" name="email" type="text" /></p>
<p><label>Message:</label> <textarea name="message"></textarea> </p>
<p><input name="sendflag" type="submit" value="send" /></p>
</form>

\....Remember to replace file_with_php_fucntion.php with the name of the file with PHP mail() code..../

$mail_to_send_to = "kuileyshi3000k@gmail.com";
$from_email = "from@yourdomain.tld";
$sendflag = $_REQUEST['sendflag'];    
$name=$_REQUEST['name'];
if ( $sendflag == "send" )
        {
                $subject= "Message subject";
                $email = $_REQUEST['email'] ;
                $message= "\r\n" . "Name: $name" . "\r\n"; //get recipient name in contact form
                $message = $message.$_REQUEST['message'] . "\r\n" ;//add message from the contact form to existing message(name of the client)
                $headers = "From: $from_email" . "\r\n" . "Reply-To: $email"  ;
                $a = mail( $mail_to_send_to, $subject, $message, $headers );
                if ($a)
                {
                     print("Message was sent, you can send another one");
                } else {
                     print("Message wasn't sent, please check that you have changed emails in the bottom");
                }

header("location: kuileyshi-contact-form-namecheap-html45-index:html");
  }
   
