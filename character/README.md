# Character: Write a Query to Get a List of All Characters

Objective

- Create GraphQL queries that retrieve a paginated list of all characters for pages 1, 2, 3, and 4.
- Select subfields: id, name, status, image.

Repository Layout

- GitHub repository: alx-graphql-0x00
- Directory: character
- Files:
  - README.md
  - characters-page-1.graphql
  - characters-page-1-output.json
  - characters-page-2.graphql
  - characters-page-2-output.json
  - characters-page-3.graphql
  - characters-page-3-output.json
  - characters-page-4.graphql
  - characters-page-4-output.json

GraphQL Queries
Save one file per page with the following content.

characters-page-1.graphql

```
query CharactersPage1 {
    characters(page: 1) {
        results {
            id
            name
            status
            image
        }
    }
}
```

characters-page-2.graphql

```
query CharactersPage2 {
    characters(page: 2) {
        results {
            id
            name
            status
            image
        }
    }
}
```

characters-page-3.graphql

```
query CharactersPage3 {
    characters(page: 3) {
        results {
            id
            name
            status
            image
        }
    }
}
```

characters-page-4.graphql

```
query CharactersPage4 {
    characters(page: 4) {
        results {
            id
            name
            status
            image
        }
    }
}
```

How to Run and Save Outputs

- Use any GraphQL endpoint that supports characters(page: Int). Example: https://rickandmortyapi.com/graphql
- Replace ENDPOINT with your endpoint.

Bash

```
ENDPOINT="https://rickandmortyapi.com/graphql"
for i in 1 2 3 4; do
    body=$(jq -Rs --arg q "$(cat characters-page-$i.graphql)" '{
        query: $q
    }' <<<"")
    curl -s -X POST -H "Content-Type: application/json" \
        --data "$body" "$ENDPOINT" \
        > "characters-page-$i-output.json"
done
```

PowerShell

```
$Endpoint = "https://rickandmortyapi.com/graphql"
1..4 | ForEach-Object {
    $q = Get-Content "characters-page-$($_).graphql" -Raw
    $body = @{ query = $q } | ConvertTo-Json -Depth 5
    Invoke-RestMethod -Method Post -Uri $Endpoint -ContentType "application/json" -Body $body |
        ConvertTo-Json -Depth 10 | Out-File "characters-page-$($_)-output.json" -Encoding utf8
}
```

Acceptance Checklist

- Four .graphql files exist, one per page (1–4).
- Each query uses characters(page: N) and selects id, name, status, image under results.
- Four .json output files are saved with the API response.
- README.md explains setup, queries, and how to generate outputs.

Notes

- If your endpoint requires authentication, add the appropriate Authorization header to the curl/PowerShell commands.
- The JSON output should include a top-level data object with the characters.results array.
