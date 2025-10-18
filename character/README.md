# Character: Query a Specific Character by ID

Objective

- Write a GraphQL query to retrieve a specific character’s details by ID.

Endpoint

- Use your provided GraphQL endpoint.
- https://rickandmortyapi.com/graphql

Instructions

- For each ID in 1, 2, 3, 4:
  - Create a .graphql file containing a query that selects: id, name, status, species, type, gender.
  - Execute the query and save the raw response into the matching -output.json file.
- Keep responses limited to the requested fields.

Repo structure

- alx-graphql-0x00/
  - character/
    - README.md
    - character-id-1.graphql
    - character-id-1-output.json
    - character-id-2.graphql
    - character-id-2-output.json
    - character-id-3.graphql
    - character-id-3-output.json
    - character-id-4.graphql
    - character-id-4-output.json

# Character: Write a Query to Get a List of All Characters

Objective

- Create GraphQL queries that retrieve a paginated list of all characters for pages 1, 2, 3, and 4.
- Select subfields: id, name, status, image.
