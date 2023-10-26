# ft_transcendence

## OAuth 2.0

- [OAuth 2 explained in simple terms](https://www.youtube.com/watch?v=ZV5yTm4pT8g) :
	- Give a key to user to access specific information
	- User instruct Trans to login, Trans send #clientID and #scope to 42auth through the Authorize Service
	- 42 auth Request Permission dialog to user and user approves request
	- Once permission granted #authorizationcode to trans
	- Trans gets access token to 42 auth (#authorizationcode #clientid #clientsecret, the later one only shared bw trans and 42auth)
	- 42auth access token to trans
	- Finally trans gets photos to 42ressource
- https://www.passportjs.org/packages/passport-42/
	- Verify Callback :
		- https://www.youtube.com/watch?v=-mir74x3f5Y : the coordinator passed the callback to the dough getter
		- https://www.youtube.com/watch?v=xHneyv38Jro : Asynchronous programming : a form of computer control timing protocol in which a specific operation begin upon receipt of an indication (signal) that the preceding opeation has been completed. You send the entire function `function test(callback) { callback(); } function myfun() { return 1; } test(myfun);` THEN you call it
		- https://www.youtube.com/shorts/tlUoKHCnUtQ : functions are like variables, they're objects
- https://api.intra.42.fr/apidoc/guides/getting_started
- https://api.intra.42.fr/apidoc/guides/web_application_flow
- https://www.youtube.com/watch?v=q8tZQxT4YPU

