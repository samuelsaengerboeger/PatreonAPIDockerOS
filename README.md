# PatreonAPIDockerOS
Open source docker file with introductions and examples on how to use this patreon api authentication server 

# software planning 
This section briefly explains the entire software process.

Once the Auth-Server has been deployed, it can be accessed via the URl.
The default route will be /auth. A landing page will be displayed there, which should regulate general data processing matters and require explicit consent.
After consent, the actual authentication begins.
For this purpose, the client sends a request with a unique ID to the server. The server then checks whether a token exists in this request. This is only the case if it is a new request with a valid token.
If no token exists, the server redirects directly to Patreon and leaves everything else to Patreon. After the Patreon part is completed, our auth server receives an auth token back from Patreon. This allows us to request the required data. This is actually just read-only access to the campaigns the user follows and the donation amount he has deposited there.
The server then checks whether our campaign ID is available and prepares a response. This is stored on the server for 15 minutes or until it has been read for the first time. Then it is deleted

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
