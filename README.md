# MoviesDatabase API Integration

This project connects with the MoviesDatabase API to fetch movie data including titles, genres, actors, release dates, and more. It provides a clean interface to explore movie information programmatically.

---

## API Overview

The MoviesDatabase API provides access to a vast collection of movie and TV show metadata. Key features include:

- Search for movies, TV shows, and people (actors, directors).
- Retrieve detailed movie information including cast, genres, and ratings.
- Get popular, trending, or top-rated movies.
- Access posters, trailers, and image assets.

---

## Version

**API Version:** v3

---

## Available Endpoints

Here are some commonly used endpoints:

| Endpoint              | Description                                   |
| --------------------- | --------------------------------------------- |
| `/search/movie`       | Search for movies by title keyword.           |
| `/movie/{movie_id}`   | Get full details for a specific movie.        |
| `/movie/popular`      | Get a list of currently popular movies.       |
| `/genre/movie/list`   | Fetch all available movie genres.             |
| `/person/{person_id}` | Get details about a person (actor, director). |

---

## Request and Response Format

All requests should be made via HTTPS using the GET method. Responses are in JSON format.

## Authentication

- All API requests require an API key.
- You can sign up for a free API key at The Movie DB API.
  - Include the key as a query parameter: ?api_key=YOUR_API_KEY
  - Alternatively, include it in the request header:
  - Authorization: Bearer YOUR_ACCESS_TOKEN

## Error Handling

| Status Code             | Meaning                     | Fix                                            |
| ----------------------- | --------------------------- | ---------------------------------------------- |
| `401 Unauthorized`      | Missing or invalid API key  | Make sure your API key is correct and included |
| `404 Not Found`         | The resource does not exist | Check your endpoint or resource ID             |
| `429 Too Many Requests` | Rate limit exceeded         | Wait before making more requests               |

## Usage Limits and Best Practices

- Rate Limit: 40 requests every 10 seconds (per IP)
- Best Practices:
- Cache responses to reduce unnecessary API calls
- Use pagination when listing movies (page query parameter)
- Handle errors gracefully in your application
- Don’t hardcode your API key — use environment variables
