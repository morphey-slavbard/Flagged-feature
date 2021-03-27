Readme.txt
Coded in Javascript React

Darren Webster
dmorphey@gmail.com

How to test the code

1) Create an Optimizely Account - https://www.optimizely.com/rollouts-signup
2) Install React-app - https://create-react-app.dev/docs/getting-started/ Call it flag-feature-test-app
3) Install React SDK  npm install --save @optimizely/react-sdk
4) Add the file from this github called app.JS to the src folder and overwrite
5) Create the feature flag in the optmizely dashboard 
	Key = feature-flag-test
6) Create a default Variable in the optmizely dashboard 
	Variable Key = amount
	Default Value = 10
7) Create two Variations in the optmizely dashboard 
	twenty sollar variation - = amount = 20
	ten dollar price - = amount = 10
8) Create an Event in the optmizely dashboard 
	Event key = making_purchase
9) Enable feature-flag-test Devlopment enviroment
10) Add a new rule to development = A|B testing
	Keep name and key as is
	Audience = everyone
	Percentage included = 100%
	Metrics = making_purchase
	Deliver variations
		ten dollar price = 50%
		twenty dollar variation 50%
	Save
11)Restart and rerun the react app. from the terminal cntrl + c to restart then npm start
12) The tab shoulld refresh with the final display
13 Open the console.

The console should display the following
1) DECISION_SERVICE
2) OPTIMIZELY - tracking
3) OPTIMIZELY - Got variable
4) OPTIMIZELY - feature flag is enabled.

How to test different users and the A|B testing
1) Once everything is built and running
2) Go to line 38  of app.js and update the user ID to something new e.g. user123456
3) refresh and check console and display

Notes:

Please excuse variable names
Choose React as I wanted the interface/ui for testing.
There are screenshots of the optmizely dashboard configuration in this github.
If my notes have an error please check these lines of code for important names that link with the dashboard.
TRACKER = optimizely.track('making_purchase')
FLAG FEATURE = <OptimizelyFeature feature="feature-flag-test">
DEFAULT VARAIBLE = {(enabled, variables) => (`Got a discount of $${variables.amount}`






