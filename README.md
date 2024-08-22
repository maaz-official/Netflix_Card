
```markdown
# Netflix-Style Card Component in React

This repository contains a tutorial and example code for creating a dynamic Netflix-style card component using React. The card component displays movie and series details, including the title, rating, summary, and a "Watch Now" button that redirects users to the streaming page.

## Project Overview

The project simulates an API using a JSON file containing mock data for movies and series. It dynamically generates React cards based on this data. Each card features an image, title, rating, summary, type, year, and a link to watch the content.

By the end of this tutorial, you will have a Netflix-style interface with data-driven cards.

## Prerequisites

- Basic knowledge of React and JavaScript.
- A React development environment set up (using `create-react-app` or similar).

## Getting Started

### 1. Clone the Repository

```bash
git clone https://github.com/maaz-official/netflix-card.git
cd netflix-style-card-component
```

### 2. Install Dependencies

Ensure you have Node.js installed, then run:

```bash
npm install
```

### 3. Run the Development Server

Start the React development server with:

```bash
npm start
```

Open your browser and navigate to `http://localhost:3000` to see the component in action.

## Project Structure

- `src/api/FilmData.json`: Contains mock data for movies and series.
- `src/components/NetflixCard.js`: The main React component for displaying the Netflix-style cards.

## Step-by-Step Tutorial

### Step 1: Creating the JSON Data

Create a file named `FilmData.json` in the `src/api` directory with the following format:

```json
[
  {
    "id": 1,
    "title": "Inception",
    "description": "A thief who steals corporate secrets through the use of dream-sharing technology...",
    "image": "inception.jpg",
    "rating": "8.8",
    "year": "2010",
    "type": "Movie",
    "watchUrl": "https://www.netflix.com/watch/70131314"
  },
  {
    "id": 2,
    "title": "The Matrix",
    "description": "A computer hacker learns from mysterious rebels about the true nature of his reality...",
    "image": "matrix.jpg",
    "rating": "8.7",
    "year": "1999",
    "type": "Movie",
    "watchUrl": "https://www.netflix.com/watch/20557937"
  }
]
```

### Step 2: Creating the Netflix Card Component

Create a `NetflixCard.js` file in the `src/components` directory with the following code:

```jsx
import React from 'react';
import FilmData from '../api/FilmData.json';

export const NetflixCard = () => {
  return (
    <ul style={{ listStyle: 'none', padding: 0, display: 'flex', flexWrap: 'wrap', gap: '20px' }}>
      {FilmData.map((film) => (
        <li key={film.id} style={{ border: '1px solid #ccc', borderRadius: '10px', padding: '20px', width: '250px', boxShadow: '0px 4px 6px rgba(0,0,0,0.1)' }}>
          <div style={{ textAlign: 'center' }}>
            <img src={film.image} alt={film.title} style={{ width: '100%', height: 'auto', borderRadius: '10px' }} />
            <h2 style={{ fontSize: '18px', margin: '15px 0' }}>{film.title}</h2>
            <p><strong>Rating:</strong> {film.rating}</p>
            <p><strong>Year:</strong> {film.year}</p>
            <p><strong>Type:</strong> {film.type}</p>
            <p style={{ fontSize: '14px', color: '#555' }}>{film.description}</p>
            <a href={film.watchUrl} target='_blank' rel='noopener noreferrer' style={{ textDecoration: 'none' }}>
              <button style={{ backgroundColor: '#e50914', color: '#fff', padding: '10px 20px', border: 'none', borderRadius: '5px', cursor: 'pointer' }}>
                Watch Now
              </button>
            </a>
          </div>
        </li>
      ))}
    </ul>
  );
};
```

### Step 3: Styling the Cards

The example uses inline styles for simplicity. You can extend the styling using CSS or styled-components.

## Optional: Connecting the API

You can replace static JSON data with a real API call using `fetch` or `axios` to load data dynamically.

## Conclusion

This Netflix-style card component provides a great starting point for building responsive and data-driven UIs in React. Enhance this project further by integrating real APIs, adding search and filter functionalities, and experimenting with different UI designs.

For more React tutorials and project ideas, check out the [LazzyCodeTech YouTube channel](https://www.youtube.com/@lazzycodetech).

Happy coding, and enjoy creating your Netflix-inspired UI!

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

```
