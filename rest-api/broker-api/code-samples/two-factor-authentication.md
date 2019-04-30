# Two-Factor Authentication

### Two-Factor Authentication 

{% tabs %}
{% tab title="Python" %}
```python
import requests

class EtnaAPIRequest:

	baseURL = "https://priv-api-et-demo-prod.etnasoft.us/api/"
	EtAppKey = "Et App Key from the BO Companies widget"

	token = 'uninitialized'

	username = "your username"
	password = "your password"

	def simpleAuth(self):
		authenticationRequest = requests.post(self.baseURL + 'token', 
											  headers = {"Accept" : "application/json", "Et-App-Key" : self.EtAppKey, "Username":self.username, "Password":self.password})

		print('Authorization status code: ' + str(authenticationRequest.status_code) + '\n')

		try:
			responseJSON = authenticationRequest.json()
			print(responseJSON)
			self.token = "Bearer " + responseJSON["Token"]
			return responseJSON
		except:
			return "No response"


	#2-factor authentication
	def twoFactorAuthentication(self, verificationCode):

		secondRequest = requests.post(self.baseURL +  'token',
									  headers = {"Accept" : "application/json", 
									  			 "Et-App-Key" : self.EtAppKey, 
									  			 "VerificationCode" : verificationCode,  #the code from email or SMS
									  			 "Username":self.username, 
									  			 "Password":self.password,
									  			 "Authorization":self.token})
		print('Authorization status code: ' + str(secondRequest.status_code) + '\n')
		print("Old bearer token: " + self.token)

		try:
			responseJSON = secondRequest.json()
			print(responseJSON)
			#Replacing the interim token with the final token
			self.token = "Bearer " + responseJSON["Token"] 
			return responseJSON
		except:
			return "No response"

sampleRequest = EtnaAPIRequest()

#performing the first step of authentication
sampleRequest.simpleAuth()

#retrieving the verification code from the user
code = input("Enter the verification code: ")

#performing two-factor authentication
sampleRequest.twoFactorAuthentication(code)
```

Similar to the regular authentication, in this example we perform the initial authentication with the username and password, and in response we receive the interim authorization token which we'll need to provide in the second request along with the verification code from email or SMS.
{% endtab %}
{% endtabs %}

#### CURL \(Two-Factor Authentication\)

```text
curl -X POST --header 'Content-Type: application/x-www-form-urlencoded' --header 'Accept: application/json' --header 'Username: yourUsername' --header 'Password: yourPassword' --header 'Authorization: Bearer yourToken' --header 'Et-App-Key: yourEttAppKey' --header 'Content-Length: 0' 'https://priv-api-et-demo-prod.etnasoft.us/api/token'
```
