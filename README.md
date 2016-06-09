# UptimeFlare
A PHP web hook to handle down notifications from uptimerobot. If a DOWN notification is received, it'll change the A record of a domain on cloudflare to a backup IP set by you.

License: MIT   
Dependencies: Web Server, PHP, php-curl lib   

Setup: <br>
1. I suggest you rename the php file to something obscure. <br>
2. Add / change the global vars section. It consists of credentials and other information that needs to be modified to your needs.  <br>
3. Upload this script to the desired server, make sure the script is accessible via the internet. <br>
4. On uptimeRobot: <br>
	Create a new alert contact and select web hook. For url, put in the url to the php script and add "?key=YourKeySetInThePHPScript&".  <br>
	If my $key was set to <b>HelloWorld</b> and I renamed my script to <b>monitorUP.php</b> which is accessible via <b>127.0.0.1</b>, then for the url I would put <br>
	<i>http://127.0.0.1/monitorUP.php?key=HelloWorld&</i> Make sure you have the <b>&</b> at the end.  <br>
5. Add this alert type to your websites. It's recommended that you have more than the PHP hook as an alert type (such as email notification), so you can switch it back to the primary server once it's up. This should be done manually (login to cloudflare and change the IP) because there might be inconsistencies between the primary and the backup server, which requires manual intervention.

With this setup, a website shouldn't have a downtime of more than ~6 minutes, assuming your DNS provider does not cache queries.
<br><br>
Credits: <a href="http://twitter.com/blackdotsh/">Blackdotsh</a>.
<br><br>

