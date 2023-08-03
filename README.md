// File: frontend/landing_page.js

// Function to add a city card to the DOM
function addCityToDOM(id, city, description, image) {
  // Create a new city card element
  const cityCard = document.createElement('div');
  cityCard.classList.add('col-md-4', 'mb-4');

  // Create the card body
  const cardBody = document.createElement('div');
  cardBody.classList.add('card', 'h-100');

  // Create the image element
  const imgElement = document.createElement('img');
  imgElement.src = image;
  imgElement.classList.add('card-img-top');

  // Create the card body content
  const cardBodyContent = document.createElement('div');
  cardBodyContent.classList.add('card-body');

  // Create the city name heading
  const cityNameHeading = document.createElement('h5');
  cityNameHeading.classList.add('card-title');
  cityNameHeading.textContent = city;

  // Create the city description paragraph
  const cityDescriptionParagraph = document.createElement('p');
  cityDescriptionParagraph.classList.add('card-text');
  cityDescriptionParagraph.textContent = description;

  // Create the adventure link
  const adventureLink = document.createElement('a');
  adventureLink.classList.add('btn', 'btn-primary');
  adventureLink.textContent = 'View Adventures';
  adventureLink.href = `pages/adventures/?city=${id}`;
  adventureLink.id = id; // Set the "id" attribute to the city id parameter

  // Append all the elements to their respective parents
  cardBodyContent.appendChild(cityNameHeading);
  cardBodyContent.appendChild(cityDescriptionParagraph);
  cardBodyContent.appendChild(adventureLink);

  cardBody.appendChild(imgElement);
  cardBody.appendChild(cardBodyContent);

  cityCard.appendChild(cardBody);

  // Get the 'data' div element and append the city card to it
  const dataDiv = document.getElementById('data');
  dataDiv.appendChild(cityCard);
}

// Now, you can call the init() function to start fetching cities and adding them to the DOM
init();


