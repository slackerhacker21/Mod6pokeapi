HTML Structure
Input and Button:
An <input> element with id="pokemon-input" allows users to type a Pokémon name (e.g., "pikachu") or ID (e.g., "25").
A <button> with id="search-button" triggers the search when clicked.
Result Display:
A <div> with id="pokemon-info" contains a <p> for the name (id="pokemon-name") and an <img> for the image (id="pokemon-image").
Initially, this div has the hidden class to keep it invisible until a successful search.
Error Message:
A <p> with id="error-message" displays error messages and is also hidden initially with the hidden class.
Bonus (Optional):
A commented <p id="pokemon-type"> can be uncommented to display the Pokémon’s type.
CSS Styling
.hidden Class: Sets display: none to hide elements like the result div and error message when not needed.
Basic Styling: Centers the Pokémon info and limits the image size to max-width: 200px for a clean layout.
JavaScript Functionality
Element Selection: Uses document.getElementById to select the input, button, result div, name element, image element, and error element for manipulation.
Event Listener: Attaches a click event to the search button to call the searchPokemon function.
Asynchronous Search Function (searchPokemon):
Input Handling: Retrieves the input value and trims whitespace. Converts it to lowercase since PokeAPI expects names in lowercase (e.g., "Pikachu" becomes "pikachu").
Initial State: Hides both the result div and error message to clear previous results or errors.
Empty Input Check: If the input is empty, displays an error message and exits the function.
API Request: Uses fetch with await to request data from https://pokeapi.co/api/v2/pokemon/${inputValue.toLowerCase()}.
Response Handling:
If response.ok (status 200-299), parses the JSON data, capitalizes the Pokémon’s name (e.g., "pikachu" to "Pikachu"), sets the name and image in the DOM, and shows the result div.
If not ok, checks for a 404 status ("Pokémon not found") or other errors ("An error occurred").
Error Handling: A try-catch block catches network errors or other exceptions, displaying a connection failure message.
Helper Functions:
showError(message): Sets the error message text and makes it visible by removing the hidden class.
capitalize(str): Capitalizes the first letter of the Pokémon’s name for better readability.
Bonus (Optional): Commented code can be uncommented to extract and display the Pokémon’s types from data.types, joining them with commas (e.g., "Type: Electric" for Pikachu).
How It Works
User Input: Type "pikachu" or "25" and click "Search".
Successful Search: Displays "Pikachu" and its image.
Invalid Search: Type "9999" or an invalid name, and see "Pokémon not found."
Empty Input: Click "Search" without typing, and see "Please enter a Pokémon name or ID."
Network Error: If offline, see "Failed to fetch data. Please check your connection."
Meeting the Requirements
Objective: Demonstrates JavaScript objects (API response), DOM manipulation, and asynchronous JavaScript (async/await).
Instructions:
Input box and button trigger an asynchronous API request to PokeAPI.
Displays the Pokémon’s name and image dynamically.
Handles errors with a clear message for invalid searches.
Technical Requirements: Uses vanilla JavaScript, Fetch API with async/await, and updates the DOM.
Deliverables: Provides a working web page fulfilling the assignment.
Evaluation Criteria:
Successfully fetches and displays data.
Code is clean and readable with comments.
Interface is simple and provides feedback for invalid searches.
Bonus Feature
To include the Pokémon’s type, uncomment the <p id="pokemon-type"> in the HTML and the type-related lines in the JavaScript. This will display, for example, "Type: Electric" for Pikachu or "Type: Grass, Poison" for Bulbasaur.

This solution provides a functional, user-friendly web page that meets all assignment requirements, with the option to easily extend it for the bonus feature. You can save this code in an HTML file, open it in a browser, and test it with various Pokémon names or IDs!
