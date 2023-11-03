# ft_transcendence

## React

- https://react.dev/learn/passing-props-to-a-component
- https://legacy.reactjs.org/docs/hooks-overview.html :
	- Hooks are functions that let you “hook into” React state and lifecycle features from function components. Hooks don’t work inside classes — they let you use React without classes.
- https://react.dev/reference/react/hooks
- https://www.simplilearn.com/what-is-reactjs-props-article :
	- In ReactJS props (properties) are a type of object where the value of attributes of a tag is stored. Its working functionality is quite simmilar to HTML attributes
- [React State Vs Props](https://www.youtube.com/watch?v=IYvD9oBCuJ) :
	- Props are like argument to your function that you pass into a component, props are handled outside of a component
	- State is handled inside of a component
- [6 React Interview Questions You Have to Know](https://www.youtube.com/watch?v=mXxsjzgD3CI) :
	- State is a JS variable which whenever its value updates it will trigger a rerender of your react app so that it will display the new value in the UI 
	- State Management : when you have states you have a hierarchy of components and you have to have access to a state from a parent component on a grant child component, the only way to do that is by passing it through the child component (the middle component, which does not even need the state)
	- Rules to follow when using hooks : only call hooks on the highest level AND inside functional components. Hooks are meant to implement all of the functionalities that class components had for functional components
	- Design patterns : the MVC model, devide project into three components : model, views and controllers
- [YT The Magic of TypeScript Decorators](https://www.youtube.com/watch?v=O6A-u_FoEX8) :
	- A decorator is a function that allows you to hook into your source code and either extend the functionality of it or annotate it with metadata
	- Can be decorated : class definition, properties, methods, accessors, parameters

## OAuth 2.0

- Authentication using NestJS (JWT) :
	- https://docs.nestjs.com/security/authentication

- OAuth 2.0
	- https://api.intra.42.fr/apidoc/guides/getting_started
	- https://api.intra.42.fr/apidoc/guides/web_application_flow
	- https://www.passportjs.org/packages/passport-42/
		- Verify Callback :
			- https://www.youtube.com/watch?v=-mir74x3f5Y : the coordinator passed the callback to the dough getter
			- https://www.youtube.com/watch?v=xHneyv38Jro : Asynchronous programming : a form of computer control timing protocol in which a specific operation begin upon receipt of an indication (signal) that the preceding opeation has been completed. You send the entire function `function test(callback) { callback(); } function myfun() { return 1; } test(myfun);` THEN you call it
			- https://www.youtube.com/shorts/tlUoKHCnUtQ : functions are like variables, they're objects

- [YT Authentication: It’s Easier Than You Think](https://www.youtube.com/watch?v=h6wBYWWdyYQ) :
	- Auth happens in the server (on requests)
	- The client make requests and requests can be authenticated AND authorized
	- If you need to know who the user is make a request (/api/me, /api/current-user)
	- Use a cookie to authenticate the user and use db to authorize their behaviors
- [YT Auth Does NOT Have To Be Hard](https://www.youtube.com/watch?v=mL8EuL7jSbg) :
	- Authentication : proving you are who you say you are
	- Authorization : the permissions you have
	- Server aftr receiving user/pwd will create a session which is a unique id associated with User. On the client, it saves uuid in a cookie : everytime you send request, the cookie with John's uuid will be sent
	- 6:45 : secure your cookie ! Dev Tab: application > cookies > session. Makesure you securely store the session id, if someone else has access to it they can be logged in as you
	- Logging out automatically by removing the session from the server
- [YT Difference between cookies, session and tokens](https://www.youtube.com/watch?v=GhrvZ5nUWNg):
	- On server : id, username, hashedpwd
	- Once server verifies credentials, it creates session_id, in a form of a cookie which has been traded with your username and pwd. This session_id is a unique identifier for your login session
	- Session_id only in a cookie stored on your computer file system
	- When log out, sessionwill be invalidated in db AND server instructs the brower to delete the cookie containing the session id
	- Long-lived session vs short-lived session (5 min before logout automatically)
	- Cookies can be modified by the client, so they can't be trusted by the server
	- JWT = Jot
- https://www.youtube.com/watch?v=q8tZQxT4YPU
- [YT: OAuth 2 explained in simple terms](https://www.youtube.com/watch?v=ZV5yTm4pT8g) :
	- Give a key to user to access specific information
	- User instruct Trans to login, Trans send #clientID and #scope to 42auth through the Authorize Service
	- 42 auth Request Permission dialog to user and user approves request
	- Once permission granted #authorizationcode to trans
	- Trans gets access token to 42 auth (#authorizationcode #clientid #clientsecret, the later one only shared bw trans and 42auth)
	- 42auth access token to trans
	- Finally trans gets photos to 42ressource
- [YT What is OAuth2.0 (in plain English)](https://www.youtube.com/watch?v=LD3NCUP5hW4):
	- Once Authorization server ok,go to redirect URI '/callback' and exchange auth code for access token
	- Once access token given by authorization server, callback can access resources from resource server using access token 
- [YT NestJS & GoogleOAuth2 with Passport](https://www.youtube.com/watch?v=OitgkKTxht4):
	- 27
