# PatreonAPIDockerOS
Open source docker file with introductions and examples on how to use this patreon api authentication server 

# software planning 
This section briefly explains the entire software process.

Once the Auth-Server has been deployed, it can be accessed via the URL.
The default route will be /auth. A landing page will be displayed there, which should regulate general data processing matters and require explicit consent.
After consent, the actual authentification begins.

For this purpose, the client sends a request with a unique ID to the server. The server then checks whether a token exists in this request. This is only the case if it is a new request with a valid token.

If no token exists, the server redirects directly to Patreon and leaves everything else to Patreon. After the Patreon part is completed, the auth server receives an auth token back from Patreon. This allows the server to request the required data. This is just a read-only access to which campaigns the token-owner (user) follows and the pledge_amount he has spend there.


This answer is stored on the server for 15 minutes or until it is accessed.

The client is given feedback, that an answer is available. 

The client then requests and gets the response from the Server with the requested informations (pledgeAmount, e.g.)


![Fow Chart](https://github.com/samuelsaengerboeger/PatreonAPIDockerOS/blob/samuelsaengerboeger-patch-1/PatreonAblauf.jpg
)


![Communication Chart](https://github.com/samuelsaengerboeger/PatreonAPIDockerOS/blob/samuelsaengerboeger-patch-1/Ablauf%20Kommunikation.jpg)
# ToDo:
<ul>
<li> Landingpage
<li> Request Class with id and timestamp
<li> Delete Request after 15 min not fetched
<li> code Refactoring
<li> hardcoded vars into env 
</ul>
