# What are APIs?

- **A**pplication **P**rogramming **I**nterfaces
- Simplified interfaces for backend interaction
- Allows resources and services to be shared across applications, organizations, devices

# How do APIs work?

### The Restaurant Analogy: A Digital Diner

In a restaurant, there are the following roles:
- The Customer who  **requests**  an order,
- The Waiter who  **carries**  the order to the Chef, and
- The Chef who **prepares**  the order.

These roles translate to the following:
- The **client (browser/app)** requests data or the execution of a service
- The **API** delivers the request to the backend
- The **server** is where the request is processed

# Postman API 102: Creating Workflows with APIs

### By the end of the workshop, you will:
- Have built a song recommender workflow that looks [like this](https://drive.google.com/file/d/106hDj2H-NjLiH4Ddi6E3bJ0M9oSxMNV1/view?usp=sharing)
- Be able to use OAuth 2.0 Authorization to make requests
- Be able to call a real-world REST API
- Be able to use variables and chain multiple API calls to build a workflow
- Be able to visualize response data

## Step-by-Step Walkthrough
### Step 1: Set-Up
- Create a [Spotify account](https://developer.spotify.com/dashboard) to use the [Spotify Web API](https://developer.spotify.com/documentation/web-api)
- Use [Postman for Web](https://www.postman.com/) to avoid downloading any software

### Step 2: Start a New Collection
- [ ] In any workspace, start a **new collection** and name it "API 102: Building Workflows with APIs"

### Step 3: Set Up Authorization
- From the collection folder **APIs 102: Building Workflows with APIs**, visit the **Authorization** tab.
- [ ] Make sure **Type** is set to **OAuth 2.0,** and **Add auth data** to is set to **Request Headers**.
- To create a Spotify app, login to the Spotify Developer Dashboard [here](https://developer.spotify.com/dashboard).
- From the Dashboard, select **Create an app**.
- [ ] Give the new app a **name** (ex: “Postman Song Recommender”), a **description**, check the checkboxes, and select **Create**.
- On the newly created app page, click *“Show client secret”* to reveal the **Client ID** and **Client Secret**.
- [ ] Open the **Variables** tab in Postman and paste these values into **CLIENT_ID** and **CLIENT_SECRET** under the **CURRENT VALUE** column only.

	> Adding sensitive data under the "CURRENT VALUE" column protects values from being accidentally viewed or being shared publicly.

- [ ] In the collection **Authorization** tab under **Configure New Token**, give the token a nickname (ex: SPOTIFY). Ensure the **Grant Type** is set to **Authorization Code**.
- [ ] From the collection’s **Authorization** tab, find and copy the **Callback URL**.
- Navigate to the Spotify dashboard for your "postman song recommender" app and click **Edit Settings**.
- Add the **Callback URL** copied from Postman to the **Redirect URL** field in the app settings and click **Add**.
- [ ] Scroll down and click **Save** to update settings.
- [ ] In Postman, from the collection Authorization tab, make sure  
    - Auth URL is set to https://accounts.spotify.com/authorize.
    - Access Token URL is set to https://accounts.spotify.com/api/token.
 
### Step 4: Obtain an Access Token
- From the collection **Authorization** tab, click **Get New Access Token**.
- [ ] Follow any login dialog. If successful, click “Proceed”. If something went wrong, ensure nothing is missing from the configuration in the above steps.
- A dialog with the new access token will appear. Select **Use Token** in the upper right.
- [ ] You should now see a token under **Access Token** in the collection **Authorization** tab.
	> If this token expires during your demo session, you can obtain a new token any time by clicking Get New Access Token and following the dialogs again.

### First Request: Get Track ID
- [ ] In the **demo > workflow folder**, add a new request called **get track id**.
- [ ] In the **get track id** request, set the request URL to: `GET {{baseUrl}}/search`, where *baseUrl* is defined as a collection variable with a value of the Spotify API base URL: https://api.spotify.com/v1.
	> The double curly braces {{}} allow us to interpolate this variable in our request. You can hover over the orange variable to see the resolved value.

- [ ] Add query params in either the Params tab or directly in the URL.
	```
	q=track:{{track}}+artist:{{artist}}
	type=track
	```
- [ ] Add `track` and `artist` as collection variables on the **APIs 102: Building Workflows with APIs > Variables** tab. Give the variables a value for a popular song (ex: track=dancing queen, artist=abba).
- Return to the **get track id** request and hit **Send**.
- [ ] The response from Spotify should be an object with a key “tracks” that contains an array called “items”. Each item represents a track, with info about the artist, album, track name, trackId etc.
- To save these values as collection variables for future use, open the **Tests** tab on the **get track id** request.
	> We want to get the trackId for the song we searched for. The trackId will help us seed our song recommendations in the next request.

	- [ ] Paste in this Node code in the **Tests** tab to get the first track and save its trackId to a collection variable.
	```javascript
	// get the JSON response body 
	const body = pm.response.json();
	
	// get first search result track 
	const firstTrack = body.tracks.items[0]
	
	// save the trackId as a collection variable to use in future request 
	const trackId = firstTrack.id;

	pm.collectionVariables.set("trackId", trackId);
	```
- Hit **Send** on the **get track id** request to call the API again. This time the code in the **Tests** tab will be executed when the response arrives.
- After making the request, show the collection variables on **APIs 102: Building Workflows with APIs**. There should now be a **trackId** with values.

### Second Request: Get Recommendations
- [ ] Create a second request in the **workflow folder** called **get recommendations**.
- This will be a GET request to the [Spotify Browse API/``recommendations`` endpoint](https://developer.spotify.com/documentation/web-api). Show the documentation, highlighting the ``seed_tracks`` query parameter.
- [ ] Set the request URL for the **get recommendations** request to:
`GET {{baseUrl}}/recommendations?seed_tracks={{trackId}}`
- **Send** the request.
- Explore the response. The response is an object with key “tracks” that has a value of an array of recommended tracks based on the seed `trackId`.
 
### Visualizing the Recommendations
- Open the **Tests** tab on the **get recommendations** request.
- [ ] Add the below script to parse the response body and get the top three recommendations:
	```javascript
	// parse response
	const body = pm.response.json()

	// get the first three recommended tracks
	const topThreeRecs = body.tracks.slice(0,3)

	console.log(topThreeRecs)
	```
- **Save** the changes and **Send** the request again.
- Open the **Postman console** from the bottom left of the window.
- You should see the logged `topThreeRecs` in the console.
- [ ] Return to the script in the **Tests** tab. Remove the `console.log()` statement.
- [ ] Add this code to the script to retrieve the **track** collection variable that was originally the search term:
	```javascript
	// get track name from collection variables
	const track = pm.collectionVariables.get(track)
	```	
- [ ] Add an HTML template and use Postman's `pm.visualizer.set()` function to apply the template to Postman's Visualizer tab.
	```javascript
	// define an HTML template with variables
	// use {{#each var}}{{/each}} to iterate through an array of data
	const template = `
	<h3>Discover new tunes!</h3>
	<p>If you like "{{track}}", you'll love:</p>
	<ul> 
	 {{#each topThreeRecs}}
		    <li>{{name}} - <a href="{{external_urls.spotify}}">Play</a></li> 
	 {{/each}}
	</ul> 
	`
	// set visualizer and pass in variables 
	pm.visualizer.set(template, { topThreeRecs, track })
	```
- [ ] The full script in the **Tests** tab should look like this:
	```javascript
	const body = pm.response.json()
	const topThreeRecs = body.tracks.slice(0,3)
	const track = pm.collectionVariables.get(track)

	const template = `
	<h3>Discover new tunes!</h3>
	<p>If you like "{{track}}", you'll love:</p>
	<ul> 
	 {{#each topThreeRecs}}
		    <li>{{name}} - <a href="{{external_urls.spotify}}">Play</a></li> 
	 {{/each}}
	</ul> 
	`
	pm.visualizer.set(template, { topThreeRecs, track })
	```
- **Save** the changes. **Send** the **get recommendations** request again and open the **Visualizer** tab.
- You can listen to the suggested songs quickly from Postman:
	- Postman for web: right-click the “Play” link to open in new tab
	- Postman for desktop: click the “Play” link

### Running Multiple Requests
- Click the **APIs 102: Building Workflows with APIs** collection and open the **Variables** tab.
- Update the ``track`` and ``artist`` variables to a new song.
- [ ] Click **Save** to save the new variable values.
- To run all the requests in the workflow folder, click the **workflow folder**, then **Run**.
- [ ] Click **Run APIs 102: Building Workflow...**.
- If all goes well, you will have **two** ``status 200`` responses from your requests. The collection variables have now been updated.
- To view the visualized response with these new variables, **Send** the **get recommendations** request one more time and open the **Visualize** tab.

## Assignment

That's it!

Fork the official workshop collection, and complete and submit the “your turn!” challenge as an assignment.

## Challenge Prompt

The blogger wants more accurate song recommendations based on artists they like. Allow the blogger to enter **three artists** (artist1, artist2, artist3) as collection variables to generate **5 song recommendations** in the "get recommendations" request.