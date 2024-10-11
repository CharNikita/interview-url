# Technical Assignment: URL Shortening Service Implementation

## Description:

You need to implement a REST API service for shortening long URLs.
The service should allow the user to submit a long URL and receive its shortened version,
as well as redirect to the original URL when accessing the shortened link.
> Most likely, you will not be able to complete the entire task in the allotted time — this is normal,
> prioritize the points as you think is right.
> Use any tools you are used to during the task — searching for information on the Internet is not prohibited :)

## Functional requirements:

### 1. API functionality:

- **POST /shorten** — create a short link:
    - Accepts a JSON request with a field for the original URL.
    - Returns the short link in JSON format.
    - If the URL already exists in the system, return the existing short link.

- **GET /{shortUrl}** — redirect by short link:
    - When accessing the short link, a redirect to the original URL should occur.
    - If the link has expired or is not found, return a 404 error.

- **GET /info/{shortUrl}** — get information about the shortened link:
    - Returns information about the original URL, creation date, and expiration date.
    - Returns 404 if the link is not found or has expired.

- **DELETE /{shortUrl}** — delete a short link:
    - Deletes the short link and original URL record from the system.

### 2. Error handling requirements:

- Return status 400 if the original URL is invalid.
- Return status 404 for non-existent or expired short links.

## Technical requirements:

### 1. Spring Boot:

- Use Spring Boot to create the application.

### 2. Storage:

- Use any in-memory storage of your choice for storing the URLs.

### 3. Short link generation:

- For generating the short link, you can use an alphanumeric character set. The link should have a fixed length (e.g.,
  6-10 characters).
- It is acceptable to use existing libraries for generating unique strings.

### 4. Controllers, Services, and Repositories:

- Separate business logic from API and data access.

### 5. Validation:

- Ensure that the original URL is valid and handle possible errors.

### 6. API Documentation:

- Use Swagger to document the REST API.

### 7. Testing:

- Write unit tests for the main functions (creating a short link, redirection, fetching information).
- Use JUnit and Mockito for testing.

## Additional requirements:

1. Implement support for custom short links where the user can specify a short identifier.
2. Add authorization for managing links (e.g., JWT tokens for creating and deleting).
3. Add the ability to set the expiration date when creating a link.
4. Implement a metrics system to track the number of clicks on the short link.
5. Add stats for link usage

---
